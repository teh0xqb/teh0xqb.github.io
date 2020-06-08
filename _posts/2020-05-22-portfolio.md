---
layout: post
title:  "Portfolio Work"
image: 'coming soon'
date:   2020-05-22 00:16:00
tags:
- software
description: 'See for yourself!'
categories:
- engineering
serie: software
---

Everyone is likely aware of the recent events that have shaken the world. I, for one,
was ready for a career change. When the companies I interviewed for froze their
positions, due to the economic uncertainity the pandemic brought, I ended up
with no work on an incredible sabbatical to discover new technologies and share some time
with my new family. I ended up building and deploying these demos to showcase what I can accomplish 
with JavaScript and CSS on the browser.

## Demos

All of these applications are embedded with iframes, except for the windrose,
which is a screenshot. Try them out!

Ps. I tried these out in both recent versions of Chrome and Firefox, both on Linux
and Windows. Some might even work on the MS Edge browser.
I have not tried these on OSX or safari.

### Meet The Pokedex

I was given barebones wireframes and asked to develop a pokedex using <https://pokeapi.co/>{:target="_blank"}.
It was required to use `VueJs`. It was my first time using this library, but
that wont stop me on delivering an organized and responsive browser app!
Link to standalone [Pokedex here](https://teh0xqb.com:444){:target="_blank"}.

<div class="demo-container">
    <iframe class="demo" src="https://teh0xqb.com:444" title="Pokedex" width="100%"></iframe> 
</div>

<br />

#### Some notes on what I was going for

The tiles on the grid are constrianed to a [1:1 ratio](https://css-tricks.com/aspect-ratio-boxes/){:target="_blank"}.
These resize to fit in the grid and, if an additional tile can fit its contents
on a new column, columns are added automagically.

The application is fully responsive- try it out under several desktop sizes. I used
[flex](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox){:target="_blank"}
and [grid](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/Basic_Concepts_of_Grid_Layout){:target="_blank"}
layout methods, and `em` values, in order for it to work and resize appropriatedly.

The data fetching logic is contained within one module. Anytime a component
fetches data the application is aware of it. With this awareness of all external calls,
we track an app-level loading state. The pokedex's UI, then, includes an interesting 
app-level loading animation. It is pretty inconspicuous- serves as the 
bottom border for the pokedex header. Users should mostly notice it when 
exploring a pokemon type the application has not retrieved before.
That's the point: on slow connections, users need to await with a loading animation.
On faster internet connections, users don't need to notice it. I prefer this, when possible,
to immediately replacing content of previous call. Replacing content with a loading
animation usually causes a flash of an animation on fast connections.

The `simplebar` library is used for OS-**in**dependent scrollbars. OS-dependent scrollbars
usually cause inconsistencies in styling and experience, especially on OSX and mobile!

---

### Meet the Pivot Table

React demo page with a Pivot Table component. The table receives linear data and 
row/column dimension configuration. Suppports multiple dimensions.
Aggreages data and sums sales. I did not use `simplebar` like on the previous example,
so the layout mileage may vary when using different OS/browser/window and size combinations.

<div class="demo-container">
    <iframe class="demo" src="https://teh0xqb.com/pivot-table" title="PivotTable" width="100%"></iframe>
</div>

<br />

#### Details 

This was a tricky undertaking for just demo purposes. I believe it is the most
complex demo anyone has requested of me. The main three components:
The common container that holds all the table body, the left panel (row dimensions)
component, and the right panel (column dimensions + data) component. This effort was 
definitely timeboxed, and I plan to update it (eg separate column 
dimension from data component) as time allows. You'll most likely notice that
the OS scrollbar breaks the layout alignment.

Run standalone application [here](https://teh0xqb.com/pivot-table){:target="_blank"}.

---

### Meet the Cassandra Ring

I built this in 2015, and did not use any framework or view library.
Not even jQuery! Just javascript, `D3js`, and `webpack` in order to bundle the project.

<div class="demo-container">
    <iframe class="demo" src="https://teh0xqb.com/c-ring" title="OpsRing" width="100%"></iframe>
</div>

<br />

#### The idea is

Given a list of tokens that can range from 0 to *a very big number*, assign a node (circle)
into the Cassandra ring view. Given that the `bigint` type was not yet introduced in `js`,
I used a library that implemented big numbers.

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

This is a simple react registration form. It does what it needs to do:
It contains controlled input elements, validates on submit using the HTML Contraint API,
and either shows the errors or navigates to a success page. I did not include labels
nor fancy animations to move placeholders as form input labels, but with more time
that was certainly possible.

You'll notice that this time around I decided to provide positive reinforcement on pre-submit form field validation. That is,
forms are not red if they are bad, but green if they are A-Ok. This also utilizies
`react-router-dom` for history-enabled navigation (think back button, url routing).

Run standalone [here](https://teh0xqb.com:446){:target="_blank"}.
Source [here](https://github.com/teh0xqb/availity-review/blob/master/registration-ui/src/Register.js){:target="_blank"}.

---

### Meet the WindRose

Ended up building this while working with D3js, back in 2014.

![windrose](/assets/img/windrose-zoom.png)

#### Details

I am not embedding the running application, as this is the oldest demo I have.
The code is most likely not great. I was still a young Padawan.

---

### Meet the ClojureScript + Material-UI Demo App

Utilizes `cljs-http` to use `core.async` channels for http calls. Uses 
[material-ui](https://v4-9-14.material-ui.com/){:target="_blank"} components,
although this wasn't exactly necessary. I just wanted to try using npm libraries
within the clojurescript ecosystem.

<div class="demo-container">
    <iframe class="demo" src="https://teh0xqb.com/trials" title="Trials cljs UI" width="100%"></iframe>
</div>

<br />

#### This is a simpler one

API calls to listings of a resource type, which are displayed on
a table. An input field to filter table rows. Clicking each row opens up
a dialog to edit a resource. The backend is no longer up, so you won't be able to
post the resource upon editing. Loading animations and error handling on edit
form included.

The main win is: ClojureScript + Reagent is an incredible combination of tools
to build user interfaces. It is different than javascript in the sense that the UI
is built using data and code- no new dsl (directives, JSX) nor data structure constraints.
Contrast that with javascript, where as an example, React has to mix a JSX template
xml pseudo-dsl with javascript logic and valid js interpolation within the template.
This post won't deep dive on how these statements are true, but there are some 
good blogs out there that already explain why the Clojure/Script combo 
(and Reagent!) are incredible technologies. Google it!

Run standalone [here](https://teh0xqb.com/trials){:target="_blank"}. Source [here](https://github.com/teh0xqb/re-trials){:target="_blank"}.
