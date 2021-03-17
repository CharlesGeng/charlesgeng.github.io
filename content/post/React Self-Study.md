---
title: "React Self Study"
date: 2021-03-17T10:23:53+09:00
draft: false
tags:
  - IT
  - REACT
  - FRONT-END
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

- **Avoiding the Dependent Value Pitfall**

 > **How to avoid**: When you have a series of dependent changes to make, you can pass a function to the setState method that will be invoked when the state data has been updated and that can be used to perform tasks that rely on the changed state values(Page. 299)

- **Avoiding the Missing Updates Pitfall**

 >If you need to perform multiple updates and have each take effect in sequence, then you can use the version of the setState method that accepts a function as its first argument.(Page. 302)

- **Defining Prop Types and Default Values**
  - componentName.propTypes & componentName.defaultProps
  - static propTypes & static defaultProps

## Chapter 12
