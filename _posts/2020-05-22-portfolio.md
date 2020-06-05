---
layout: post
title:  "Portfolio Work"
image: 'coming soon'
date:   2015-05-22 00:16:00
tags:
- software
description: 'See for yourself!'
categories:
- engineering
serie: software
---

Everyone is aware of the recent events that have shaken the world. I, for one,
was ready for a career change. When the companies I interviewed for froze their
positions, due to the economic uncertainity the pandemic brought, I ended up
with no work on an incredible pseudo-sabbatical to discover new technologies and share some time
with my new family.

I had to go through one or two interview processess this summer. Even though the
roles weren't an exact fit with my skills and next steps, I ended up building these
demos to showcase what I can accomplish with JavaScript and CSS on the browser.

Here's the result of my exercise of hosting and collecting these demo applications.
I have also included relevant previous work that may have landed me a job.

## Demos

All of these applications are embedded with iframes, except for the windrose,
which is a screenshot. Try them out!

### Meet The Pokedex

I was given barebones wireframes and asked to develop a pokedex using <https://pokeapi.co/>{:target="_blank"}.
It was required to use `VueJs`. It was my first time using this library/framework, but
that wont stop me on delivering and organized and responsive browser app!
Link to standalone [Pokedex here](https://teh0xqb.com:444){:target="_blank"}.

<div class="demo-container">
    <iframe class="demo" src="https://teh0xqb.com:444" title="Pokedex" width="100%"></iframe> 
</div>

<br />

#### Some notes on what I was going for

The data fetching logic is contained within one module. Anytime a component
fetches data the application is aware of it. Additionally, the main module returns
the promise just in case the caller wishes to handle it manually
(say local animation, fallbacks, error handling).

Using this app-level "flag" (loading), the pokedex has an interesting app-level
loading animation. It is pretty inconspicuous- serves as the border for the pokedex header.
Users should mostly notice it when exploring a pokemon type the application has not retrieved before.
That's the point: on slow connections, users should  see the loading animation.
On faster internet connections, you don't really need to notice it (nor have previous
content immediately replaced or yanky flashes of animations from requests that took a small amount of time).

This application is fully responsive- try it out under several browser sizes. I used
flex and grid layout methods, and `em` values, in order for it to work and resize appropriatedly.
It is not exactly optimized for mobile, but any desktop window will do.

I used the `simplebar` library for OS-**in**dependent scrollbars. OS-dependent scrollbars
usually cause inconsistencies in styling and experience, especially on mobile!

---

### Meet the Pivot Table

React demo page with a Pivot Table component. The table receives linear data and 
row/column dimension configuration. Suppports multiple dimensions.
Aggreages data and sums sales. I did not use `simplebar` like on the previous example,
so your mileage may vary when using different OS/browser/window and size combinations.

<div class="demo-container">
    <iframe class="demo" src="https://teh0xqb.com/pivot-table" title="PivotTable" width="100%"></iframe>
</div>

<br />

#### Details 

This was a tricky undertaking for just demo purposes. I believe it is the most
complex demo anyone has requested of me. The main three components:
The common container that holds all the table body, the left panel (row dimensions)
component, and the right panel (column dimensions + data) component. This effort was 
definitely time-constrained, and I plan to update it (eg separate column 
dimension from data component) as time allows. You'll notice the scrollbar breaks
layout a little bit.

Run standalone application [here](https://teh0xqb.com/pivot-table){:target="_blank"}.

---

### Meet the OpsRing

I built this in 2015. I might have outdone myself here: I did not use any framework or
view library. Not even jQuery! Just javascript, D3js, and webpack in order to 
bundle the project.

<div class="demo-container">
    <iframe class="demo" src="https://teh0xqb.com/c-ring" title="OpsRing" width="100%"></iframe>
</div>

<br />

#### The idea is

Given many tokens from 0 to a very big number, assign the node (circle)
into the Cassandra ring view. Given that the `bigint` type was not yet introduced,
I used a library that implemented big numbers, since the tokens represented by the rings
were larger than what javascript could safely represent.

Run standalone application [here](https://teh0xqb.com/c-ring){:target="_blank"}.
See source code [here](https://github.com/teh0xqb/c-ring){:target="_blank"}.

---

### Meet the React Registration Page

Includes the simplest validation mechanism with React using the HTML Constraint Validation API.

<div class="demo-container">
    <iframe class="demo" src="https://teh0xqb.com:446" title="Registration UI" width="100%"></iframe>
</div>

<br />

#### Notes

This is a really simple react-backed registration form. It does what it needs to do:
It contains controlled input elements, validates on submit using the HTML Contraint API,
and either shows the errors or navigates to a success page. I did not include labels
nor fancy animations to move placeholders as form input labels, but with more time
that was certainly possible.

You'll notice that this time around I decided to provide positive reinforcement 
(long live the field of psychology) on pre-submit form field validation. That is,
forms are not red if they are bad, but green if they are A-Ok.

Of course, on a production project the user should be able to receive information
on what the requirement is in order to fill the field correctly, without having to wait
for submites or color hints. Out of scope for this demo.

The theme for colors and gradient were just taken from a the company theme that
asked me to build this demo.

---

### Meet the WindRose

Ended up building this While working with D3js, back in 2014.

![windrose](/assets/img/windrose-zoom.png)

#### Details

I am not embedding the running application, as this is the oldest demo I have.
The code is most likely not great. I was still a young Padawan.

---

### Meet the ClojureScript + Material-UI Demo App

Utilizes cljs-http to use core.async channels for http calls. Uses [material-ui](https://v4-9-14.material-ui.com/){:target="_blank"}
components, although this wasn't exactly necessary. I wanted to test npm libraries
within the clojurescript ecosystem.

<div class="demo-container">
    <iframe class="demo" src="https://teh0xqb.com/trials" title="Trials cljs UI" width="100%"></iframe>
</div>

<br />

#### This is a simpler one

API calls to listings of a resource type, which are displayed on
a table. A filter field to filter the table rows. Clicking each row opens up
a dialog to edit the resource. The backend is no longer up, so you won't be able to
post the resource upon editing. Loading animations and error handling on edit
form included. I did the original version in about an hour, so there's not a lot to show here.

The main win is: ClojureScript + Reagent is an incredible combination of tools
to build user interfaces [UI]. It is different than javascript in the sense that the UI
is built using data and code alone (no weird syntax no data structure constraints).
Contrast that with javascript, where as an example, React has to mix a JSX template
xml pseudo-dsl with javascript logic and interpolate within the template. These statements
are not fair in this context, I know. This post won't deep dive on how these
statements are true, but there are some good blogs out there that already explain
why the Clojure/Script combo (and Reagent!) are incredible technologies. Google it!

