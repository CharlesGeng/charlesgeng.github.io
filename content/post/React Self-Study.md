---
title: "React Self Study"
date: 2021-03-17T10:23:53+09:00
draft: false
tags:
  - REACT
  - FRONT-END
categories: 
  - IT
---

## Book **Pro React 16**

- ISBN: 978-1-4842-4450-0
- [homepage](https://www.apress.com/gp/book/9781484244500)

## Chapter 09

- to be updated

## Chapter 10

- to be updated

## Chapter 11 Stateful Component

- **Stateful Component Definition**

```jsx
import React, { Component } from 'react'

export default class statefulComponent extends Component {
  constructor(props) {
    super(props)

    this.state = {
      myState: 0
    };
  }

  handleClick = () => {
    this.setState({ myState: 1 });
  }

  render() {
    return (
      <div>
        <button onClick={this.handleClick}>Click Me!</button>
      </div>
    )
  }
}

```

- :warning:**Avoiding the Dependent Value Pitfall**

 > **How to avoid**: When you have a series of dependent changes to make, you can pass a function to the setState method that will be invoked when the state data has been updated and that can be used to perform tasks that rely on the changed state values(Page. 299)

- :warning:**Avoiding the Missing Updates Pitfall**

 >If you need to perform multiple updates and have each take effect in sequence, then you can use the version of the setState method that accepts a function as its first argument.(Page. 302)

- **Defining Prop Types and Default Values**
  - componentName.propTypes & componentName.defaultProps
  - static propTypes & static defaultProps

## Chapter 12 Working With Events

- **Events**

> Events are handled using properties that share the name of the corresponding DOM API property, expressed in camel case. The DOM API onclick property is expressed as onClick in React applications and specifies how to handle the click event, which is triggered when the user clicks an element. 

- **AVOIDING THE EVENT FUNCTION INVOCATION PITFALLS**

1. :warning: The first **mistake** is to enclose the function you require in quotes rather than braces. This provides react with a string value instead of a function and produces an error in the browser’s Javascript console.

```jsx
<button className="btn btn-primary" onClick="this.handleEvent" >
```

2. :warning: The other common mistake is to use an expression that invokes the function you require. This expression results in react invoking the handleEvent method when the component object is created and not when an event is triggered. You won’t receive an error or warning for this mistake, which makes the problem harder to spot.

```jsx
<button className="btn btn-primary" onClick={ this.handleEvent() } >
```

- **Access Component Features**

```jsx
/*******************
    1st Methord
********************/
handleEvent = () => {
  //do something
}
...
onClick = {this.handleEvent}

/*******************
    2nd Methord
********************/
handleEvent  ()  {
  //do something
}
...
onClick = {() => this.handleEvent()}

/*******************
    3rd Methord
********************/
constructor(props){
  this.handleEvent = this.handleEvent.bind(this)
}
...
onClick = {this.handleEvent}
```

- **Avoiding the Event Reuse Pitfall**

> React reuses SyntheticEvent objects and resets all the properties to null once an event has been handled. The **persist** method is used to prevent React from resetting the event object,

```jsx
foo = () => {
  event.persist()
  // do something
}
```

- **Invoking Event Handlers with a Custom Argument**

```jsx
  handleEvent = (event, newTheme) => {
    this.setState({ theme: newTheme });
  }

  <button
    className={`btn btn-${this.state.theme} m-2`}
    {/* Custom parameter*/}
    onClick={(e) => this.handleClick(e, "danger")}>
    Danger
  </button>

```

- **Preventing Default Behavior**

- Some events have behavior that the browser performs by default. The **preventDefault** method can be called on event objects to prevent the default behavior.
