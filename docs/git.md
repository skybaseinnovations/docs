## Introduction
Version control software is an essential part of modern-day software developer practices.

By far, Git is the most widely used version control system in the world. It is a distributed and actively maintained open source project originally developed in 2005 by Linus Torvalds, the famous creator of the Linux operating system kernel.

New to Git? Check out the official getting started guide or this slide from a past talk I gave.

# What is a commit message?
The commit command is used to save changes to a local repository after staging in Git. However, before you can save changes in Git, you have to tell Git which changes you want to save as you might have made tons of edits. A great way to do that is by adding a commit message to identify your changes.

Commit Options
    -m
This option sets the commit's message.

    git add static/admin/config.yml
    git commit -m "Setup multiple roles for skybase-cms git gateway"
    -a or --all

This option automatically commits all (including new) tracked, modified or deleted files.

    git commit -a -m "Add a new role for skybase-cms git gateway"
    --amend

This option rewrites the very last commit with any currently staged changes or a new commit message and should only be performed on commits that have not been pushed to a remote repository, yet.

    git add .
    git commit --amend -m "Update roles for skybase-cms git gateway"

Why should you write good commit messages?
A well-crafted Git commit message is the best way to communicate context about a change to other developers working on that project, and indeed, to your future self as well.
Have you ever tried running git log on one of your old projects to see the "weird" commit messages you have used since its inception? It can be hard to understand why you made some changes in the past, and you'll wish you read this article earlier .

Commit messages can adequately communicate why a change was made, and understanding that makes development and collaboration more efficient.

## How to write?
Before now, I only used git commit -m "Fix X to allow Y to use Z" on my personal projects with just a subject and no extra description. This is great for small and clear fixes like git commit -m "Fix typo in README.md, but in cases of more extensive changes, you would need to add some extra details.

Editor method
Run git commit without a message or option and it'll open up your default text editor to write a commit message.

To configure your "default" editor:

    git config --global core.editor nano

This would configure Git to use nano as your default editor. Replace "nano" with "emacs," "vim," or whatever your preference is.

In the opened editor, the first line is the subject (short description), leave a blank line after it, and everything else is the extended description (body).

<Summarize change(s) in around 50 characters or less>

<More detailed explanatory description of the change wrapped into about 72
characters>

Command Line method
    git commit -m "Subject" -m "Description..."

The first -m option is the subject (short description), and the next is the extended description (body).

How to write good commit messages
Here at Skybase, we follow certain rules on writing commit messages, so it's easier for everyone working now and in the future to get along the project easily.


Here's the template:

    Capitalized, short (50 chars or less) summary, in imperative form

    More detailed explanatory text, if necessary.  Wrap it to about 72
    characters or so.  In some contexts, the first line is treated as the
    subject of an email and the rest of the text as the body.  The blank
    line separating the summary from the body is critical (unless you omit
    the body entirely); tools like rebase can get confused if you run the
    two together. The tense and verbs donot matter in this, you can explain
    needed on this body

Write your commit message in the capitalized imperative: **"Fix bug"** and not *"Fixed bug"* or *"fixed bug"*
or *"Fixes bug."* 

This convention matches up with commit messages generated
by commands like git merge and git revert.

Further paragraphs come after blank lines.

- Bullet points are okay, too

- Typically a hyphen or asterisk is used for the bullet, followed by a
  single space, with blank lines in between, but conventions vary here

- Use a hanging indent

If you use an issue tracker, add a reference(s) to them at the bottom,
like so:

Resolves: #123
Looks great, right? Here's how you can make yours great too:


Some Examples: 

Example 1:

    Fix course redirect error


Example 2:

    Add examination module

    - Setup exam types
    - Add migration files for exams
    - Setup views for exam types

Example 3:

    Refractor fee calculation

Example 4:

    Optimize report generation

    Fixes #87


Specify the type of commit:
Feat: The new feature you're adding to a particular application
Fix: A bug fix
Style: Feature and updates related to styling
Refactor: Refactoring a specific section of the codebase
Test: Everything related to testing
Docs: Everything related to documentation
Chore: Regular code maintenance.[ You can also use emojis to represent commit types]

Separate the subject from the body with a blank line
Your commit message should not contain any whitespace errors
Remove unnecessary punctuation marks
Do not end the subject line with a period
Capitalize the subject line and each paragraph
Use the imperative mood in the subject line
Use the body to explain what changes you have made and why you made them.
Do not assume the reviewer understands what the original problem was, ensure you add it.
Do not think your code is self-explanatory
Follow the commit convention defined by your team

## Conclusion

The most important part of a commit message is that it should be clear and meaningful. In the long run, writing good commit messages shows how much of a collaborator you are. The benefits of writing good commit messages are not only limited to your team, but indeed expand to yourself and future contributors.
