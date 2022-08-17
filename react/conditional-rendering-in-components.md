# Conditional Rendering In Components

__Category: React__

Conditional rendering in React components can be done using element variables or inline if statements.

### Element variables

You can use variables to store elements and render the output:

```javascript
type HeaderProps = {
  text: string;
  loggedIn: boolean;
}

const Header = ({ text, loggedIn } : HeaderProps) => {

  let heading;
  if (loggedIn) {
    heading = <Logout>Logout {text}</Logout>
  } else {
    heading = <Login>Login {text}</Login>
  }

  return (
    <div>
      {heading}
    </div>
  );
}
```

### Inline if with logical && operator

Expressions can be wrapped using curly braces. The JavaScript logical && operator can conditionally render an element:

```javascript
type HeaderProps = {
  text: string;
  loggedIn: boolean;
}

const Header = ({ text, loggedIn } : HeaderProps) => {

  return (
    <div>
      {loggedIn &&
        <Logout>Logout {text}</Logout>
      }
      {!loggedIn &&
        <Login>Login {text}</Login>
      }
    </div >
  );
}
```
