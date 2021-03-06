---
layout: home
title: Communities Visualisation
permalink: /visualisation/communities
head_js:
    - "https://d3js.org/d3.v4.min.js"
    - "https://d3js.org/d3-scale-chromatic.v1.min.js"
    - "https://unpkg.com/force-graph"
body_js:
    - "/assets/js/communities.js"
---

<p class="text-center">Click on each coloured circle to explore community members. Click on a yellow circle to zoom out. Use the search bar below to find specific users.</p>

<svg id="circles" class="center"></svg>

<div class="text-center">
<p>Curious to find a specific account? Type <a>@username</a> into the search bar below (more than 10,000 follower accounts only.)<br/>
Don't know who to search? Try the <a>I'm feeling lucky</a> button.</p>

<input type="text" id="username" value="@username">
<button id="search" onclick="UserSearch(1)" >Search</button>
<button if="lucky"  onclick="LuckySearch(1)">I'm feeling lucky</button>
<p id="message"></p>
</div>

### About this visualisation

Nested communities of the 500 most influential users in the COP26 retweet network. To explore the visualisation, click on a circle to zoom in on that community. Clicking on a white circle after the visualisation has zoomed will reset the visualisation.

The visualisation uses Twitter data for the period prior to the conference (01/06/2021 to 20/10/2021). Each white circle corresponds to a username. White circles grouped together in a larger circle indicate that those users have been identified as a community. These communities may be stand-alone, or may be a sub-community in a larger community.

Communities are identified using the Infomap algorithm, an automated process which groups nodes based on how information flows through the directed edges of a network. This process is unsupervised, and groups nodes based on similarities in their interactions in the discussion relating to COP26 only - interactions outside of Twitter, or on Twitter which do not include the term “cop26”, do not impact the community detection algorithm. Note, for privacy and data protection reasons we have not labelled communities.

This visualisation was created in Javascript D3 based on <a href="https://github.com/holtzy/D3-graph-gallery" target="_blank">D3-graph-gallery</a>.