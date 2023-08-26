---
layout: post
title:  "Interactive Map with Python Folium and Google Maps API"
date:   2023-08-21 21:40:00 -0700
---

I have been travelling a lot so I created my own map to visualize all the cities and countries that I visited. Seeing the places on a map gives me a sense of fulfillment as it helps me reflect on my unique experiences. There are apps out there that help create such visualizations, but I wanted create a personalized, interactive and embeddable map.

I'll explain the process of creating the map in this post and I hope that it serves as a helpful guide for anyone who wants to create a map or wants to work on similar projects.

## Summary
The map consists of two layers: a heatmap and a circle marker layer. The heatmap visualizes the frequency I have travelled to each country with a linear colour scale. The circle marker layer creates circular markers on the map with a number indicating the number of locations in its cluster. By clicking on a circle marker, the map zooms in on that area and eventually you can see a single dot on the exact location. There is also both a light and dark mode for increased accessibility. 

I wrote a Python script to process the list of locations and dates from a Google Sheet, geocode using Google Maps API, and finally create the interactive leaflet map using Folium. I used Google Cloud to host the script and run it on a schedule so that the map is updated automatically when I add new locations to the Google Sheet.

## Setting Up in Google Cloud
I used Google cloud console to ...

## The Data
I used Google Sheets to keep a list of locations. This part was really easy. I just had to create a new sheet and add columns for the location, country, and date. Using the Google Maps API means that I don't need to specify beyond the location name and country. I chose to have cities as my location entries, but this would also work with whatever you might enter into Google Maps searches, such as tourist destination names.

<img title="Spreadsheet Columns" alt="Spreadsheet with columns labeled Location, Country, Date" src="/assets/images/locations_sheet_layout.png">

## The Code
I used the Google Maps API to create a map with markers for each location. I also added a heatmap layer to visualize the frequency of travel to each country.
'''
'''

## The Result
The output is html that I used to embed the map on my website.
<img title="Resulting Map" alt="Screenshot of map" src="/assets/images/ccmap_screenshot.png">


There are a few things that I want to change about this map. The main issue being the legend for the linear colour map layer. I wish the scale were continous, since a heatmap by design only gives an approximate visualization of frequency, so there is no need for such exact numbers. I would also hide the legend when the colour map layer is deselected. Another thing I would play around with is the default center position and zoom on the map.

When my friends ask me about my travels, this map has proven to be a great way to show them where I've been. I hope to continue adding to this map as I explore more of the world.

Until next time,

Iris