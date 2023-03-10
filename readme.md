---
id: 6c3f40e4-79b7-4b42-b9cd-eb559c1fa12e
created: 1675139885655
updated: 1675142578056
---
## Introduction

Here is a sample obsidian vault by Nick McMillan. It blends a few different ideas like the PARA method and hierarchical note-taking (seen in the note-taking app [Dendron](https://www.dendron.so/)). 

There is no correct way to use Obsidian (or other PKM tools), and my own vault organization will probably change as I figure out what works best for me. 

To fully explore this vault, please clone the repo and open up in Obsidian.

## Vault Layout

### General Layout

- All notes live in the `./notes folder.` 
- All media (like PNG, PDF, etc...) lives in the `./notes/assets/` folder.
- All template notes (notes that can be premade and auto-generated to make note-taking easier) live in `./utilities/templates/`

### Hierarchical Note Taking

Hierarchies are defined by periods in a file name. Periods take the place of folders and offer a few distinct advantages compared to folders. 

1. It allows you to see all your notes and not need to dig through folders that can become nested
2. The hierarchies can be easily refactored using regex tools. I personally use the refactoring commands of Dendron. This vault layout is compatible with Dendron so I can easily open it up and refactor my hierarchies in seconds. As notes scale or you need to make changes to how your notes are organized, you won't need to dig through folders and rearrange.

My top-level hierarchies (which can also be thought of as folders) are modeled after the PARA method of organization. Please read [the blog](https://fortelabs.com/blog/para/) by Tiago Forte to learn more about PARA as he will do a much better job at explaining. I find that this method of organization allows me to easily split my life and notes into deadlines, areas of responsibility, areas of interest, and research/technical notes. I have added extra hierarchies such as the `@` hierarchy for contacts and the `home` hierarchy for aggregating information in my vault to act upon.

The structure is as follows:


- [[home]]:  This main note offers a way to aggregate information in my vault to act upon and plan my life
- [[project]]: A project is ???a series of tasks linked to a goal, with a deadline.???
- [[area]]: An **area of responsibility** is ???a sphere of activity with a standard to be maintained over time.???
- [[resource]]: A **resource** is ???a topic or theme of ongoing interest.???
- [[archive]]: An **archive** includes ???inactive items from the other three categories.??? Use dendron to move items to archive
- [[@]]: List of people that are connected to the projects, areas, resources, and archives of my vault. I connect them to these different areas through backlinks instead of hierarchical note-taking. 

Each of these top hierarchies exists as a note. Below I will go into adding notes under a hierarchy.


#### Example

Let's say I want to add a project, which is something with a deadline that needs to be finished. I am a data journalist at NPR and also do freelance videography on the side. I also like to work on personal projects in my free time to grow my skills. 

Therefore I would like to add three hierarchies under the project category.

To do this I add three notes as followings:

- [[project.npr]]
- [[project.freelance]]
- [[project.personal]]

If I am working on an investigation into cryptocurrency at NPR, I would make a note with the title:

- [[project.npr.cryptocurrency]]

#### Hierarchies that work for me

For each type of note (project, area, resource, archive, @), I have come up with the following general hierarchies that offer a structure that makes sense to me. Feel free to change or add to make them work better for you. 


```
home.md
home.scratch.md
home.mobile.md
home.goals.md
home.2023-calendar.md

project.md
project.npr.md
project.npr.project-name.md
project.npr.project-name.meeting.md
project.npr.project-name.meeting.2023-01-28--meeting-title.md
project.npr.project-name.note.md
project.npr.project-name.log.md
project.npr.project-name.meeting.todo.md

@.md
@.Firstname-LastName.md

area.md
area.sport.md
area.sport.swimming.md
area.sport.swimming.workouts.md
area.sport.swimming.workouts.a-really-difficult-distance-set.md

resource.md
resource.code.md
resource.code.language.r.md
resource.code.language.r.how-to.md
resource.code.language.r.links.md

```

## General Note Format 

### Meta-data and linking

Metadata is added to add context to a note. For example, the data created or who attended a meeting. Then this information can be queried later to surface the note.

Metadata data for a note is recorded in two ways. One way is through front matter (the format used is `YAML`) and another done through a plugin called `Dataview`, which uses this `key::value` notation.

**I add metadata using YAML** for information about the notes creation. This is an example front matter:

```
---
id: 57d0a8e8-36fd-4259-a255-20d75dd9e4d3
updated: 1674935934968
created: 1671903136343
---

```

**Explanation of Frontmatter**
- id: is a unique id for each note. This is mainly done to maintain compatibility with the `Dendron` app
- title: the last hierarchy of the note
- desc: optional description
- created: when the note was created. This is a unix timestamp and handled through a plug in which I talk about further down.
- updated: when the note was modified. This is a unix timestamp and handled through a plug in which I talk about further down.

**I add metadata** using dataview notation for additional context. Backlinks will not auto-update in front matter but will update using dataview notation. 

For example if there are attendees in a meeting I would notate them like this:

```
attendees:: [[@.Firstname-Lastname]] [[@.Firstname-Lastname]]

```


### Body of  a note

Formatting is done through Markdown. Here is the website for markdown explaining how to use it. 

Links to a note use double brackets: `[[note-name]]` 

You can also add information with tags: `#work` tags can be nested `#work/urgent`

I usually use tags to denote the status of a note, like if a note or item needs review.

## Plugins

Plugins extend the functionality of Obsidian. But the danger is that some plugins have custom syntax whose functionalities would not work when the markdown is exported to other apps. 

In order to minimize this potential side effect of plugins, a good philosophy is that plugins should automate things you can do by hand, or make it easier to navigate your vault.

Here is a list of plugins and the reason I use them. I will also screenshot the settings I use when I think it's important.

**Make sure to go through all the settings yourself to fully explore**


### Core Plugins

I basically turn all core plug ins on

Here are some settings I like for the editor and files sections 

- New notes are always created in `./notes/`
- New attachments/media are always put in `./notes/assets/`
![[Screenshot 2023-01-30 at 10.45.20 PM.png|2000]]



### 3rd Party Plugins


#### Dataview
- Allows me to query my notes. Check the section `Flow of Information` for dataview queries that I use to surface information

#### Templater
- Allows you to apply predetermined templates and input outputs of code snippets. 
- For example, I have templates for 
	- a people note: 
	- a meeting note:
	- a regular note: 
- I use a user function to create a unique id for each note, from the output of the command line tool uuidgen
	- ![[Screenshot 2023-01-30 at 10.36.20 PM.png]]
- I have bound the following hotkeys to insert templates
	- ![[Screenshot 2023-01-30 at 10.38.05 PM.png]]
#### Breadcrumbs

- Allows you to see the vault in the right side panel, and navigate the hierarchical format. 

![[Screenshot 2023-01-29 at 2.05.48 PM.png]]

![[Screenshot 2023-01-29 at 4.50.15 PM.png]]
#### Obsidian Git
- Sets up convenient pulling and pushing to Github for versioning of notes


#### Periodic Notes
- Sets up a way to apply a note template when you push the day or week on the calendar 

#### Calendar
- Put a calendar on the right sidebar. 

#### Outliner

- Bring functionality to the outlines for better tabbing and moving about

#### Zoom
- If you click into a bullet point you can just focus on that bullet and it's children

#### Pandoc Plugin
- Allows for easy conversion of markdown notes to whatever format you want
- You have to install pandoc on your system 

#### Update time on edit
- Adds an updated and created key and value pair to the frontmatter of a note
- I use the unix timestamp format to keep it compatible with `Dendron`

#### Kindle Highlights
- Import your kindle highlights.
- I have it import into a folder outside of `./notes/` because its not notes that I have created

## Appearance

- I like the `Minimal Theme`, you customize the colors themes with the `Minimal Theme Settings Plugin`
- The theme also has custom markdown tasks renders which I use in my calendar
	- ![[157957663-5425edb7-3bee-4214-af63-971b56725cc2.png|1000]]
## Important Hotkeys to set / shortcuts to know

- ![[Screenshot 2023-01-30 at 11.36.44 PM.png]]
- `CMD + O` : Opens quick switcher
- `CMD + N`: New Notes
- `CMD + SHIFT + N`: Open Note in new tab
- `Control + T`: Insert Template
- `Control + N`: new note with a template applied
## Flow of Information

- Every hierarchy can have a `.todo` child
	- For example:  [[area.finance.todo]]
- All todo's are brought into the [[home.todo]] file with dataview query
	- move the cursor through to see the dataview query
- You can fill in the check mark and the original .todo file will be marked and the completed inline metadata will be added
- To record progress for something add a `.log` child
	- For example: [[project.work.project-name.log]]
- I like showing the sources for a journalism story by using data query as shown here: [[project.work.project-name]]








