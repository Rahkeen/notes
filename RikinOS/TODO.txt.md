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


