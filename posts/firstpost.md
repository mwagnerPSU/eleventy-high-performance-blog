---
title: Getting Started with open-wc
description: This is a post about the basics of open-wc.
date: 2021-08-30
scheduled: 2021-08-30
tags:
  - programming
  - web components
layout: layouts/post.njk
image: https://cdn.pixabay.com/photo/2020/08/30/20/54/rice-field-5530707_1280.jpg
---
In this post we'll go through all the steps to set up a web component using open-wc in windows. We'll go through the needed dependencies and steps to get a web component going.

### Before we start
We need a few things before creating a web component. First we'll install Node.js from their [website](https://nodejs.org/en/download/). Next, we'll install npm by opening a command prompt and typing 
```
npm install
```
It is optional to also install yarn which can be done with your command prompt as well.
```
npm install -g yarn
```

### Creating a Web Component
Now we're ready to actually create a web component.

Start by using the command prompt to go into your desired folder. For example, `cd "project folder"`

Then initiate the web component by using this command.
```
npm init @open-wc
```

We now have a few options to pick from.

First we can can choose to scaffold a new project or expand upon an existing one. To create a new component we'll pick the scaffolding option by using the arrow keys and pressing the space bar. 

Next, we can choose between creating a web component or an application. We'll choose a web component. 

The third set of choices are optional and will determine what will be set up automatically. Use the space bar to select your options, I choose to select all of them. To move on click the enter key. 

Then we choose whether to use typescript or not. I choose not to. 

Enter a name for your web component. 

Now, we'll choose to write the proposed file structure to the disk and pick what dependencies to setup the web component with. You can choose to install with npm or if you previously installed yarn you can install using yarn.

You're all set!

### Running and Editing your Web Component
The web component we just created can be ran by changing the directory in the command prompt to the folder that has been created. Ex. `cd test-project`

Then running the component with, `npm run start`.

Lastly, to edit the component in VS Code use the same commands as previously to change the directory to the project folder then type the command, `code .`