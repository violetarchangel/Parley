# What Is This?

A **browser-based engine for choice-driven chat fiction** — interactive stories told through fake text messages, branching dialogue, and character relationships. Think "Choose Your Own Adventure" meets "phone screenshots."

## The Core Idea

Stories are written as structured data (JSON/JavaScript), not code. The engine handles:
- Rendering phone-like chat interfaces
- Managing conversation history and character memory
- Branching choices that can jump between scenes or continue current conversations
- Background images, character portraits, and ambient theming
- Timed message reveals, typing indicators, and other "live chat" flourishes

You write the story. The engine brings it to life.

## How It Works (Broadly)

1. **You write a story file** — a JavaScript object defining characters, messages, choices, and branches
2. **You add assets** — PNG/JPG images for backgrounds, character avatars, chat wallpapers
3. **The engine loads it** — parses your story, renders the phone UI, handles player interaction
4. **Players experience it** — tapping through messages, making choices, unlocking branches

No compiling. No build steps. Just a web browser and a text editor.

## File Structure for Packaging

A complete story package can just be the story.js file. If you want to include media, should should place them in a subfolder in the same directory as the .js file, like so:

my-story/
├── story.js ← Your story data (required)
├── assets/
│ ├── wifeavatar.png
│ ├── backgrounds/
│ │ ├── phonebackground1.png
│ │ ├── ambientbackground.png

When creating your story, in the dialog, you must include the folder structure from the root of the .js file onwards, i.e. assets/backgrounds/ambientbackground.png

## Quickstart

Open Parley.html in you browser and click the editor button.
Fill out the sidebar with some story info, add some NPCs.
Click "+ New Node".
Click "add message", then start writing your story. You can change the NPC you are talking to at the top, and you can Ctrl+Enter to quickly switch characters.
You can also:
add an image, with a caption, for a photo message. 
add a SysMsg, this will diplay differently to a normal message, useful for thoughts or time skips.
Set a new Chat BG, this is the backgroud of the chat window, that you made with the Character dialog, here you can update it silently, for the duration of the story.
Set a Variable. Here you can name and set a value for when this node is loaded. Then, in the next node, you can query these variables within the messages themselves, to hide messages using the +Condition dialog.
When you need to move the story forward, fill out the bottom of the node, either by jumping to the node node, or by creating a player choice. This will allow you to branch your story, and set variables depending on the choices made.

Finally, export your json, and the import it within the player tab. Experimentation is the best way to get the hang of it.
