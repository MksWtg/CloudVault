
### The Problem

In this file: https://github.com/WiseTechGlobal/CargoWiseCloud.Console/blob/master/Source/ConsoleFrontend/src/components/customersystems/wtg-get-customersystems.vue we have the code:
```
<CreateCustomerSystems
				v-model="popUpDetails.createCustomerSystemsVisibility"
				:customer-codes="customerCodes"
				@close="handlePopUps('createCustomerSystemsVisibility', false)" />
```
Which passes the bool `createCustomerSystemsVisibility` to the child component `CreateCustomerSystems`.

In the child component: https://github.com/WiseTechGlobal/CargoWiseCloud.Console/blob/master/Source/ConsoleFrontend/src/components/customersystems/wtg-create-customersystems.vue the root element is a single `<WtgModal>` component from the  [SUPPLY](https://design.wtg.zone/?path=/docs/intro--overview) component library.

Problem: where is the grandchild `WtgModal` receiving the information it needs to know whether to display the modal? We know practically that what is really happening is that this data is provided via `v-model` (bool `createCustomerSystemsVisibility`) in the grandparent, but then how does it propagate through the parent into the child? Especially since we never declare this prop in the child in the form of a `modelValue`. Yet somehow, via empirical testing we know that this setup accurately connects the grandparent and grandchild through the parent. How?
### Solution: Attribute Fallthrough

If the parent has no declared props and its root element is exactly the child component, Vue automatically passes undeclared props (including `modelValue` and `update:modelValue`), known as attributes, to that child.

```
// Grandparent
<Parent v-model="foo" />

// Parent
<template>
  <Child /> // child is only element and is root
</template>
<script setup>
// no props declared
</script>

// Child
<template>
  <div>
    Child sees modelValue: {{ modelValue }}
  </div>
</template>
<script setup>
const props = defineProps({ modelValue: Number })
</script>

```

- `v-model` becomes `:modelValue="foo"` + `@update:modelValue="foo = $event"`
- Parent does not declare modelValue, so it ends up in `$attrs`
- `$attrs` automatically attaches to the root element
- Child now receives `modelValue` and can emit `update:modelValue` directly, updating the grandparent

### Docs
https://vuejs.org/guide/components/attrs#nested-component-inheritance