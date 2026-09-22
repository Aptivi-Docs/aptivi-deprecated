---
description: How do you use it?
---

# 🖥️ How to use

Using this library is very simple! Just use the `ColorSeq` namespace in any piece of code you want to use the library, as in: `using ColorSeq;`

This library contains several functions that you can make use of in your console application:

* Building a `Color` instance that supports RGB and 255-color modes
* Getting console color information from the 255-color mode
* Simulating color-blindness during compilation

## Building a `Color` instance

You can build your own `Color` instance for usage in your console application. There are various ways to build it:

* `Color(int R, int G, int B)`
* `Color(ConsoleColors ColorDef)`
* `Color(int ColorNum)`
* `Color(string ColorSpecifier)`

The `ColorSpecifier` can be of the syntax:

* `<num>`
  * `<num>` should be of the range between 0 and 255
* `<rrr>;<ggg>;<bbb>`
  * `<rrr>`, `<ggg>`, and `<bbb>` should be of the range between 0 and 255
* `#000000`
  * Hexadecimal representation of the color for HTML fans
* `<ColorName>`
  * Color name from `ConsoleColors` enumeration

## Getting console color information

You can get detailed information about the console color ranging from 0 to 255 by making a new instance of the `ConsoleColorsInfo` class:

* `ConsoleColorsInfo(ConsoleColors ColorValue)`

## Simulating color-blindness

{% hint style="info" %}
This feature is not available in the Rust port of this library.
{% endhint %}

In the `ColorTools` static class, it contains several color blindness simulation tools that you can use:

* `EnableColorTransformation`
  * Enables the color transformation to adjust to color blindness upon making a new instance of color
* `EnableSimpleColorTransformation`
  * Enables the simple color transformation. This changes formula from Brettel 1997 (value is false) to Vienot 1999 (value is true)
* `ColorDeficiency`
  * Specifies the type of color blindness (Protan, Deutan, and Tritan)
* `ColorDeficiencySeverity`
  * Specifies the severity of the color deficiency ranging between 0.0 and 1.0 from lowest to highest

After you change these values, the next time you make a new instance of `Color`, you'll notice that the resulting color is shifted to adjust to color-blindness.
