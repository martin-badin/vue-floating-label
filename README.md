# vue-floating-label

## Props

### label

```javascript
{
  type: String,
  required: true
}
```

### showOnTop

```javascript
{
  type: Boolean,
  default: false
}
```

### disabled

```javascript
{
  type: Boolean,
  default: false
}
```

### align

```javascript
{
  type: String,
  default: 'center'
}
```

## Example

```js
import { FloatingLabel } from "vue-floating-label";
```

```html
<floating-label label="Label">
  <input value="">
</floating-label>

<floating-label label="Label">
  <select>
    <option value="">Default</option>
    <option value="aa">AA</option>
  </select>
</floating-label>

<floating-label label="Label" show-on-top>
  <input value="">
</floating-label>
```

## Project setup

````
yarn install

```
### Compiles and hot-reloads for development
```

yarn run serve

```
### Compiles and minifies for production
```

yarn run build

```
### Lints and fixes files
```

yarn run lint

```

```
````
