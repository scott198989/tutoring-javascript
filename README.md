## Git Flow - Starting from scratch

1.  When first opening your terminal, you will start in your machines root directory 

2. If you do not have the repository saved on your local (your computer), locate the repo in github and find the main branch.  Click the blue "code" button and copy the url.  Go back to your terminal (again make sure you are on your desktop (cd Desktop)) and type git clone ***repo url***.  You will then cd into that directory.  Example: (do not type $)

$ cd Desktop

$ git clone [repourl.github.com](https://github.com/scott198989/tutoring-javascript.git)

$ cd tuoring-javascript

3.  You will want to avoid using main as your working branch, to create a branch, while on main, type $ git checkout -b branch name.  This command will create the branch for you and checkout to it at the same time.

4.  Once you complete your work, you will want to push your work to your branch.  You can either type $ git status, or a shorthand way is $ gst. This will list all the files that have changes and need to be tracked to push to your branch.  You can do this one of 3 ways.  I have listed them in order of preference.  The last method you dont really want to do unless you have a bunch of files.

4a. $ gst
    $ git add filename
    $ git commit -m "explaining git flow"
    $ git push origin branch name

4b. $ gst
    $ git add -A <--- This will add everything you have worked on in the current directory only. You can use pwd to see what directory you are working in.  
    $ git commit -m "explaining git flow"
    $ git push origin branch name

4c. $ gst
    $ git add . <--- This will add EVERYTHING to your push!
    $ git commit -m "explaining git flow"
    $ git push origin branch name 

5.  Once you have pushed your work, follow these steps.

5a. checkout to main
    $ git checkout main OR shorthand $ gco main
    $ cd .. <--- always a good idea to checkout of your project when not working on it

## Fetching 

1. To fetch your partners work, again make sure you start on your desktop ($ cd Desktop). cd into your project folder and you will be on the main branch.  I find it is always a good idea to pull from main to avoid a merge conflict.  Even though you may not have anything on main yet, it is a good idea to do. 
   
   $ git pull origin main 
   
   Next, if you do not have your partners branch on your local, you can use 

   $ git fetch --all

This command will fetch all the current branches in the repo. If you know the specific name of the branch you want, but dont want all the branches (if you dont have them already) you can:

    $ git fetch origin branch name

Then make sure you

    $ git pull origin branch name

If you do already have your partners branch:

    $ git branch

    $ gco branch name

    $ git pull origin branch name

When your work is completed, you will follow the steps from before, add your work, commit, then push.  

## Helpful commands 

$ pwd <--- shows your working directory

$ git stash <--- if you made mistakes and DONT want to push your work, maybe it might mess your good code or something, but for whatever reason you dont want to push your work, you can use this and instead of being tracked by git this will save your work to your local, and allow you checkout of the branch.

$ git stash apply <--- If you change your mind on the previous command, and realize you DO want to push your work, use this command to undo the stash.

$ git branch -D <--- will force delete the branch on your local, make sure your changes are commited and pushed

$ git branch -d <--- will also delete, but only if your changes are pushed.  Its a litte "safer"

**Only use the above two once your branch has been merged!** 

In the instance of a merge conflict, you will see a bunch of wording and it will suggest you type "git pull".  Do it.  You will then have a merge conflict, and the best way I have found to solve this is by:

$ git config pull.rebase <--- this will rewrite your commit history, but it will solve the merge conflict, usually...make sure your team pulls from the branch afterwords and everyone has the same work.  

## JavaScript Conditionals 

Conditionals will have "if, else if, and else". JavaScript reads from top to bottom, so once the condition is met, or "true", the code stops running.  That could mean the first "if" is true, then the code stops, or it code be any one of the "else if" statements, if the first "if" isnt true, but one of the "else if" is, it will end at that particular statement.  If none of the statements are true, then our last statement, the catch all "else", will be true.  

an example:

const example = "100";

if (100/3 === 10) {  
    console.log(example)
} else if (100/20 === 10) {
    console.log(example)
} else {
    console.log("Check your math!")
}

# you can refactor this code using the ternary operator, the "?"

const example = "100";

(100/3 === 10)
    ? console.log(example)
    : (100/20 === 10)
        ? console.log(example)
        : console.log("Check your math!")

console.log(example)

think of the : (100/20 === 10) as suggesting the statement, like a student saying "100 divided by 20 strictly equals 10", and the question mark and console log, ? console.log(example), is the teacher saying "If that is correct, I will write it on the board".  The opposite is true as well.  Same scenario, but "100/3 === 20", the teacher would write on the board, or, ? console.log(example), false.  