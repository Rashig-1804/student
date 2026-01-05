---
layout: post
title: About
permalink: /about/
comments: true
---

## As a conversation Starter

Here are some places I have lived.

<comment>
Flags are made using Wikipedia images
</comment>

<style>
    /* Style looks pretty compact, 
       - grid-container and grid-item are referenced the code 
    */
    .grid-container {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(150px, 1fr)); /* Dynamic columns */
        gap: 10px;
    }
    .grid-item {
        text-align: center;
    }
    .grid-item img {
        width: 100%;
        height: 100px; /* Fixed height for uniformity */
        object-fit: contain; /* Ensure the image fits within the fixed height */
    }
    .grid-item p {
        margin: 5px 0; /* Add some margin for spacing */
    }

    .image-gallery {
        display: flex;
        flex-wrap: nowrap;
        overflow-x: auto;
        gap: 10px;
        }

    .image-gallery img {
        max-height: 150px;
        object-fit: cover;
        border-radius: 5px;
    }
</style>

<!-- This grid_container class is used by CSS styling and the id is used by JavaScript connection -->
<div class="grid-container" id="grid_container">
    <!-- content will be added here by JavaScript -->
</div>

<script>
    // 1. Make a connection to the HTML container defined in the HTML div
    var container = document.getElementById("grid_container"); // This container connects to the HTML div

    // 2. Define a JavaScript object for our http source and our data rows for the Living in the World grid
    var http_source = "https://upload.wikimedia.org/wikipedia/commons/";
    var living_in_the_world = [
        {"flag": "0/01/Flag_of_California.svg", "greeting": "Hey", "description": "California - forever"},
        {"flag": "4/41/Flag_of_India.svg", "greeting": "Namaste", "description": "India - As a baby"},
    ];

    // 3a. Consider how to update style count for size of container
    // The grid-template-columns has been defined as dynamic with auto-fill and minmax

    // 3b. Build grid items inside of our container for each row of data
    for (const location of living_in_the_world) {
        // Create a "div" with "class grid-item" for each row
        var gridItem = document.createElement("div");
        gridItem.className = "grid-item";  // This class name connects the gridItem to the CSS style elements
        // Add "img" HTML tag for the flag
        var img = document.createElement("img");
        img.src = http_source + location.flag; // concatenate the source and flag
        img.alt = location.flag + " Flag"; // add alt text for accessibility

        // Add "p" HTML tag for the description
        var description = document.createElement("p");
        description.textContent = location.description; // extract the description

        // Add "p" HTML tag for the greeting
        var greeting = document.createElement("p");
        greeting.textContent = location.greeting;  // extract the greeting

        // Append img and p HTML tags to the grid item DIV
        gridItem.appendChild(img);
        gridItem.appendChild(description);
        gridItem.appendChild(greeting);

        // Append the grid item DIV to the container DIV
        container.appendChild(gridItem);
    }
</script>

### Journey through Life

Here is what I did at those places

- 👶 Born in Patna, India in 2011
- 🌅 Moved to sunny San Diego as a baby
- 🎓 Attended Monterey Ridge Elementary School 
- 🎓 Graduated from Oak Valley Middle School '25
- 🎓 Currently attending Del Norte High School


### Culture, Family, and Fun

Everything for me, as for many others, revolves around family and culture!
- The gallery of pics has some of my family, fun, and cultural memories!
- There is my mom, dad, and my elder sister, Ananya! 
- I love dancing
- Below are some pics from our fun New York Trip, my dance performance, Diwali, and my middle school promotion!

<comment>
Gallery of Pics, scroll to the right for more ...
</comment>

<div class="image-gallery">
  <img src="{{site.baseurl}}/images/about/family.jpg" alt="Image 1">
  <img src="{{site.baseurl}}/images/about/new_york.JPG" alt="Image 2">
  <img src="{{site.baseurl}}/images/about/dance_1.JPG" alt="Image 3">
  <img src="{{site.baseurl}}/images/about/mom.jpg" alt="Image 4">
</div>

### Fun Facts!
- Hobbies: Playing the piano and learning Odissi Dance
- Favorite Ice Cream Flavor: Cookies and Cream
- Favorite Food: Alfredo Pasta 
- Favorite Color: Navy blue

<div class="favorite_things">
  <img src="{{site.baseurl}}/images/alfredo_pasta.jpg" style="width: 30%;">
  <img src="{{site.baseurl}}/images/cookies_cream.jpg" style="width: 30%;">
</div>


### Fun Facts
<div id="grid_container"></div>

<script>
var outputElement = document.getElementById("grid_container");
// Clear the output
outputElement.innerHTML = '';

// Data array
const living_in_the_world = [
  {flag: "https://upload.wikimedia.org/wikipedia/commons/thumb/4/4c/HK_food_Appolo_%E9%9B%AA%E7%B3%95_ice_cream_with_black_cookies_n_white_cream_May_2021_SS2_01.jpg/500px-HK_food_Appolo_%E9%9B%AA%E7%B3%95_ice_cream_with_black_cookies_n_white_cream_May_2021_SS2_01.jpg?20210512160940", greeting: "Favorite Ice Cream", description: "Cookies and Cream"},
  {flag: "https://upload.wikimedia.org/wikipedia/commons/thumb/1/1b/Shrimp_Fettucini_Alfredo.jpg/640px-Shrimp_Fettucini_Alfredo.jpg", greeting: "Favorite Food", description: "Alfredo Pasta"},
];


// Style the container 
container.style.border = '2px solid';
container.style.padding = '10px';

// Grid specific styles
container.style.display = 'grid';
container.style.gridTemplateColumns = 'repeat(auto-fill, minmax(150px, 1fr))';
container.style.gap = '10px';

// Loop through data and create grid items
for (const location of living_in_the_world) {
  // Create grid item
  const gridItem = document.createElement('div');
  gridItem.style.textAlign = 'center';
  
  // Create a flag image
  const img = document.createElement('img');
  img.src = location.flag;
  img.alt = location.description + ' Flag';
  img.style.width = '100%';
  img.style.height = '100px';
  img.style.objectFit = 'contain';
  
  // Create a description
  const description = document.createElement('p');
  description.textContent = location.description;
  description.style.margin = '5px 0';
  description.style.fontWeight = 'bold';
  
  // Create a greeting
  const greeting = document.createElement('p');
  greeting.textContent = location.greeting;
  greeting.style.margin = '5px 0';
  greeting.style.fontStyle = 'italic';
  greeting.style.opacity = '0.7';
  
  // Add all elements to grid item
  gridItem.appendChild(img);
  gridItem.appendChild(description);
  gridItem.appendChild(greeting);
  
  // Add grid item to container
  container.appendChild(gridItem);
}

// Add containter to output 
outputElement.appendChild(container);
</script>