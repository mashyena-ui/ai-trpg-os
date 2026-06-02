AI TRPG OS
Instead of having the GM manage all information, AI TRPG OS generates only what is visible from the PC's coordinate × each NPC's coordinate — that is the core design philosophy.
Each character can only see the world through their own coordinate. This constraint structurally eliminates the AI's temptation to leak information.
A coordinate is a character's viewpoint expressed in one line: what they see × how they act × their line. Through this combination, a soldier, a merchant, and a child each perceive the same scene differently and act accordingly.
By loading JSON files into Claude, a game master based on this design comes to life. Claude handles all rule arbitration, NPC roleplay, dice resolution, and session logging. The player only needs to type their actions in the chat.
Features
NPC Roleplay — Each NPC is assigned a coordinate (what they see × how they act × their line). Claude automatically excludes any speech or action that falls outside that coordinate
Fragments & Transformation — Conversations and actions accumulate as "fragments". When fragments touch the character's line, the coordinate transforms
Noise Log — An immunity file that categorizes and accumulates AI mistakes during sessions. Mistakes are fixed through structure, not procedural patches
Cross-Session Memory — Session state is saved in three files (PlayLog, Session_Start, CharacterSheet). Loading them next time resumes exactly where you left off
Custom TRPG Support — Fill in the included templates with your own rules and scenario. Any system works
File Structure
‘‘‘AI_TRPG_OS_Core_v1_34_EN.json    # OS core
NoiseLog_AI_TRPG_OS_v2_7_EN.json # Immunity file accumulating AI mistake patterns
StartPrompt_v1_25.json           # For first session
App_Template.json                # Rule system template
Scenario_Template.json           # Scenario template‘‘‘
How to Use
1. Create a Project
Upload the following to claude.ai's Project feature:
AI_TRPG_OS_Core_v1_34_EN.json
NoiseLog_AI_TRPG_OS_v2_7_EN.json
Your App file
Your Scenario file
2. First Session
Upload StartPrompt_v1_25.json to a new chat and send:
‘‘‘Load all files and start character creation following the StartPrompt.‘‘‘
3. Subsequent Sessions
Upload the three save files from last session (Session_Start, PlayLog, CharacterSheet) and send:
‘‘‘Load all files and resume the session.‘‘‘
Running a Custom TRPG
Fill in App_Template.json and Scenario_Template.json with your own rules and scenario.
For existing systems (e.g. Call of Cthulhu 7th Edition), you can have Claude convert the official PDF using the conversion prompts included in the README.
Requirements
claude.ai (Pro plan recommended)
Other chat AIs (Gemini, ChatGPT, etc.) also work, but Claude provides the most stable results
Background
How saying "I want to play TRPG" led to an OS two months later (Japanese):
Part 1
Part 2
Download page with a 3-session actual play log:
AI TRPG OS Download
License
MIT License
Any included sample scenarios or App files based on Chaosium Inc. / KADOKAWA materials are for personal use only.
