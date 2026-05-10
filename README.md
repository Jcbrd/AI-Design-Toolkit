# design-roadmap-architect

A Claude skill that generates framework-anchored project roadmaps for product designers.


## The problem

Designers are grappling with how the design process has changed with the emergence of AI. Traditional UX phases no longer map cleanly to modern product development, and there’s growing ambiguity around which tools, workflows, and methods actually make sense in AI-native work.

Design projects now start with a moving target. Designers are figuring out not just what to make, but how to work inside a landscape shaped by generative tools, agents, rapid prototyping, and AI-assisted research.


## What it does

Describe your project, answer a few onboarding questions about your experience and willingness to learn new tools, and the skill generates a personalized AI-native project roadmap tailored to the way modern design work actually happens.

The output is a living HTML tracker with:

adaptive project stages and sub-tasks

AI tool recommendations matched to your workflow and skill level

framework grounding (PAIR, JTBD, Lean UX, HAX, StoryBrand)

progress tracking across stages

end-of-stage prompts focused on what you actually shipped, not just what you completed

Rather than giving you a static process diagram, it helps you develop a workflow that evolves alongside the tools and practices shaping modern product design.


## Things worth knowing

**Stages are a menu, not a sequence.** Pick the ones your project needs. Skip user research if you know the user cold. Skip handoff if you're also building.


**There's a diversity rule.** It won't recommend the same generalist tool in every stage just because it technically could. Specialists beat generalists where a real specialist exists.


**Status comes from checkboxes.** One source of truth, no separate controls to disagree with.


## Install

Download the `.skill` file → drag into Cowork's installer → describe a project you're working on.


## Feedback welcome

Especially on: does the onboarding ask too much before giving anything back? Are the tool recommendations relevant or arbitrary? Does framework attribution build trust or just look academic?

Pull requests, issues, and "this is wrong" notes all welcome.
