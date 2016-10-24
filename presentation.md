# Introduction to React

---

## Single-page Javascript Applications

----

### Traditional Website:
- Client sends request for page to server
- Server communicates with database and returns templated HTML

### Modern Web Applications
- Server ships blank HTML
- Frontend Javascript communicates with backend RESTful API for information and dynamically updates HTML

----

![butwhy](https://media.giphy.com/media/1M9fmo1WAFVK0/giphy.gif)

----

- Responsive (consider this presentation)
- Reduced server load
- Less communication over-the-wire

----

### SPA Frameworks
- Help mitigate messy UI through convention
- Popular frameworks:
   - Angular
   - Ember
   - React

---

## React
- JS SPA framework
- Open source
- Maintained by Facebook
- Massive popularity
- Originally designed to handle only the View, but large ecosystem allows for Modeling, routing, etc.

----

### General Overview: Components
- The atomic unit of a React application
- Composable, reusable, and extendable
- Component trees are mounted to the real HTML root anchor
- Contains:
   - UI
   - Lifecycle event handlers
   - State
   - Props

----

### Internal State
- A component's internal state is tracked by the `state` object
- `setState()` takes a new state object and merges it with the previous state object
- Every time state changes, React recalculates the UI drawing

----

### Props
- Object similar to `state`
- Passed in from the parent at first mount, then immutable
- Essentially, initial state

----

### UI
- Every React component needs a `render()` function that returns a virtual DOM object
- Typically, this is written in JSX, which is an HTML-like templating syntax
- State variables may be interpolated, for example
- Can include other components, passing them props as attributes

```
render() {
    return(<div>
        <HeaderComponent layout="jumbo" />
        <p>Hello, world!</p>
        <p>{ this.state.pageViews } people have been here.</p>
    </div>)
}

```

----

### Lifecycle Events
- Functions that can be defined within components that fire at certain events
- Helpful in component management
- Some examples:
    - `componentWillMount` – Invoked once before rendering occurs.
    - `componentWillUpdate` – Invoked any time state changes. Passed both the old and new state and props.
    - `componentWillUnmount` – Invoked prior to unmounting component.

----

### Example Component
- Button increments a state variable and displays the click count

```
class Counter extends React.Component {

    constructor(props) {
        super(props);
        this.state = {
            clicks: props.initialClickCount
        };
    }

    increment() {
        this.setState({
            clicks: ++this.state.clicks
        })
    }

    render() {
        return(
            <div>
                <p>{ this.state.clicks }</p>
                <button
                    onClick={ this.increment.bind(this) }>
                    Increment
                </button>
            </div>
        )
    }
}
```

----

### General Overview: Virtual DOM
- Manipulating the DOM is intensive
- React maintains an internal ledger of "virtual", HTML-like element optimized for manipulation
- Components' state changes update this internal ledger
- React then calculates the minimum amount of DOM manipulation needed

![virtualdom](http://techblog.constantcontact.com/wp-content/uploads/2014/11/TechTalk_BAnderson_11052014_Image7.png)

----

![butwhy](https://media.giphy.com/media/1M9fmo1WAFVK0/giphy.gif)

----

### Virtual DOM performance

![layoutperf](https://cdn.auth0.com/blog/newdombenchs/Layout.svg)

---

## Example: Will It Rain in Pittsburgh?
- A small React application to determine if it will rain in Pittsburgh today (spoiler alert: it will)
- Also annoyed by how often you need to look

---

## React in the Real World

----

### Flux
- State management across component trees can become extremely complex, especially with sibling-component communication
- Lots of application-wide state management solutions, many implementing a Flux concepts (developed by Facebook)
- Redux is the most popular

----

### Webpack
- In the real-world React for the web is compiled, minified, and packaged into HTML
- Webpack is a build tool that makes this simple and easy
- Allows for hot module reloading and time-travel debugging

----

### React Native
- Allows for compiling React into native Java/Swift for mobile applications
- Coupled with efforts like Electron, allowing for cross-platform desktop applications, React can be transferred to virtually any platform
- Some sever-side React-based template libraries available, too, for non-SPAs

---

## Questions?

