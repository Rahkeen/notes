---
created: 2025-10-19
---

2025:11:19
---

Quick Plan

*Followups for Android Component Adoption*
- Cleaning up Data Modeling
- Can I bring it into ICAPP or IDS repo?
- Can I run it as a gradle script?

*TDS Options Panel*
- Merge main branch, do design pass
- Notify team
- Talk to Hosh'ki about Storybook + Component updates

*Projects I want to work on?*
- Token Explorer for Android
- Working with Rive
- Compose for Web (for Doc Site)
- Improving Sample App
	- Beta for Plastore
	- More demonstrations

*Design Technologist Manifesto*
Spend some time really thinking about what this role is to you? What types of things do you want to work on.

**For Next Time**
- Put up diff for IDS repo adding Component Adoption script
- FIll out Crit Doc for TDS.Option Panel
- Project Ideas + Manifesto
- Compose for Web + IDS Test


2025:11:20
---

Quick Plan

*Wrap up as much of IDS Component Adoption*
- Get Review Feedback
- Break things out for easy testability

2025:11:21
---

Claude Code Talk

USE PLAN MODE
Esc, NOT Ctrl-C


Memory / Notes
`_claude folder + global gitignore`
DANCE Framework

Quick Plan

*Component Adoption*
- Let's follow up with Francois on the counting mechanism
- See if we can come to terms on what the counting logic should be
- See if we can land the PR today

*TDS Options Panel*

2025-12-2
---

I just had a pretty fruitful discussion, so turns out, we are gonna be just doing our own thing per platform, sounds good.

Going back to the drawing board a little bit, we now have a bit of a new approach:

1. Index the IDS codebase, find all the components from IDS, add them to a map
	1. Ignore any private or internal components
	2. Make sure they are UI
	3. Can keep track of what module the component is from
	4. ```
	   name
	   package
	   module
	   ```
2. Parse the selected codebase, get all the Kotlin Source Files as KtFiles
	1. Extract the declared component functions, per module
3. Construct the call graph by visiting each declared function for any call expressions that might also be called component functions

2025-12-3
---

I'm still working on Component Adoption things

Right now I am indexing the IDS codebase to make it easy to lookup IDS components when searching another codebase.

Working on Indexing Components right now

We may have to clean up how modules paths are setup, but for now it's prolly ok to hardcode them.

ALRIGHT

I Clauded up a solution, but tomorrow I really need to read through it and clean it up
Then I need to write some test cases to test that bad boy out.

2025-12-4
---

Alright quick plan + todoist sesh

Let's review + cleanup adoption metrics code
Let's add reporting + module level scores
Let's add tests

 I'm cleaning up the call graph right now. First thing I'm seeing is that the data classes can be reduced a bit.

WHAT EXACTLY SHOULD BUILDING THE CALL GRAPH ENTAIL

At this point we have a list of components, an index of IDS components

List of Components to Process
IDS Lookup Table


I noticed that CallGraphBuilder needed a parser for some reason, but that likely is just a remnant of some gross code gen

There is some more cleanup we can do with ComponentNode, looks like the type and the associated info can be grouped into a compound data class of sorts, maybe a sealed class

Let's inject dependencies into CallGraphBuilder, store those as members
and reference those members with different funcitons
- build step, create inital graph
- merge step, merge same name nodes as best we can
- filter step, filter out noise based on externally passed filters

I also want to make sure I hone in on the linking step for component nodes and children and such. Right now the call graph object is a little wonky it feels like. There's probably an opportunity to do a pass there and clean that up as well. And yeah, see if we can make that a little more functional and more of like a data class rather than a mutable structure.

Let's analyze CallGraph data structure

Alright resolving a call expression to either
- a matching Project Node
- a matching IDS node
- creating a new node

2025-12-5
---

Ok, new day, let's think about the process end to end

*Indexing IDS Component*
Read IDS source files, find components, stick them into a map, keyed by unique name

As I am indexing components and finding their called functions, I notices I don't always get the attributed import, if it's importing the class and that class calls a member function.

Last Score we got: Total Score: 62.2%

2025-12-10
---

Things I needs to do:
- Restart Button Expy
- Followup on Adoption Diff
- SelectionBordered renaming

What are some things I can pick up today:
- Look at the Banana Sheet, create a simple prototype using our API
- Re-pick up TDS Selection Panel, see if I can get some feedback


Some things are clarifying after talking to Abhay
- I want to showcase my skills, and build cool experiences
- I want to explore building things with Rive, Spline, etc and finding ways to bring that into the product
- If there is an opportunity to help built a tool or prototype, let's get after it.

Tomorrow if I wake up early!
- Start taking Rive 101

2025-12-11
---

Abhays Review

Abhay's Core Strengths:

Abhay is a strong communicator. When working with him, I've noticed he always asks for clarification in ambiguious scenarios. He is also very proactive in setting up lines of communication, bring people in and sharing his work frequently.

Abhay is also strong in Domain Expertise. I worked with him on the Caper Android Sandbox and he showed a high level of technical understanding. It made working with him a breeze and we were able to deliver high quality output together.

Abhay's Opportunities to Grow:

Mostly I just want him to be able to shine his skillset more. I think he is very eager to help build prototypes and tools that help unlock designers, and specifically the Caper team to help them test out flows, and get higher quality feedback. I think his mix of technical knowledge, speed of execution, and eagerness to explore the unknown are an amazing combo, so I just want to see him advocate and explore more opportunities that let him showcase his ability.

Anything else:

Aside from strictly his strong abilities, Abhay is a fantastic person and partner to work with. He always has a good attitude no matter the situation, and personally it's been great having someone to share stories with, bounce ideas off of, and just chat with in general. It is always a positive and uplifting experience.

**Today is Rive Day**

Let's stop overthinking and start learning something new

[[Learning Rive]]

**For Tomorrow**

If I wake up early, continue doing some rive learning
Make a list of small projects to work on as well
Decide on continuing your side app project

2025-12-12
---

All right, quick little brainstorm here. What do I want to do with the time that I have left for getting, you know, thinking about the type of work I want to do here at Instacart. And there's a couple things I want to explore in general. All right, I want to explore motion design tools, tools like Rive, right? I want to get really good at like motion design type experiences. Okay, like I want to know that in and out and I want to be able to create like motion graphics or things that like if we want to demonstrate an idea like Rive could be a good opportunity there. So I want to explore Rive at the very least. I want to explore tool explain for 3D and integrating 3D into mobile applications. But I also want to work with native code and build native prototypes, right? So I want that to also be a thing. And so I think a lot of times my head's kind of split on like, hey, like I have some bandwidth, like what should I explore? And right now, like I've been, I've been, I feel like I'm being pulled towards Rive. But I also have these courses for like getting into React and building whimsical, cool, React based, web based like interaction design experiences. Function design is also what I'm like referring to here. So yeah, there's just a lot going on in my brain. And I feel like I need to like vomit it out and come up with like a list of little mini projects that I can explore. And you know, gate my exploration with projects that I want to build. So for example, if I want to learn Rive, like I should have an example project in Rive that I want to build some sort of design thing. Yeah, let's start there. I need to go up and poop.

2025-12-14
---

Things to think about tomorrow:
1. Followup on Component Adoption things
2. Prioritize restarting the experiment
3. Build Banana Picker Prototype
4. Come up with some Rive Experiments for IDS
5. Come up with some prototyping projects (make them explicit)
6. Make a project plan that includes these


2025-12-17
---

 Okay, so I am just talking about the ideal flow here for this link rule. So if I run it for a particular module, essentially, what I want to do is I want to capture all of the functions that are in its dependency path. Right? So any declared function there. And then from those declared functions, I now have a list of functions here. And I guess, you know, maybe instead of doing that, maybe what I would do is I would find the declared functions in the particular module that I care about. Right? Right. And in that module, I'm going to resolve any function that I see. Right. And so as I go through declared functions, I go through called expressions, I check if they are methods and if they are, I resolve them. Okay. And when I resolve them, I can get their full qualified name. And then I can also potentially visit that function. Right. And so that's when we can do this recursive structure here. So I'm curious if we can like just get that proof of concept out of the way first.

1. POC function traversal using a lint rule

2025-12-18
---

I'm a bit frustrated and in a rut, so I'm gonna be spending my time learning. And I just wanna get started, so let's start.

In general, I'm interested in interaction design, so I'm looking at devouring details.

Then maybe I can go more into react with joy of react

There is also threejs journey, getting more into 3D

then we just got svg.info, a course on everything svg


For Tomorrow:

Investigate what things are tracked as roots
Investigate what functions are being called


2025-12-19
---

 Alright, let's just remind ourselves what we should be doing here. There are obviously going to be some errors here in the logic in terms of identifying call expressions as functions and mapping them to functions that exist in the project. So, I think the first thing we need to do is just anytime we hit a case where we don't know where the function belongs, we track that in our output.

 We can take a pass at seeing what issues we can resolve. But honestly I think we need to be okay with a little bit of error. We give up a little bit of accuracy for something that's quick and something that works for the time being.

2026-01-6
---

2026-01-21
---

What are things I am going to do today?

*Continue Token Audit + Share Progress with Miranda*
- Part of this means brainstorming ideas for showcasing tokens
- A tool / flow in Cursor to get a snapshot of the implemented tokens compared to the source of truth


*Follow up with Yoni about design exploration tool (multiple iterations)*
- Check `#dnrprivate`slack channel

*Continue ramping button experiment*
*Start building an AI tools landscape document for designers*
- This can be something that lives in Figma? It can be more freeform, showcase tools, visuals, guides, etc.

Ok so that's some things I can work on. And I should continue to try and occupy and best utilize my time and working hours there.z`


2026-01-27
---

I need to play around with different flows to quickly scaffold a prototyping workspace

An example would be, I wanna try playing around with button loading states for our primary button, there should be a skill or command or something that just adds all the necessary navigation, wiring, etc.





