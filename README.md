# se-time-input

Polymer wrapper around &lt;input type="time"> with browser-dependent appearance

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
## API
Component have four public properties.
1. Value

|                             |         |
| ---                         | ---     |
| **Property name**           | value   |
| **Property type**           | String  |
| **Default value**           | '00:00' |
| **Can be set from html**    | Yes     |
| **Corresponding attribute** | value   |
|                             |         |

Actual value of the component. Has format hh:mm where hh is hours(values from 0 to 23) and mm is minutes(values from 0 to 59). Input in inacceptable format will cause error to show.
```html
      <se-time-input value="12:34"></se-time-input>
```
```javascript
      var customEl = document.querySelector('se-timer');
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

# Demo
Better view on webcomponentsjs.org
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
