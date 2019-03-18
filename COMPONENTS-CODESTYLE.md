
# Components Code Style [WIP]

## React

### Pass `children` explicitly.

```jsx
const {
	children,
	...props
} = this.props;

<table
    {...getHtmlProps(props)}
>
    {children}
</table>
```

### To handle `children` use `Children.map` or `Children.toArray`

1) This methods can pass and autofill `key`s for every child.
2) Filters `null`s in output.

```jsx
<ul>
    {Children.map(children, child => child && (
        <li>{child}</li>
    ))}
</ul>
```

### Be sure to pass `props` on.

```jsx
export function MenuButton({
	children,
	...props
}) {
	return (
		<Button
			{...props}
		>
			{children}
		</Button>
	);
}
```

### Pass `props` on before other props.

```jsx
<Button
    {/* Firstly */}
    {...props}
    {/* Other props */}
    type='button'
>
    {children}
</Button>
```

### Pass `props` on to HTML-elements with `getHtmlProps` helper.

```jsx
<table
    {...getHtmlProps(props)}
>
    {children}
</table>
```

### Do not pass excess props.

```jsx
const {
    children,
    ...props // with `onChange`
} = this.props;

<div
    {...getHtmlProps(props, ['onChange'])}
>
    {children}
</div>
// or
Reflect.deleteProperty(props, 'onChange');

<Button
    {...props}
>
    {children}
</Button>
// ...
// `onChange` used in other place
onChange(event) {
    this.props.onChange(event.target.value);
}
```

### Use this pattern to provide internal element reference.

```jsx
propTypes = {
    elementRef: PropTypes.func
}
// ...
<input
    {...getHtmlProps(props)}
    ref={elementRef}
    {/* ... */}
/>
```

> TODO: `React.forwardRef`

## Stylable

### Variables naming

Rule:

```
[type][Name][Variant?]
```

Example:

```css
sizeText: 1rem;
sizeTextLg: 2rem;
colorText: white;
colorBackground: #007bff;
colorBackgroundHover: #0069d9;
```
