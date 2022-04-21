---
title: Slots for Tots - A Dive into Slots with Web Components
description: 
date: 2021-12-14
scheduled: 2021-12-14
tags:
  - programming
  - web components
layout: layouts/post.njk
---
## What are slots?
When writing reusable web components we come across the need to let a programmer easily enter any content they want to make the component work for their project. In a low-level sense we traditionally could use variables like this:
`<div>${this.variable}</div>`
`<demo-project variable="Boring text"></demo-project>`

This would get the job done for entering "Boring text" into our div but what if we wanted to put a `<ul>` with 3 `<li>` elements in place?

This is where slots come in. We can take that code and create a simple slot such as this:
`<div><slot></slot></div>`
And pass our list elements in like this:
```
<demo-project>
  <ul>
    <li>Exciting text 1</li>
    <li>Exciting text 2</li>
    <li>Exciting text 3</li>
  </ul>
</demo-project>
```

Now we'll be able to see that entire list in our div to be used in any way we want.

## Why slots for tots?
Banking of the clever slogan 'toys for tots', slots for tots (some would say is much more clever) is a way of explaining that slots enhance the ability to add custom children elements to a designated parent element. When the list above is 'slotted' into our div, that unordered list and each list element become children of our div. We are then able to go through the list and use, alter, move, etc. each element as if it was a normal ingrained list.

## But wait! There's more...
After using slots a few times, you might run into the issue of needing two or more slots. This becomes a problem with the code we have since our `<demo-project>` tag only has one spot available for a slot. 

To fix this, we can use a named slot rather than a regular slot. Named slots give the ability to select which slot we want our custom content to go to.

Let's take our `<demo-project>` for example. If we wanted to add a header into one slot and a button into another we could do something like this:
```
<div>
  <slot name=header></slot>
  <slot name=button></slot>
</div>
```
```
<demo-project>
  <span slot=header><h2>Even more exciting header</h2></span>
  <span slot=button><button>Even more exciting button</button></span>
</demo-project>
```

By naming our slots and using `slot=[name of slot]` we're able to direct where we want our slotted content to go.

## Having fun yet?
I hope so because knowing how to slot content can open up a huge amount of possibilities. What if you want to slot content to other components inside your main? Sure! You can use slots to pass virtually anything, anywhere. Let's say you want to slot a header into a sub-component while slotting a list into your main component:

#### sub-component
```
<div>
  <slot name=header></slot>
</div>
```
#### demo-project
```
<div>
  <sub-component>
    <h5 slot=header>${this.header}</h5>
  </sub-component>
  <slot></slot>
</div>
```
#### demo / index.html 
```
<demo-project header="Most exciting header">
  <ul>
    <li>Most exciting list item 1</li>
    <li>Most exciting list item 2</li>
    <li>Most exciting list item 3</li>
  </ul>
</demo-project>
```
The result looks like this:
##### Most exciting header
* Most exciting list item 1
* Most exciting list item 2
* Most exciting list item 3

## Wrap it up
If you're interested in slots and want to look at a more in-depth use of them, I've created a project that does just that.
Check out the [Github](https://github.com/IST-402-Group-1/project-two) and feel free to install this project into your own project from [npm](https://www.npmjs.com/package/@ist-402-group-1/project-two).
  