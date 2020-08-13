# Chrissy Cho's Mapping_Earthquakes
### Table of Contents
[ 1. Project Overview ](#desc)<br /> 
[ 2. Resources ](#resc)<br /> 
[ 3. Objectives ](#obj)<br /> 
[ 4. Summary ](#sum)<br /> 
[ 5. Challenge Overview ](#chal)<br /> 
[ 6. Challenge Summary ](#chalsum)<br /> 
[ 7. Final Outlook ](#find)<br />
[ 8. Issues and Solution ](#iss)<br />

<a name="desc"></a>
## Project Overview
In this module, we've learned..

<a name="resc"></a>
## Resources
- Data Source: [data.js](https://github.com/chrissycho/UFOs/blob/master/data.js), [app.js](https://github.com/chrissycho/UFOs/blob/master/static/js/app.js), [index.html](https://github.com/chrissycho/UFOs/blob/master/index.html), [style.css](https://github.com/chrissycho/UFOs/blob/master/static/css/style.css)
- Software: Bootstrap(CDN), CSS, HTML, JavaScript, Jupyter Notebook, VSCode

<a name="obj"></a>
## Objectives
- Create a branch from the master branch on GitHub.
- Add, commit, and push data to a GitHub branch.
- Merge a branch with the master branch on GitHub.
- Retrieve data from a GeoJSON file.
- Make API requests to a server to host geographical maps.
- Populate geographical maps with GeoJSON data using JavaScript and the Data-Driven Documents (D3) library.
- Add multiple map layers to geographical maps using Leaflet control plugins to add user interface - controls.
- Use JavaScript ES6 functions to add GeoJSON data, features, and interactivity to maps.
- Render maps on a local server.

<a name="sum"></a>
## Summary
We've completed displaying data that is stored in a JSON like array into a table by building a table with JavaScript. With JavaScript, we added interactive function to the table such as filtering. Then, we customized our web page with nasa image on the navigation bar background, font style and size, and background theme of the page. 

<a name="chal"></a>
## Challenge Overview
In this challenge, you will be finding a few key aspects of Oahu’s seasonal weather data. The investors want to ensure you’ve hit all of the key points before opening the surf shop.

### Challenge Objective
- Create, update, and deploy JavaScript functions to provide additional table filters.
- Update and deploy forEach (for loop) to loop through the filters and update them with user input.
- Update and populate the dynamic filters and table using JavaScript and HTML.

<a name="chalsum"></a>
## Challenge Summary
For the challenge, we now added more filters by date, city, state, country, and shape of UFO sighting information in the States. 

<a name="find"></a>
## Final Outlook
![](Pics/outlook.png)
This is what it looks like before filtering the data. 

![](Pics/filter_result.png)
This is after we filter by date and state. It returned a row of the table data with a date of 1/1/2010 and the state as "or."

<a name="iss"></a>
## Issues and Solution
Throughout the challenge, I faced several difficulties. First, I defined 5 filtering varibles using d3.select().property(). However, I realized this way won't be efficient if we are making 100+ filters in our page. Therefore, I learned "this" method of D3 library would work if it's listening for an event. What I didn't realize is that I still kept the command for JavaScript to listen to a button click instead of listening to the event itself. The very first command inside a function called updateFilters() for listening to an event was listening to a button click. Thus, the filters object wasn't saving the key-value pair of the user input. To fix this solution, the TA and I inspected the console and sources of the web page, making breakpoints of each line of the function (see below). 
![](Pics/issue.png)

There, we both realized that the D3 was listening to the button itself. On the JavaScript script, we changed the parameter of .selectAll() from "#filter-btn" to "input" which indicates the text box in our html code. We also changed the parameter for .on from "click" to "change." This way we would filter the table data accordingly to user inputs without a button. 