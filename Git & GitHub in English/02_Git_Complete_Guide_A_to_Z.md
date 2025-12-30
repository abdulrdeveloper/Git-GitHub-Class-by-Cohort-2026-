==================================== Let's Learn Git ==========================================


        Ok, first question that comes up is: How does Git internally track code/project?
        How does it track all our code changes when we don't see anything happening, 
        then how does Git know what changed in the code?


==================


    Answer:


        When Linus Torvalds started building Git, he thought:
        
        "I need to track code changes, but where do I store them?"
        
        He could have stored them in databases (MongoDB, MySQL, PostgreSQL), but 
        databases exist on separate servers - they're not portable (hard to move/shift).


        So he came up with a CLEVER SOLUTION:
        
        He created a ".git" folder inside the project itself (hidden folder)
        This folder contains a special "database" (actually a complex file structure)
        That records every single change
        
        Now, when someone writes code and commits with Git:
        
            → Git automatically scans all files
            → Checks what changes happened
            → Shows each change as + or -:
                    + = New line added
                    - = Line removed/deleted
            → Generates a unique ID (hash) for those changes
               So in the future you can view that specific change using this unique ID
            → Saves everything in the .git folder
            → Later, when you want to see old changes or old code,
               you can retrieve it using commands


        Simple Example:
        
            Ahmad: "I added 5 new lines to file.js"
            ↓
            Git: "Saved record in .git folder (+ 5 lines)"
            ↓
            Ahmad: "Runs git log command"
            ↓
            Git: "Retrieves data from .git folder and shows Ahmad"
        
        IMPORTANT Point: .git Folder is Hidden
        
            This is why Linus made .git folder hidden
            So users don't accidentally touch or delete it
            Windows/Mac/Linux all have hidden files/folders
            This keeps the .git folder safe and protected



======================================== GIT COMMANDS ==========================================


        Now understand, if we want to build our own Git system (like Linus did),
        we have to type git commands in the terminal


==================


    Command 1: git init


        Git says: "You type the git init command, and I'll create a .git folder 
        that will be hidden - you don't need to do anything with it"
        
        What Happens:
        
            You: Type "git init" command in terminal and press Enter
            ↓
            Git: Automatically creates a hidden ".git" folder that you don't need to touch
            
        Example:
        
            $ git init
            
            Output: "Initialized empty Git repository in /path/to/your/project/.git/"
            
            (Means: .git folder was successfully created!)
        
        For Verification (Check that .git folder was created):
        
            $ ls -a
            
            Output:
            .   ..   .git   file.js   index.html
            
            (Look! The .git folder is visible with other hidden files)
            
            Note: 
             ls = List files (only shows visible files)
             ls -a = List ALL files (also shows hidden files)
             .git folder is hidden so we need to use "ls -a"


==================


    Command 2: git add


        Now we have .git folder ready. But Git still isn't tracking our code.


        Git says: "You've written code, but you haven't told me which files to track!"


        So Git says: "You type 'git add <filename>' command. I'll put that file in the 
        'staging area'. It's not being tracked yet, just ready to be committed"


        What Happens:
        
            You: "git add file.js" (or "git add ." for all files)
            ↓
            Git: "Okay, I've added file.js to the tracking list"
            ↓
            Now this file is in "staging area" (Git knows which file to track)
            
        Example:
        
            $ git add file.js
            
            (No output - it silently adds to tracking)
            
        Or to add all files:
        
            $ git add .
            
            (All files are ready to be tracked!)


        Now Git completely knows which files to track and has prepared them, but hasn't tracked them yet


==================


    Command 3: git commit


        Now Git knows which files to track and everything is ready in the staging area. 
        But Git still hasn't SAVED the files in the .git folder.


        Git says: "Now type the git commit command. I'll permanently save these files 
        in the .git folder and give you a unique ID (hash)"
        
        What Happens:
        
            You: "git commit -m 'your message'"
            ↓
            Git: "Permanently saves files in .git folder"
            ↓
            Generates a unique hash (ID) for each commit
            ↓
            Changes are now permanently recorded in .git folder
            
        Example:
        
            $ git commit -m "Added login feature"
            
            Output: "[master abc123d] Added login feature
                     1 file changed, 50 insertions(+)"
            
            (Look! Gave a unique ID "abc123d" - and you can identify 
             this commit using that ID in the future)


==================


    COMPLETE WORKFLOW:


        Step 1: git init → Create .git folder (do this only once)
                ↓
        Step 2: Write code / make changes
                ↓
        Step 3: git add .   [ → Tell Git: "Track these files!" ]
                ↓
        Step 4: git commit -m "message" [ → Tell Git: "Now save these files!" ]
                ↓
        REPEAT: Steps 2, 3, and 4 every time you make new changes!


==================


    Command 4: git log


        You can view the complete history whenever you want.
        
        $ git log
        
        (Output: Shows all commits with hash, author, date, and message)
        
      Short Version (Easy View):
        
        $ git log --oneline
        
        (Output: Only shows hash and message - one commit per line)
        
        Example:
        
        $ git log --oneline
        
        def456f third commit
        xyz789e second commit
        abc123d first commit
        
        (Very short and clean!)


==================


    Command 5: git status


        You can check current status - which files changed,
        which are staged, which are untracked.
        
        $ git status


        (Output: file.js and index.html changed, new-file.js is not tracked yet, etc)


==================


    Command 6: git diff <commit1> <commit2>


       You can see changes between two commits.


       $ git diff 840c9bd 9b17369


       (What changed from 840c9bd to 9b17369)
    
       Important: Order matters!
       - First hash = Old (starting point)
       - Second hash = New (ending point)
       - If you reverse them (new commit first and old hash later), 
         the code changes will also show reversed, so don't do that


==================


    Command 7: git commit -am "message"


        Combine git add and git commit in one command (shortcut).


        $ git commit -am "updated file"
        
        Note: 
        - Only works for modified files
        - Doesn't add new files
        - In professional work, use git add and git commit separately
        
        (Keep it brief - no need for too much detail)


==================


⭐⭐⭐ IMPORTANT CONCEPT: HEAD ⭐⭐⭐


    What is HEAD?
        
        → In Git, the latest/newest commit is called "HEAD"
        → HEAD = Current position where Git is standing
        → When you make a new commit, HEAD automatically moves to that new commit
        
        Example:
        
        Commit 1: abc123d (1st commit)
        Commit 2: xyz789e (2nd commit) ← HEAD is here (latest)
        
        Now if you make a new commit:
        $ git commit -m "I Update Code"    ← (3rd Commit)
        
        Then:
        Commit 1: abc123d (1st commit)
        Commit 2: xyz789e (2nd commit)
        Commit 3: def456f (3rd commit) ← HEAD has now moved here (NEW LATEST)
        
        Simple Rule: HEAD always points to the latest commit!
        
        In git log you'll see:
        $ git log
        
        commit def456f (HEAD -> main)  ← This is the latest
        Author: Abdul
        Date: Dec 31 2025
            third commit
        
        commit xyz789e
        Author: Abdul
        Date: Dec 30 2025
            second commit
        
        commit abc123d
        Author: Abdul
        Date: Dec 29 2025
            first commit


==================


    Command 8: git revert <commit_hash>


        SAFELY undo an old commit (by creating a new commit).
        
        $ git revert def456f
        
        (Undoes commit 3's changes, but preserves the history)
        
        How it works:
        
        Commit 1: "Added login"
        Commit 2: "Added dashboard"
        Commit 3: "Added payment" ❌ (was wrong)
        
        $ git revert def456f
        
        Commit 1: "Added login"
        Commit 2: "Added dashboard"
        Commit 3: "Added payment" (still in history)
        Commit 4: "Revert: Added payment" ← New commit (removes payment code from commit 3)
        
        Important Points:


        - History is preserved (not like git reset)
        - Creates a new commit
        - Used by professional teams
        - Safe and trackable


==================


    Command 9: git reset --hard <commit_hash>


        DELETE everything after a commit (including from history).
        
        $ git reset --hard abc123d
        
        (Commits 2 and 3 are completely removed)
        
        How it works:
        
        Before:
        Commit 1: "login"
        Commit 2: "dashboard"
        Commit 3: "payment" ❌
        
        $ git reset --hard abc123d


        After:
        Commit 1: "login" ← HEAD moves here
        (Commits 2 and 3 are deleted!)


        ⚠️ IMPORTANT - DANGEROUS:
        - History is completely deleted (no backup or trace of changes)
        - Causes problems in teams
        - Use git revert instead in professional work!
        - Only use on your own projects if you're sure
        - Recovery is very difficult
        
        Professionally: Use git revert, avoid git reset --hard!



============================================================================================================