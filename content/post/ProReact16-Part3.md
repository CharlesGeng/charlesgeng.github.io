---
title: "Pro React 16 - Part 3"
date: 2021-05-11T16:52:18+09:00
draft: false 
tags:
  - REACT
  - FRONT-END
  - Pro React 16
categories: 
  - IT
---

## Chapter 18 CREATING COMPLETE APPLICATIONS

- Updating an object with setState in React. [link](https://stackoverflow.com/questions/43638938/updating-an-object-with-setstate-in-react)
- Array.prototype.concat()
  - **Syntax**[link](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/concat)
  
  ```js
  concat()
  concat(value0)
  concat(value0, value1)
  concat(value0, value1, ... , valueN)
  ```

## Chapter 19  USING A REDUX DATA STORE

| Name           | Description                                                                                                                                                                                                                                                      |
| :------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| action         | An action describes an operation that will change the data in the store. Redux doesn’t allow data to be modified directly and requires actions to specify changes.                                                                                               |
| action type    | Actions are plain JavaScript objects that have a type parameter, which specifies the action type. This ensures that actions can be identified and processed correctly.                                                                                           |
| action creator | An action creator is a function that creates an action. Action creators are presented to React components as function props so that invoking the action creator function applies a change to the data store.                                                     |
| reducer        | A reducer is a function that receives an action and processes the change it represents in the data store. An action specifies which operation should be applied to the data store, but it is the reducer that contains the JavaScript code that makes it happen. |
| selector       | A selector provides a component with access to the data it requires from the data store. Selectors are presented to React components as data props.                                                                                                              |
