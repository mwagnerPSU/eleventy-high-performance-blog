---
title:  Web Component Frameworks
description: 
date: 2021-09-21
scheduled: 2021-09-21
tags:
  - programming
  - web components
layout: layouts/post.njk
---
Ever been confused by web programming? No? ...stop lying

JavaScript runs the majority of web pages and with JS we can create custom web components. Since web components are relatively new they may be tough to pick up and implement. To ease the pain we all feel, people have made frameworks to slightly ease the burden of creating web components.

We'll compare some of the most popular frameworks (Angular, Vue, React) and a toolchain (Stencil) to determine the pluses and minuses that apply across them.

### Commonalities
Angular, React and Stencil are all similar in the way they conduct their file structures. Package.json is located in the main directory while the main page content is located in a designated folder. The outlier, Vue holds all the main content in the root directory. Misleadingly, Vue also puts .vue files in the /src folder which could be seen as confusing to a vanillaJS veteran.

Angular and Stencil use typescript which makes a newbie shiver but can be learned fairly quickly with experience in JS. On the other hand, React and Vue run (frontend-wise) on JS.

### Duplicate / Overlapping Frameworks
Once you begin using each framework, you begin to notice a good amount of how they work overlaps with each other. We get this duplication since these frameworks are open to use and shape into any project anybody wants. This makes contributors adding the effective parts of other frameworks to the one your using.

### Easiest vs. Bias
Overall, Vue seems the easiest to use since it's not very complicated to learn and running with.

But who likes doing the easy one?

I've had experience in a past internship with Angular and although Vue wouldn't be tough to pick up if needed, if I had to choose a one to get a website going today, I'd be more confident in using Angular.

### GitHub
[Group Repo](https://github.com/IST-402-Group-1/IST402)
[My Fork with Boilerplate](https://github.com/mwagnerPSU/IST402/)
[Stencil Hello-World Boilerplate](https://github.com/hartjus/stencil-hello-world)
