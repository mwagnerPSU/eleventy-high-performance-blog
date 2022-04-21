---
title: Leveraging APIs for Microservices
description:
date: 2022-01-31
scheduled: 2022-01-31
tags:
  - programming
  - web components
layout: layouts/post.njk
---
The main idea of what were going to look at is using an IP locator API to define a location and display that location on google maps (internally and externally) and wire that location to a different, existing component.

### API Calls
Calling an API and receiving/storing its data is actually pretty simple as long as the API is designed correctly. In this case, we're going to look at an API called [free GIO IP](https://freegeoip.app/). Here we are able to get the general location (country, state, city, longitude, latitude) of an IP address. 

To make the call we are going to use a `fetch` function that will access a link we pass into it and return the JSON data that is received from that link.
![fetch example](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/skogvxelwvbpq37zxa2h.JPG)
In the code above we first start `fetch` and pass our link that looks like this `https://freegeoip.app/json/[ip address]`. `Fetch` then returns a response of the data grabbed from the API associated with the IP we passed in. The `.then` section is where we can go through that response and store the data in our program. Here, we are taking the longitude, latitude, city, and state and saving them to our existing properties.

### Displaying our Data with Google Maps
#### Internally
First, we're going to look at embedding a Google Map into our program using an `<iframe>`. Since we have the longitude and latitude (found earlier ^) of the location we want to display, we can use those in our `iframe` to embed the map.

That may have sounded difficult and hard to implement but it really comes down to two lines of code.
```
const url = `https://maps.google.com/maps?q=${this.lat},${this.long}&t=&z=15&ie=UTF8&iwloc=&output=embed`;
<iframe title="Where you are" src="${url}"></iframe>
```
Our `url` holds the link to google's mapping api and right after the `/maps?q=` in the link, we place in the latitude and longitude we have already found. Then, all we have left is to place that url into the `src` of our `<iframe>` and the map will display, embedded in our page.

For more info on using the Google Maps Platform check out their [developer page](https://developers.google.com/maps).

#### Externally
To create a link in our page that takes up to Google Maps with our desired location already in the view window is not too different from before. We can create a simple `<a>` tag and place the link for an external path with our long and lat we've received before.
```
<a href="https://www.google.com/maps/@${this.lat},${this.long},14z">
    See on Google
</a>
```
Here we've created a link that leads to google map's site with our long and lat coordinates and a zoom of 14 (`,14z`). 

### Wiring with an Existing Component
Let's say you want to use the data we received to utilize a different web component.

For this example, we'll look at a tag named `<wikipedia -query>` that will perform a wikipedia search and embed the page found into our site.
Wikipedia-query info: [Github](https://github.com/elmsln/lrnwebcomponents) [npmjs](https://www.npmjs.com/package/@lrnwebcomponents/wikipedia-query)

#### Set Up
We'll start by wiring the component into our program so we can implement the project. First, adding the package location to our `dependencies` in `package.json`.
![dependencies example](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/smv1jgolq5mftnl3el5e.png)
Then we'll run an `npm install` on our project to get all the needed assets to run `wikipedia-query`.

Once the install is finished, we want to add a "bare import" to our program file to be able to access the tag we just installed. A "bare import" is a convention where we let LitElement find what exact file we are looking for rather than specifically declaring one. This is important for improving the maintainability of our code since file locations and structures can change over time.

In this example, our "bare import" will look like this:
```
import '@lrnwebcomponents/wikipedia-query';
```
Notice we only specify the general area of what we are importing and not a specific file name.

#### Utilization
Now that we're all set up, we can do objectively the easiest part. Remember we want to use the `<wikipedia-query>` tag to display a wiki page of the location we received from our API earlier. 

To implement our `<wikipedia-query>` tag we pass our location into it's `search` property and let the tag do the rest of the work for us. 
```
//finding wiki based on city and state
<wikipedia-query search="${this.city}, ${this.state}"></wikipedia-query>

//finding wiki based on city
<wikipedia-query search="${this.city}"></wikipedia-query>

//finding wiki based on state
<wikipedia-query search="${this.state}"></wikipedia-query>
```

### Wrap It Up
The main point in this post is the effectiveness of the `fetch` function. We are able to set a call to any API, receive the JSON data, and use that data in any way we want.

Everything I talked about in this post is held in a small project that does more than is explained but is mostly centered around these topics.

Feel free to clone and play with the program on your own to see how it all plays together: [Github](https://github.com/mwagnerPSU/ip-project)

FYI: Everything discussed in this post is location in the LocationFromIP.js file in the src folder.