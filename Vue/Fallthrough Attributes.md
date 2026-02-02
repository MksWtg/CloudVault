
### The Problem
In this file: https://github.com/WiseTechGlobal/CargoWiseCloud.Console/blob/master/Source/ConsoleFrontend/src/components/customersystems/wtg-get-customersystems.vue we h

### Attribute Fallthrough

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
