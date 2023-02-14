---
layout:      project
title:       "Stellar"
date:        02 February 2023
image:
  path:       assets/img/projects/2023/stellar.png
caption:     The James Webb of UI Testing
description: >
    Stellar is an opinionated Python library designed to make writing Selenium and Appium code easier by providing a unified API for web and mobile test automation.
links:
  - title:   Devtopia Link
    url:     https://devtopia.esri.com/sam10266/stellar

featured:    true
---
# Stellar

## Key Features
* testing utilities for interacting with the UI, including: waits, actions, and validations
* well-defined page object structure
* declarative style via formalized annotation
* component-oriented design to support modern OOP in your testing
* structural typing utilities for advanced flow control
* 100% typed signatures
* Robust exception and error handling

## Key Concepts

### `Adapters`
*The logical implementation of the two core objects in `stellar`: the `Container` and `Element`*

These objects interface with both Selenium and Appium to provide a single API for interacting with web and mobile UI.

#### 1. The `Container` Class
*The base class for interacting with the UI.*

You can consider this synonymous with any UI tier - screen, component, or element. All adapters' base implementation is 
modeled on the `Container`. The `Container` holds test utilities that 
allow you to make assertions about its child elements with logical default test behavior.

Some examples of what you can do with the `Container` include:
- **Searching** for child elements within the `Container`
- Validating attributes of the `Container` such as **class**, **accessibility id**, **text content**
- Validating attributes of the child elements like **visibility**, **selection**, or **focus**
- Performing actions on the `Container` like **clicking** or **scrolling**
- **Selecting** child elements

##### The primary responsibility of the `Container` is to represent a **parent element** of other elements.

#### 2. The `Element` Class
*A subtype of `Container`, representing an individual `WebElement` or `MobileElement`*

The `Element` represents individual UI `Elements` of varying scales, from buttons and search bars to panels and popups.
This class holds test utilities that allow you to make assertions about the `Element` it represents or its children.

Some examples of what you can do with the `Element` include:
- All `Container` actions and validations
- Validating attributes of the `Element` such as **class**, **accessibility id**, **text content**
- Validating attributes of the child elements like **visibility**, **selection**, or **focus**
- Performing actions on the `Element` like **typing**, **clearing text**, or **pressing buttons**

##### The primary responsibility of the `Element` is precise action and attribute validation.

#### 3. The `Component` Class and `annotation` API
*The bread and butter of `stellar` 90% of your implementation code will live inside a `Component` and 99% of your element
references will be towards an `annotation`*

With the `annotation` API, you can use an element's **selector** and **identifier** to create simple declarative page 
objects that can be tied to specific `Components`. Once declared, simply call the `annotation` to access the element's 
(and any parent element's) action or validation methods.

Some examples of what you can do with `annotation` include:
- Declare a child `Element` using its **xpath**, **accessibility id**, **ios class chain**, **css selector** and more
- Give long `Element` xpaths or identifiers simpler more precise names
- Return a single `Element`, an `ElementCollection`, or the first visible `Element` in a group.
- Perform all the actions and validations available in the `Component` parent

A `Component` is a subtype of `Element` that's designed to be:
- **re-usable** across screens
- a **`Container`** for other `Elements` or `Components`
- scoped to a **specific parent `Element`**