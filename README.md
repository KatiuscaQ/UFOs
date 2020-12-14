# UFOs

## Overview of Project: 
The purpose of this project is to assist Dana on providing a more in-depth analysis of UFO sightings by allowing users to filter for multiple criteria at the same time.

## Results: 
The users of this new webpage can filter their search by the criteria they feel important to know or by the criteria they already have knowledge of.
On the bottom left side of the webpage the “Filter Search” container can be found, just next to the table with all the information about the UFO sightings.

![](https://github.com/KatiuscaQ/UFOs/blob/main/Resources/Filter_search.PNG)

The users could choose to search by five (5) criteria or by multiple criteria at the same time. Examples as follow:

### Search by date:
The user can input a date following the placeholder example with the format “m/d/year”. When the user input “1/3/2010” and press “enter” the table will only show the information that matches that specific date, in this case it shows one result.

![](https://github.com/KatiuscaQ/UFOs/blob/main/Resources/search_by_date.PNG)

### Search by city:
The user can input a city name inside the city-search box, and after pressing enter the table will display only the results with said city. In the following example the user input “el cajon” and five results are displayed.

![](https://github.com/KatiuscaQ/UFOs/blob/main/Resources/search_by_city.PNG)

### Search by state:
The user can search by state using the standard “two-letter state abbreviation”. When the user enters “or” (for Oregon) the table is filtered, and the display shows three results.

![](https://github.com/KatiuscaQ/UFOs/blob/main/Resources/search_by_state.PNG)

### Search by country:
The user can search by country using the same “two-letter abbreviation” standard but this time for countries. If the user wants to search for the sightings in Canada, he/she would have to write “ca” in the country box. In the following image this search is performed, and two results are shown.

![](https://github.com/KatiuscaQ/UFOs/blob/main/Resources/search_by_country.PNG)

### Search by shape:
When the user is interested in finding sightings base on the shape they were seen, the “Enter a shape” input box comes handy. In the example the shape “fireball” is input, and seven results were displayed.

![](https://github.com/KatiuscaQ/UFOs/blob/main/Resources/search_by_shape.PNG)

## Summary: 
The webpage has been updated to perform particularly useful searches from a user point of view, but at the same time there are some drawbacks that could be frustrating when using the webpage. Those drawbacks are as follow:
1.	The page must be reset every time the user needs to change the search, or the user must remove every input one by one to start “clean”.
2.	The input boxes are case sensitive, this means if the user writes “El Cajon” instead of “el cajon” the search will throw not results.
3.	The following is not a drawback but more of a confirmation that the user might need, and it is that there is no message that confirms to the user that his/her search cannot be found on the table, instead there is a blank table.

The recommendation in order to have a more user-friendly webpage are as follow (all recommendations were applied to the webpage):

1.	Create a “Reset Search” button. From a user point of view this change makes the webpage more advance and fun to play with.

On index.html the following code was add to make the button part of the "Filter search"
```html
<li  class="list-group-item bg-dark text-center">
      <button id="reset" type="button" class="btn btn-dark btn-lg">Reset Search</button>
</li>
```
Meanwhile on the app.js document, the button brought "to life" by making a function and by adding an event listener, both shown as follow:
```html
 // Recommendation #1 "Reset Search button"
  function resetFilters() {
    location.reload();
  };
// 2. Attach an event to listen for changes to each filter
  d3.select("#reset").on("click", resetFilters);
```
2.	Force the code to make all inputs lower case. Even if the user is writing all the text capitalized the input box will make the text lower-case and the most important part it will read it as lower-case. For this code to work a function was made on app.js and said function was called on index.html.
```html
  // Recommendation #2 To convert to lower case even if writing is ALL CAPITAL
  function forceLower(strInput) {
    strInput.value = strInput.value.toLowerCase();
  }
```

![](https://github.com/KatiuscaQ/UFOs/blob/main/Resources/Calling-the-forceLower-function-on-input-in-HTML.PNG)

3.	Add a text confirming to the user that the criteria inputted was not found. In the example below "Los Angeles" was inputted and since there is not information about sightings in this city the message of "Sorry, search not found!" is shown to the user.

![](https://github.com/KatiuscaQ/UFOs/blob/main/Resources/notfound.PNG)


