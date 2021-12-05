---
description: More input types than you can dream of
---

# Keyboard

When you want to accept content from the user, you instantiate and interact with `wiiKeyboard`. Utilizing its method, you can specify layouts and options for input that best fit your content.

```javascript
var keyboard = new wiiKeyboard();
```

Note that `wiiKeyboard` will only function on pages loading over HTTPS. You will need to modify the Wii Shop Channel to load your content. Opera (and IOS via EC) only has SSLv3/TLS 1.0 available, so additional modifications to various trust levels may be necessary.

## Members

Unlike other objects, `wiiKeyboard` only exposes one member. Its usefulness is instead via its parameters variants.

| Member Name                                       | Discussion                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| ------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `keyboard.call(type)`                             | <p>Invokes a keyboard of the specified <a href="keyboard.md#keyboard-types">type</a>.</p><p></p><p><em>An example of</em> <code>keyboard.call(1)</code><em>.</em></p><p><img src="../.gitbook/assets/Screen Shot 2021-12-04 at 18.10.21.png" alt=""></p>                                                                                                                                                                                                                                               |
| `keyboard.call(type, rowLimit)`                   | <p>Invokes a keyboard of <a href="keyboard.md#keyboard-types">type</a> with a limit of the amount of rows available for typing.</p><p></p><p><em>An example of a row limit when invoked as</em> <code>keyboard.call(1, 1)</code><em>. As the text (highlighted red to designate the error) exceeds the first row, it is deleted upon entry.</em></p><p><img src="../.gitbook/assets/image (4).png" alt=""></p>                                                                                         |
| `keyboard.call(type, rowLimit, isPassword)`       | <p>Instantiates a keyboard of <a href="keyboard.md#keyboard-types">type</a> with <code>rowLimit</code> and whether the entered text <code>isPassword</code>. If true, entered text becomes asterisks after entry or space bar, as pictured beneath.</p><p></p><p><em>An example of</em> <code>keyboard.call(1, 3, true)</code><em>. Note that "text", highlighted red, has not yet converted to asterisks.</em></p><p><img src="../.gitbook/assets/Screen Shot 2021-12-04 at 18.05.39.png" alt=""></p> |
| `keyboard.call(type, rowLimit, isPassword, hint)` | <p>Instantiates a keyboard of type with <code>rowLimit</code>, whether the entered text <code>isPassword</code>, and a background text of <code>hint</code>.</p><p></p><p><em>An example of</em> <code>keyboard.call(1, 3, false, 'Text Hint')</code>.</p><p><img src="../.gitbook/assets/Screen Shot 2021-12-04 at 18.09.35.png" alt=""></p>                                                                                                                                                          |

## Keyboard Types

There are 11 variants of keyboards available. For all examples, the used code to invoke was similar to the following:

```html
<textarea rows="5" style="width: 100%" onmousedown="keyboard.call(1);"></textarea>
```

The 11 variants are as follows:

* [Default](keyboard.md#default)
* [Default (2)](keyboard.md#default-1)
* [Number Pad](keyboard.md#number-pad)
* [Default without Return, Completion, Number Pad](keyboard.md#default-without-return-completion-number-pad)
* [Large Font](keyboard.md#large-font)
* [Default without Return](keyboard.md#default-without-return)
* [Large Font without Return and Number Pad](keyboard.md#large-font-without-return-and-number-pad)
* [Large Number with Decimal](keyboard.md#large-number-with-decimal)
* [Large Number with Decimal (2)](keyboard.md#large-number-with-decimal-1)
* [Friend Code Entry](keyboard.md#friend-code-entry)
* [Default without Return](keyboard.md#default-without-return)

### Default

Type `0`, or defaulted to if any value above 13 is specified. A generic keyboard.

![](<../.gitbook/assets/image (5).png>)

### Default (?)

Type `1`. Appears to behave similarly to [Default](keyboard.md#default) on all regions.

![](<../.gitbook/assets/image (2).png>)

### Number Pad

Type `2`. Provides a generic number pad, useful for things such as friend code entry.

![](<../.gitbook/assets/image (9).png>)

### Default without Completion, Return Key

Type `3`. The same as [Default](keyboard.md#default), but lacking a return key and word completion/suggestion.

![](<../.gitbook/assets/image (11).png>)

### Large Font

Type `4`. Entered text cannot exceed the text field's length.

![](<../.gitbook/assets/image (6).png>)

### Default without Return, Completion, Number Pad

Type `5`. Lacks word completion/suggestion, and the switcher UI between QWERTY and a number pad: ![](<../.gitbook/assets/Screen Shot 2021-12-04 at 18.35.16.png>)

![](<../.gitbook/assets/image (10).png>)

### Large Font without Return and Number Pad

Type `6`. Lacks word completion/suggestion, and the switcher UI between QWERTY and a number pad.

![](<../.gitbook/assets/image (8).png>)

### Large Number with Decimal

Type `7`. Provides a decimal point alongside numeric entry.

![](<../.gitbook/assets/Screen Shot 2021-12-04 at 18.37.59.png>)

### Large Number with Decimal(?)

Type `8`. Appears to operate similarly to [Large Number with Decimal](keyboard.md#large-number-with-decimal) - TODO: Does this function differently in other regions?

![](<../.gitbook/assets/Screen Shot 2021-12-04 at 18.38.08.png>)

### Friend Code Entry

Type `9`. Provides a usable Friend Code entry pad.

![](<../.gitbook/assets/Screen Shot 2021-12-04 at 18.38.22.png>)

### Default without Return

Type `10`. Unlike [Default without Completion, Return](keyboard.md#default-without-return-key), this type does have completion. It lacks a return key.

![](<../.gitbook/assets/Screen Shot 2021-12-04 at 18.38.41.png>)
