---
title: Web Component Progress
description: 
date: 2021-10-01
scheduled: 2021-10-01
tags:
  - programming
  - web components
layout: layouts/post.njk
---
We are currently making a reusable button web component in one of my classes. I'm going to run through the current status of the project.

When clicked the button will play a randomly picked audio clip from a selection of meme audios. Currently, the button has five properties (link, title, icon, disabled, play) that can be adjusted to personalize the button for yourself. When clicked the button plays an audio clip then opens the link in a new window. The button has functionality that will updated properties based on other properties. For example, is the play property is set to true, the button will also be disabled to prevent spamming. We also included various CSS properties to not only shape the button but change how it looks based on different states. For example, when the button is hovered over, the text and button color will change. Also, when the button is playing an audio clip, the button color will change as well.

Link to repo: https://github.com/IST-402-Group-1/KMBtn