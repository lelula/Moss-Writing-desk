# AGENTS.md: working with a Moss Writing Desk folder

You are helping a writer with a book kept in a **Moss Writing Desk** folder. The desk is a small writing app that saves every book as plain files, so you can read and write them too. This file tells you where everything lives and how to work without making a mess.

If your platform has a better way to store or connect to these files (a connector, a synced drive, a project space), suggest it to your user. The layout below works anywhere files do.

## First, ask one question

At the start of a session, ask your user:

> "Should I save into the desk as we go, or only at the end of a section (or when you say save)?"

Remember the answer for the rest of the session (and beyond, if you have memory). Saving less often uses less of their usage limits. Either way, keep showing your work in the chat as you go. Don't go quiet just because you aren't saving yet.

## Where things live

The folder the writer picked is the **desk folder**. Each book has its own folder inside it:

```
Desk folder/
  My Novel/
    book.json               title, author, word goal
    where-i-left-off.md     the writer's note to their future self
    summaries.md            a few sentences per chapter
    bible.md                characters, places, things: the facts that must stay consistent
    chapters/
      01 The Storm.md
      02 Morning.md
    trash/                  trashed chapters and bible entries (same layout)
    days.json               words-per-day tracking (the app keeps this; leave it alone)
  Another Book/
    ...
  _backups/                 daily zip backups the app makes (leave it alone)
```

Folder names starting with `_` or `.` are not books.

## Read in this order (not the whole manuscript)

Summaries are the backbone. They let you know the whole book without loading the whole book.

1. `book.json`
2. `where-i-left-off.md`
3. `bible.md`
4. `summaries.md`

Only then open the chapter you are actually working in. Open other chapters only when you need an exact detail from them. A novel is far too big to read every time, and you don't need to.

## File formats

### Chapters: `chapters/NN Title.md`

```
# The Storm

It was a dark night.

Kit ran.
```

- The first line is `# ` plus the chapter title. Then a blank line, then the text.
- The number at the start of the file name sets the order: `01`, `02`, … (three digits once a book passes 99 chapters).
- Plain text. One paragraph per line or per blank-line-separated block. A line of `***` or `* * *` is a scene break.
- To add a chapter at the end, use the next number. To insert one in the middle, renumber the files after it **and** the matching headings in `summaries.md`.

### Summaries: `summaries.md`

```
# Chapter summaries

## 01 The Storm
Kit runs from the storm and reaches the lighthouse. The keeper lets her in, but he has seen her face before.

## 02 Morning
...
```

- One `## ` section per chapter, in book order.
- **Each heading must match the chapter's file name without `.md`.** That is how the desk pairs a summary with its chapter.
- 3 to 5 plain sentences: who is there, what happens, what has changed by the end. Present tense. Spell names exactly as the chapter does.
- Update a chapter's summary when the chapter is finished, or when it changes a lot.

### Writer's bible: `bible.md`

```
# Writer's bible

## Kit
Kind: Character
Spelled Katherine, goes by Kit
Eyes: grey-green
Afraid of deep water

## The Lighthouse
Kind: Place
North point of the island, 112 steps
```

- One `## Name` section per entry.
- The first line is `Kind:` with one of `Character`, `Place`, `Thing`, `Group`, `Other`.
- Then one fact per line. Only what matters for consistency: spellings, eye colour, ages, who is tied to whom, rules of the world, things that must not change.
- **Suggest bible changes, and let the writer approve them** before you write them. It is their book.
- If a chapter contradicts the bible or an earlier summary (eye colour changed, a name spelled two ways, a dead character talking), **flag it**. Don't silently fix it either way; ask which is right.

### `where-i-left-off.md`

Plain text. At the end of a session, offer to update it: what was about to happen, what to fix next, what the writer was stuck on.

### `book.json`

```json
{ "title": "My Novel", "author": "", "goal": 50000, "created": 1795000000000, "app": "Moss Writing Desk", "format": 1 }
```

Change `title`, `author` or `goal` if the writer asks. Keep the other fields.

## Working alongside the open desk

The writer may have the desk open while you work.

- The desk notices changed files when its window comes back into focus, or when they press **Reload from folder**. Tell them to do that if they don't see your changes.
- Don't both edit the **same chapter** at the same time. The last one to save wins.
- The desk renames chapter files when the writer retitles or reorders chapters. **List `chapters/` again before you write** instead of trusting a file name from earlier in the conversation.
- Never delete a chapter. Move it into `trash/chapters/` (and its summary into `trash/summaries.md`). The writer empties the trash.

## Common jobs

**Dictation.** The writer talks loosely; you write it up clean. Fix grammar, fill the small gaps, keep their voice and word choices. Put anything you invented (a name, a detail, a bridge sentence) in [square brackets] so they can see it and decide. Show the cleaned-up prose in the chat; save it into the chapter file following the answer to the first question.

**Typing.** The writer types in the desk. You help with summaries, bible updates, continuity checks and "I'm stuck" ideas.

**Editing and revision.** Work one chapter at a time. Say what you changed. Don't rewrite their style into yours.

**Brainstorming and outlining.** Turn ideas into chapter files with a title and a few lines of notes, plus a summary each, so the outline shows up in the desk.

**Continuity checks.** Compare a chapter against `bible.md` and `summaries.md`. Report names that look misspelled and details that contradict. Don't comment on style unless asked.

**Bringing in an existing book.** Import it **one chapter at a time**: write the chapter file, write its summary, suggest its bible entries, then move on to the next. This uses more tokens than pasting everything at once, but it won't choke, and it leaves a desk the writer can actually use. Tell them where you are as you go ("Chapter 7 of 31 done").

**Starting a new book.** Make a new folder in the desk folder with a `book.json` (at least a `title`), an empty `summaries.md` and `bible.md` (just their `#` title lines), and a `chapters/` folder. The writer may need to press Reload from folder.

## Keep to the folder

Only work inside the desk folder you were given, and only in the book you were asked about. Leave `days.json` and `_backups/` alone.
