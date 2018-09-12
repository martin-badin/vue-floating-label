# vue-floating-label

## Props

### label

```js
{
  type: String,
  required: true
}
```

### showOnTop

```js
{
  type: Boolean,
  default: false
}
```

### disabled

```js
{
  type: Boolean,
  default: false
}
```

### align

```js
{
  type: String,
  default: 'center',
  validate: align => ["center", "top"].indexOf(align) !== -1
}
```

## Example

```js
import FloatingLabel from "vue-floating-label";
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

<floating-label label="Label">
  <textarea></textarea>
</floating-label>

<floating-label label="Label" disabled>
  <input type="file">
</floating-label>
```
