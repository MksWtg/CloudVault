Prerequisites: [[Unit Testing]]

NUnit is popular library for unit testing in C#.

```C#
using NUnit.Framework;

namespace MyTests
{
    // A simple class to test
    public class Calculator
    {
        public int Add(int a, int b)
        {
            return a + b;
        }

        public int Subtract(int a, int b)
        {
            return a - b;
        }
    }

    [TestFixture] // Marks this class as containing tests
    public class CalculatorTests
    {
        private Calculator _calculator;

        [SetUp] // Runs before each test
        public void Setup()
        {
            _calculator = new Calculator();
        }

        [Test] // Marks this method as a test
        public void Add_WhenCalled_ReturnsSum()
        {
            int result = _calculator.Add(3, 5);
            Assert.AreEqual(8, result); // Verifies the result
        }

        [Test]
        public void Subtract_WhenCalled_ReturnsDifference()
        {
            int result = _calculator.Subtract(10, 4);
            Assert.AreEqual(6, result);
        }

        [Test]
        public void Add_WithNegativeNumbers_ReturnsCorrectSum()
        {
            int result = _calculator.Add(-2, -3);
            Assert.AreEqual(-5, result);
        }
    }
}

```

## `Setup` Method
You can annotate a setup method (a method whose name is `Setup`) with the `[Setup]` attribute. This ensures it gets run before every test. This is useful because we don't want state from one variable spilling into another, all tests should be individual for determinism.

## `TestFixture` Attribute
You can annotate a class containing tests with `[TestFixture]`. This is necessary in certain cases such as if your test class has a constructor with parameters. Simple classes with freestanding tests may function without it but it is good practice to include it.

## `Test` Attribute
This denotes a single test, that can be run from visual studio test explorer or using dotnet test.

## `Assert` Class
This is the basis of an nunit test, which is a line of code that at runtime expects two values to be equal (the contents of the test). If the statement `Assert.AreEqual(-5, result);` is true the test passes otherwise it fails.




