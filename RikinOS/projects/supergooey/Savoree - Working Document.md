---
project: Savoree
status: Active
created: 2025-11-18
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

2025-11-18
---
Ok I didn't do much work today, other than organizing some notes here.

Next thing to work on:
- Let's start getting the flow of sharing a recipe to the app, parsing it, and saving it to our local database
- We will make a screen that will simply display the list of recipes we have.

2025-11-24
---
Let's make a quick work plan, take about 10 minutes

I've been working on Component Adoption, but i do need some team input there. Next steps for me here:
- Build out the Crit Document. Let's make this detailed, but also include a lot of visuals so that we can explore the problems, and everyone has an idea of what is being discussed
- We can create diagrams for how to Traverse a Component Hierachy, and how to count components for usage results

I can also take a pass at updating the Adoption score based on Francois suggetions, just to see what it would look like in that case. It's an option to look at.

Next up, I have TDS Options Panel, so I should probably setup a little document to discuss that:
- The current state of the component
- What was the problem with the previous iteration
- What did I specifically change
- What it looks like with dropdowns

I also wanted to take a pass at projects that I think would be good for design technologists, so doing a bit of a brainstorm

I did commit to updating the sample app as well, in terms of making it available via the Play Store, that's something I can start to look into (or maybe I just save that for the new year)

I can explore Compose Multiplatform for the IDS Documentation site in the future

I can see what other components haven't been migrated yet.

I can explore how we build components using Compose 1.9, (i.e Shadows etc)

I can build that Token Visualization tool
- See how token values propagate

I have an idea to build a tool that highlights what components come from IDS (with a debug border)

2025-11-25
---

Things we should do today

Build a POC of a different component adoption method

Create some diagrams to explain the different concepts

Explore Compose 1.9 Shadow APIs



