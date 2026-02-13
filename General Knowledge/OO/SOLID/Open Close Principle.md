The Open Close Principle is the 2nd SOLID principle. It states that classes should be open for extension, but closed for modification. So you can add new behaviour (extend) but shouldn't have to change existing behaviour to add the new behaviour.

## Example of Violation

```C#
public class InvoiceProcessor
{
    public void ProcessInvoice(Invoice invoice, string paymentType)
    {
        if(paymentType == "CreditCard")
        {
            // credit card processing
        }
        else if(paymentType == "PayPal")
        {
            // PayPal processing
        }
        else if(paymentType == "Bitcoin")
        {
            // Bitcoin processing
        }
    }
}

```

What are the problems with the above?
1) Every time you add a new payment type, you need to modify `InvoiceProcessor`

## Fixed Example

Use an abstraction:

```C#
public interface IPaymentProcessor
{
    void ProcessPayment(Invoice invoice);
}
```

Implement different processors:

```C#
public class CreditCardProcessor : IPaymentProcessor
{
    public void ProcessPayment(Invoice invoice)
    {
        // credit card processing
    }
}

public class PayPalProcessor : IPaymentProcessor
{
    public void ProcessPayment(Invoice invoice)
    {
        // PayPal processing
    }
}
```

`InvoiceProcessor` depends on abstractions, so to ad a new payment type you can create a new class implementing `IPaymentProcessor` instead of modifying the existing, functioning class.

```C#
public class InvoiceProcessor
{
    private readonly IPaymentProcessor _paymentProcessor;

    public InvoiceProcessor(IPaymentProcessor paymentProcessor)
    {
        _paymentProcessor = paymentProcessor;
    }

    public void Process(Invoice invoice)
    {
        _paymentProcessor.ProcessPayment(invoice);
    }
}
```