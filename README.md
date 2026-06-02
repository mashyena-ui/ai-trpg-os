AI TRPG OS
Instead of having the GM manage all information, AI TRPG OS generates only what is visible from the PC's coordinate × each NPC's coordinate — that is the core design philosophy.
Each character can only see the world through their own coordinate. This constraint structurally eliminates the AI's temptation to leak information.
By loading JSON files into Claude, a game master based on this design comes to life. Claude handles all rule arbitration, NPC roleplay, dice resolution, and session logging. The player only needs to type their actions in the chat.
Features
NPC Roleplay — Each NPC is assigned a coordinate. Claude automatically excludes any speech or action that falls outside that coordinate
Fragments & Transformation — Conversations and actions accumulate as "fragments". When fragments touch the character's line, the coordinate transforms
Noise Log — An immunity file that categorizes and accumulates AI mistakes during sessions. Mistakes are fixed through structure, not procedural patches
Cross-Session Memory — Session state is saved in three files. Loading them next time resumes exactly where you left off
Custom TRPG Support — Fill in the included templates with your own rules and scenario. Any system works
How to Use
Upload Core and NoiseLog to a claude.ai Project
Add your App file and Scenario file to the same Project
Upload StartPrompt to a new chat and send: "Load all files and start character creation following the StartPrompt."
For subsequent sessions, upload Session_Start, PlayLog, and CharacterSheet instead
Requirements
claude.ai (Pro plan recommended)
Other chat AIs also work, but Claude provides the most stable results
Background
How saying "I want to play TRPG" led to an OS two months later (Japanese):
Part 1
Part 2
Download page: AI TRPG OS
License
MIT License
