---
project: Savoree
status: Active
created: 2025-11-19
---

## Overview

Savoree is an app that saves recipe reels from Instagram. Users can find a reel on Instagram, share it to Savoree, and the app will store it locally and display the recipe details and instructions in a cleaner, more readable format.

We want to build something simple, but really fun and delightful. Smooth + intentional animations, playfulness, the works. That is why the scope of the feature set should be very small.

## Key Features

- Share Instagram recipe reels directly to Savoree
- Recipe Organization + Offline Use
- Fun Recipe Display

## Blueprints

*Android App*
Core Screens
- Analyzing Recipe
- Recipe List / Grid
- Recipe Display
- Settings

*Instagram Data Source*
Apify is our main API
- it's built use web crawling / scraping to grab some data
- should probably be built in a way where we can replace / fallback to our on solution

*Recipe Analysis*
Part of analyzing a recipe will require parsing the caption and converting that into a human readable list of ingredients.




---

## Work Log

*2025-11-18*

Ok I didn't do much work today, other than organizing some notes here.

Next thing to work on:
- Let's start getting the flow of sharing a recipe to the app, parsing it, and saving it to our local database
- We will make a screen that will simply display the list of recipes we have.