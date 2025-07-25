
Props (short for "properties") are the mechanism for passing data from a parent component to a child component in React. They allow you to create dynamic and reusable components.

---

### Core Concepts

-   **Unidirectional Data Flow:** Data in React flows in one direction: from parent to child. A child component receives props but cannot pass data back up to the parent via props.
-   **Read-Only:** A fundamental rule in React is that **props are immutable**. A component must never modify its own `props` object. This ensures a predictable data flow and prevents bugs.

---

### Passing and Accessing Props

You pass props to a component as if they were HTML attributes. The child component receives these props as a single object.

#### **Parent Component (`App.js`)**

Here, the `App` component passes a `name` (string) and `age` (number) prop to the `UserProfile` component.

```jsx
import React from 'react';
import UserProfile from './UserProfile';

function App() {
  return (
    <div>
      <UserProfile name="Alex" age={28} />
      <UserProfile name="Jordan" age={32} />
    </div>
  );
}

export default App;
````

*Note: Non-string values like numbers, booleans, or variables must be wrapped in curly braces `{}`.*

#### **Child Component (`UserProfile.js`)**

The child component receives the `props` object. You can access the values using dot notation (e.g., `props.name`).

```jsx
import React from 'react';

function UserProfile(props) {
  return (
    <p>
      User: <strong>{props.name}</strong>, Age: <strong>{props.age}</strong>
    </p>
  );
}

export default UserProfile;
```

-----

### Destructuring Props

Destructuring is a popular and cleaner way to access props inside a child component. It makes the code more readable by avoiding the repetitive use of `props.`

```jsx
import React from 'react';

// Destructuring directly in the function's parameter list
function UserProfile({ name, age }) {
  return (
    <p>
      User: <strong>{name}</strong>, Age: <strong>{age}</strong>
    </p>
  );
}

export default UserProfile;
```

-----

### The `children` Prop

The `children` prop is a special prop that is automatically passed to a component. It contains whatever content is placed between the opening and closing tags of that component.

#### **Parent Component (`App.js`)**

```jsx
import React from 'react';
import Card from './Card';

function App() {
  return (
    <Card>
      <h2>This is a title</h2>
      <p>This paragraph is passed as a child.</p>
    </Card>
  );
}
```

#### **Child Component (`Card.js`)**

The `Card` component can then render this content by using `props.children`.

```jsx
import React from 'react';

function Card(props) {
  return (
    <div className="card-container">
      {props.children}
    </div>
  );
}
// Or using destructuring: function Card({ children }) { ... }
```

-----

### Default Props

You can define default values for props using `defaultProps`. This is useful for preventing errors when a prop is not passed by the parent component.

```jsx
import React from 'react';

function Button({ label, color }) {
  return <button style={{ backgroundColor: color }}>{label}</button>;
}

// Setting default values
Button.defaultProps = {
  label: 'Click Me',
  color: 'lightgray'
};

export default Button;
```

Now, if you render `<Button />` without any props, it will still display a gray button with the text "Click Me".