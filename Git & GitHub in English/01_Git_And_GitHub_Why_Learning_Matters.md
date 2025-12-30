==================================== GIT & GITHUB ======================================


Question:


        First question that arises is: Why do we want to study Git & GitHub?
        Work was happening without Git too, so what was the reason to 
        create/build/introduce Git & GitHub?


==================


Answer with Example:


        Imagine there's a developer named Ahmad who runs code on his local machine.
        He saves his code on a pen drive and shares it with his teammate so they 
        can use it. When the teammate views the code, they make some changes and 
        return the updated code via pen drive back to Ahmad.
        
        Now Ahmad doesn't know what's happening in the code, which changes were made,
        where the changes occurred. After a while, the teammate realizes there's an 
        issue in the code and fixes it. Again, they have to give Ahmad the pen drive.
        This cycle continues...


==================


Problems They Face:


            - When teammate made changes, Ahmad didn't know what changed in the code
            - When Ahmad made changes, teammate didn't know what changed in the code
            - Which files changed, which were deleted - there was no way to know
            - Every time someone made changes, they had to share the pen drive
            - Both couldn't work simultaneously (collaboration was very difficult)
            - There was no history/record of code changes - couldn't retrieve old versions


==================


Solution - Part 1: Git (Local Version Control):


        Now... when they identified the problem, they built a CODE TRACKER 
        which they named "Git".
        
        Actually, "Git" is a Version Control System (VCS). There are other VCS in the 
        market like Mercurial, Apache Subversion (SVN) etc, but Git is the most popular.


        Git does the following:


            - Tracks all changes in the code
            - Shows who made what changes and when
            - Displays history of modified/changed files
            - Can be used by even 1 developer (locally)


        This way, they solved one problem.


==================


        But there was still a BIG PROBLEM:


            - Pen drive still had to be shared every time
            - Confusion about which version was latest/updated
            - No central backup existed
            - Code was only on local machines - only whoever had the pen drive could code


        This was a huge collaboration problem.


==================


Solution - Part 2: Remote Repository (GitHub):


        So they built a single source SOLUTION together where all developers 
        could push their updated code to a central server, which they named "GitHub".
        
        Actually, what we call "server" is referred to as "Remote Repository" in this context.
        GitHub is just one example. Other remote services exist like GitLab, Bitbucket etc.
       
        GitHub (Remote) does the following:


            - It's a central server (in the cloud) where developers can collaborate
            - All developers connect to GitHub
            - When a developer updates code, they "Push" it to GitHub
            - All other developers can easily view the latest code and "Pull" it
            - Everyone instantly knows what changed in the code
            - Complete backup of code stays safe in the cloud


        This way, the collaboration problem was completely solved too!


==================


Important Note - Git is Independent:


        Git can be used by even 1 developer on their local machine:
        
            - Can view code changes - what changed yesterday, what changed today
            - If there's an issue in the code, can easily go back to old code
            - Git doesn't need internet or a server - it's LOCAL software
            
        When Git was created, it was only for local use so you could track your projects.
        Later, when collaboration became necessary, remote services like GitHub were created 
        that host Git in the cloud.
        
        In Simple Words:
            Git = Local Version Control System (On your computer)
            GitHub = Remote Repository Hosting (On the internet, for collaboration)
            GitLab = Another remote option like GitHub


==================


Who Built Git?:


        Git was created by "Linus Torvalds" in 2005. He was working on the Linux Operating 
        System and at that time Linux was growing very rapidly. Thousands of developers were 
        working together and tracking code became very difficult.
        
        Previously they were using other version control systems (like SVN) but they were slow 
        and limited. So Linus thought he should build his own version control system that would be:
            
            - Very fast
            - Distributed (every developer has the complete code)
            - Reliable


        He built Git in just a few weeks as a side project! Today Git is the world's most 
        popular version control system.


--->>


Fun Fact:


        "Git" means "annoying or foolish person" in English.
        Linus jokingly gave it this name because Git version control was quite 
        strict and complicated! Besides, after Linux, Git is another "Linus creation" 
        that changed the world!


==================


Important Clarification - Git vs GitHub:


        Nowadays many people write "learned GitHub" on their resume but 
        it's TECHNICALLY WRONG!
        
        The truth is:
        
            ❌ "Learned GitHub" = WRONG
            ✅ "Learned Git" = CORRECT
        
        Why?
        
        GitHub is just a HOSTING SERVICE where you store code.
        Learning GitHub means just clicking buttons and creating repositories.
        
        Git is a COMPLETE VERSION CONTROL SYSTEM that needs to be learned and we'll learn it soon:
        
            - Understanding commands (init, add, commit, push, pull, branch, merge, etc.)
            - Understanding concepts (staging, commits, history, etc.)
            - Learning workflows (how to collaborate properly)
            - Problem solving (resolving conflicts, etc.)
        
       
        So when someone asks "What's the difference between Git and GitHub?"


        Answer:


           "Git = Version Control System (tool/language)
            GitHub = Hosting service for Git (platform)"


        Most students create GitHub accounts but don't properly learn Git.
        They create GitHub repositories but don't actually know how to use Git!
        So when asked in interviews, give the proper answer!



=============================================================================================================