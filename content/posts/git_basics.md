+++
title = "Git & Github Basics"
date = "2021-07-08T20:15:58-07:00"
author = "Lux"
cover = "/images/git_basics_cover.jpg"
tags = ["git", "github"]
keywords = ["git", "github"]
description = "A short post on the basics of Git & Github"
showFullContent = false
+++

# ❓ what is git?

- Git is a **distributed version control system**.
- Okay... so what is a version control system then?
    - A version control system keeps track of all the changes you make to a file or project throughout it's entire lifetime.
    - Why is this useful?
        - It turns out there are a *ton* of reasons this is helpful in the world of software development.
        - For one, if you introduce changes to a file that *break* a previously working project, you can use Git to revert your project back to the previous, working state.

            > Git is a bit like an "undo" button with a super long memory that can remember every action you took!

        - Another useful feature is if you are working in a team or other collaborative environment. Have a question about why a certain file or function was written the way that it was? Git allows you to see who wrote that part of the code so you can reach out directly to that person.
- So now that we know what a version control system is, what does it mean that Git is **distributed**?
    - There are three main different types of version control systems that exist:
        - **Local**
            - In a local version control system, everything (meaning the project and the full history of changes to the project) is stored only in one place - your computer. If you are the only person working on a project, this *could* meet your needs; however, it can be error-prone.
        - **Centralized**
            - In a centralized version control system, the project and the history of changes are stored on a central server. Individuals can "checkout" certain files to work on, but they only receive that specific file - not the whole history of the file, nor any other files in the project.
            - If the central server goes down, no one can checkout any new files until it comes back up. If the server suffers data loss, any files that were not currently being worked by someone may just be lost.
        - **Distributed**
            - In a distributed version control system, whenever someone wants to work on a project, they actually *clone* the entire project and all of its history onto their computer from a remote repository (such as a project hosted on GitHub or on a private server).
            - So if something happens to the remote repository, there are essentially full backups located on the actual computers of anyone who is working on the project.
    - While Git is not the only distributed version control system that exists, it is definitely one of (if not the) most popular systems today.

# 🤔 what is github?

- While Git is a program you can run on your computer, Github is an online platform that you can use with Git to store your project and manage collaboration.
- When we talk about remote repositories, Github is an example of a very popular location to store a repository.
- In other words, Git & Github are not the same thing; Github is an online tool that helps store Git-managed projects & makes certain social/collaboration features easier. You can use Git without Github, but you can't really use Github without using Git.

# ✅ git workflow

- While going through this section, the following visual may be helpful:

    ![Diagram of git workflow](/images/git_diagram.png)

- There are **four** different areas a file can "live" in at any given time:
    - **Working Directory**
        - This is the folder you are currently working out of in your code editor. When you save a file in your code editor, you are saving a file in this folder. Git doesn't know about changes made here until you explicitly tell it about them.
    - **Staging Area**
        - When you are ready to tell Git about changes you have made to a file, you can run:

            ```bash
            git add <filename>
            ```

            in your terminal, replacing <filename> with the actual name & extension of the file you want to commit to changing.

        If you run `git add .`, the `.` tells Git that you want to add all of the files in your working directory to the staging area.

        - Git is a little afraid of commitment and likes to take things slow! Because of this, when you add a file to the staging area, Git waits for you to confirm that you are absolutely sure you like the changes you made before it adds those changes to the version control history.
        - If you make a mistake and want to press the "undo" button to remove the last file you added to the staging area, you can run:

            ```bash
            git reset HEAD~1
            ```

            in your terminal. This will remove the last added file from your staging area.

        You can check the current status of your files (to see, for example, what is in your staging area) by running `git status` in your terminal.

    - **Local Repository**
        - When you are sure that you want to make a commitment to any changes you have made, you can "commit" the changes you put in your staging area into your local repository by running:

            ```bash
            git commit <filename> -m "short message explaining changes here"
            ```

            in your terminal.

            Just like when adding files to the staging area with `git add .`, running `git commit .` will commit all of the changes in your staging area at once!

        - This basically tells Git: "I made some changes to these files that I like and want to keep! Please remember these changes for the future in case I need to remember what this looked like beforehand."
        - The `-m "short message explaining changes here"` part of the command is important because it allows you to add a short message about your changes so you and other developers can quickly tell what the purpose of the change you made was.
            - If you leave out this part, your default code editor should pop up and Git will wait for you to create and save a message about your changes.
        - Right now, your code still only exists on your computer. If you have a remote repository hosted on Github, you have one more step to go before all of your changes show up on Github.
    - **Remote Repository**
        - This is the main place your code "lives" at all times; anyone working on the project can clone a copy of this remote repository and create a local repository on their own computer, complete with the full history of changes up until the moment they clone it.
        - When you make commit a change to your local repository, you can let your remote repository know about the change too by running:

            ```bash
            git push origin main
            ```

            in your terminal. `origin` tells Git that you want to use the remote repository, and `main` tells Git that you want to add it to the main branch.

            - More on branches another time...for now, `main` will be the only one you should have to use. Once you get more comfortable with the basics, you can checkout some of the [other resources]() to learn more.

            There was a recent move to using `main` instead of the previously used `master`; you may still see `master` used online in tutorials, but know that you can generally safely switch it out with `main` and it means the same thing.

        - Now the next time someone clones the repository, they will also get all of your changes along with it.
        - If you are working on a project with other people, they will be updating the remote repository too. You don't need to re-clone the whole repository every time that happens, though! Instead, run:

            ```bash
            git pull origin main
            ```

            in your terminal. This will grab all of the changes that have been made to the remote repository and update your files locally to match.

- For a **full walkthrough** of the process of creating and updating a repository on Github with Git, see the links below.

# ⚙️ other resources

- [Basics of Git & Github](https://www.freecodecamp.org/news/learn-the-basics-of-git-in-under-10-minutes-da548267cc91/)
    - Article on FreeCodeCamp
    - Includes a walkthrough of the process of creating a new repository and updating it
- [Git & Github Crash Course](https://www.youtube.com/watch?v=RGOj5yH7evk)
    - Youtube video by FreeCodeCamp
- [Git & Github for Poets](https://www.youtube.com/watch?v=BCQHnlnPusY&list=PLRqwX-V7Uu6ZF9C0YMKuns9sLDzK6zoiV)
    - Youtube playlist of videos that teach Git and Github in a very friendly, approachable way
- [Gitignore.io](https://www.toptal.com/developers/gitignore)
    - Autogenerates .gitignore files for you
    - For information on .gitignore files & what those are, see the [FreeCodeCamp article]() linked above