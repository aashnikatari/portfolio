---
layout: post
title: About
permalink: /about/
comments: true
---

## As a conversation Starter

Here are some places I have lived:

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
        {"flag": "0/01/Flag_of_California.svg", "greeting": "What's up?", "description": "California - forever"},
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

Here is a timeline of the important moments in my life:

- Feb 2009: Born in La Jolla, which makes sense since I love the beach!
- 2014: Started taking dance lessons, which I would later continue for over a decade
- Aug 2015: Started Elementary school at Stone Ranch
- March 2020: COVID-19 hit, and I graduated elementary school virtually
- Aug 2022: Started High School at Del Norte
- July 2024: Completed my Dance Rangapravesam, a 3-hour long solo dance performance, marking a dancers graduation from a dance student to a dancer
- April 2026: Earned my Girl Scout Gold Award

### Culture, Family, and Fun

- My parents were both born in India, and moved here after getting married.
- I have a brother, who is four years younger than me
- In my free time, I like to read, dance, and listen to music
- The gallery of pictures has some fun photos of my family and my culture.

<comment>
Gallery of Pics, scroll to the right for more!

1. Me and my childhood friend
2. Me and my friends at prom
3. After a dance performance
4. At Banff National Park in Canada
5. My brother
6. At a Girl Scout event
7. At a dance certificate event
8. Me and my mom
9. Me and my best friend
10. Me and my brother!!

</comment>
<div class="image-gallery">
  <img src="{{ '/assets/img/Me_n_Nandika.jpeg' | relative_url }}" alt="Image 1">
  <img src="{{ '/assets/img/Prom_ab_me.png' | relative_url }}" alt="Image 2">
  <img src="{{ '/assets/img/Kuchipudi_pose_ab_me.png' | relative_url }}" alt="Image 3">
  <img src="{{ '/assets/img/Banff_ab_me.png' | relative_url }}" alt="Image 4">
  <img src="{{ '/assets/img/Aahan_ab_me.png' | relative_url }}" alt="Image 5">
  <img src="{{ '/assets/img/ELGS_ab_me.png' | relative_url }}" alt="Image 6">
  <img src="{{ '/assets/img/Dance_grad_ab_me.png' | relative_url }}" alt="Image 7">
  <img src="{{ '/assets/img/Me_n_mom.png' | relative_url }}" alt="Image 8">
  <img src="{{ '/assets/img/Me_n_kae_ab_me.png' | relative_url }}" alt="Image 9">
  <img src="{{ '/assets/img/Me_n_Aahan_ab_me.png' | relative_url }}" alt="Image 10">
</div>
