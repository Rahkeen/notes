This is going to be raw + distilled notes as I go through the Joy of React course by Josh W. Comeau

2026-02-9
---

*Components*

React Components NEED to start with a CapitalLetter

When passing in props to a component, you can use object destructuring inline. 
```javascript
function FriendlyGreeting({ name = "there" }) {
	return (
		<p>
			Hey {name}
		</p>
	);
}
```
*Reminder that the parentheses are optional but they do allow you to write the component on a new line for indentation purposes*


We can also pass data as "children" to the component by setting something between the open and closing tag.
```javascript
<Component>
	hello
</Component>

// is the same as

<Component children="hello" />

function Component({ children }}) {
	<p>{children}</p>
}
```

