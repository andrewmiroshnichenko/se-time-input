[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/andrewmiroshnichenko/se-time-input)
# se-time-input

Polymer wrapper around input type `time` with browser-dependent appearance. Basically, it allows user to use native mobile time pickers and Edge time picker, because they are looking good and provide good experience. In other cases (unsuppored type `time` or desktop Chrome) input will become `text` with ability to manually enter the value.

## Install
```
$ bower install se-time-input
```
Make sure you have the [Polymer CLI](https://www.npmjs.com/package/polymer-cli) installed. Then run `polymer serve` to serve your element locally.

## Viewing component

```
$ polymer serve
```

## Running tests

```
$ polymer test
```
# API

## Properties.

1. Value

|                             |         |
| ---                         | ---     |
| **Property name**           | value   |
| **Property type**           | String  |
| **Default value**           | 00:00   |
| **Can be set from html**    | Yes     |
| **Corresponding attribute** | value   |
|                             |         |

Actual value of the component. Has format hh:mm where hh is hours(values from 0 to 23) and mm is minutes(values from 0 to 59). Input in inacceptable format will cause error to show.
```html
      <se-time-input value="12:34"></se-time-input>
```
```javascript
      var customEl = document.querySelector('se-time-input');
      customEl.value; // returns String '12:34'
      customEl.value = '10:00';
      customEl.value; // returns String '10:00'
 ```
2. Disabled

|                             |            |
| ---                         | ---        |
| **Property name**           | disabled   |
| **Property type**           | Boolean    |
| **Default value**           | false      |
| **Can be set from html**    | Yes        |
| **Corresponding attribute** | disabled   |
|                             |            |

If true - disables possibility of user interaction with component. But component’s value still will be changeable from code.
**Warning:** presence of this property as attribute of `<se-time-input>` tag will lead to disabling of component, even if it's value will be `false`.

```html
      <se-time-input></se-time-input>
```
```javascript
      var customEl = document.querySelector('se-time-input');
      customEl.disabled; // returns Boolean false
      customEl.disabled = true;
      customEl.disabled; // returns Boolean true
 ```
3. Placeholder

|                             |             |
| ---                         | ---         |
| **Property name**           | placeholder |
| **Property type**           | String      |
| **Default value**           | -           |
| **Can be set from html**    | Yes         |
| **Corresponding attribute** | placeholder |
|                             |             |

String that is shown as component’s placeholder when component’s value is empty. Length of this property is limited to 10 characters, bigger placeholder will explicitely cut to this length. When component’s value changes from empty to non-empty placeholder should move to “upper left corner” of the component.

```html
      <se-time-input placeholder="Enter time"></se-time-input>
```
```javascript
      var customEl = document.querySelector('se-time-input');
      customEl.placeholder; // returns String 'Enter time'
      customEl.placeholder = 'hh:mm';
      customEl.placeholder; // returns String 'hh:mm'
 ```
## Styling

The following custom properties are available for styling:

| Custom property                   | Description                                                         | Default                        |
| ---                               | ---                                                                 | ---                            |
| `--setimeinput-text-color`        | Input digits color                                                  | Browser-default(black)         |
| `--setimeinput-bottom-line`       | Style of component’s bottom line. Other borders are disabled        | `1px solid rgba(0, 0, 0, .12)` |
| `--setimeinput-placeholder-color` | Color of placeholder text                                           | `#999999`                      |
| `--setimeinput-font-size`         | Font size of digits. All component dimesions will scale accordingly | `16px`                         |
| `--setimeinput-font-family`       | Font family of input digits                                         | `Roboto, sans-serif`           |

## Events

timeChange(event)
Event is fired when input field, either input[type="time"] or input[type="text"] loses focus. This is wrapper of `change` event, presented on every input element.
New component value is available in event object, as `event.detail.value`.
```html
      <se-time-input></se-time-input>
```
```javascript
      var customEl = document.querySelector('se-time-input');
      customEl.addEventListener('timeChange', (event) => {
        console.log(event.detail.value);
      });
      // user focuses on input
      // user enters time value '02:00'
      // user removes focus from input
      // '02:00' is printed on the console

 ```
# Demo
Better view on [webcomponentsjs.org](https://www.webcomponents.org/element/andrewmiroshnichenko/se-time-input)
 <!--
```
<custom-element-demo>
  <template>
    <script src="../webcomponentsjs/webcomponents-lite.js"></script>
    <link rel="import" href="se-time-input.html">
    <next-code-block></next-code-block>
  </template>
</custom-element-demo>
```
-->
```html
<se-time-input placeholder="hh:mm" value="10:45"></se-time-input>
```
