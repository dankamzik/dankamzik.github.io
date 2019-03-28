Git Bash Notes: How to Commit from cmdln


dankamzik@Dan MINGW64 ~/documents/github
$ ls
collectclouds/  dankamzik.github.io/  DO-NOT-USE-THIS-FOLDER.txt

dankamzik@Dan MINGW64 ~/documents/github
$ git clone https://github.com/dankamzik/JavaScript-Learning-and-Examples.git
Cloning into 'JavaScript-Learning-and-Examples'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), done.

dankamzik@Dan MINGW64 ~/documents/github
$ git status
fatal: not a git repository (or any of the parent directories): .git

dankamzik@Dan MINGW64 ~/documents/github
$ ls
collectclouds/        DO-NOT-USE-THIS-FOLDER.txt
dankamzik.github.io/  JavaScript-Learning-and-Examples/

dankamzik@Dan MINGW64 ~/documents/github
$ cd JavaScript-Learning-and-Examples/

dankamzik@Dan MINGW64 ~/documents/github/JavaScript-Learning-and-Examples (master)
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        JS Coloration Tool/
        js practice animation/
        js practice quiz/
        jsPracticeHell/

nothing added to commit but untracked files present (use "git add" to track)

dankamzik@Dan MINGW64 ~/documents/github/JavaScript-Learning-and-Examples (master)
$ git add .

dankamzik@Dan MINGW64 ~/documents/github/JavaScript-Learning-and-Examples (master)
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   JS Coloration Tool/index.html
        new file:   js practice animation/index.html
        new file:   js practice animation/pics/dan.jpg
        new file:   js practice quiz/js-quiz-practice.js
        new file:   jsPracticeHell/css/bootstrap.min.css
        new file:   jsPracticeHell/css/stylesheet.css
        new file:   jsPracticeHell/fonts/Geomanist-Regular-Italic.otf
        new file:   jsPracticeHell/fonts/Geomanist-Regular.otf
        new file:   jsPracticeHell/fonts/Savoye LET Plain1.0.ttf
        new file:   jsPracticeHell/index.html
        new file:   jsPracticeHell/pics/star.jpeg
        new file:   jsPracticeHell/script.js


dankamzik@Dan MINGW64 ~/documents/github/JavaScript-Learning-and-Examples (master)
$ git commit -m "JavaScript Exercises"
[master 334551d] JavaScript Exercises
 12 files changed, 329 insertions(+)
 create mode 100644 JS Coloration Tool/index.html
 create mode 100644 js practice animation/index.html
 create mode 100644 js practice animation/pics/dan.jpg
 create mode 100644 js practice quiz/js-quiz-practice.js
 create mode 100644 jsPracticeHell/css/bootstrap.min.css
 create mode 100644 jsPracticeHell/css/stylesheet.css
 create mode 100644 jsPracticeHell/fonts/Geomanist-Regular-Italic.otf
 create mode 100644 jsPracticeHell/fonts/Geomanist-Regular.otf
 create mode 100644 jsPracticeHell/fonts/Savoye LET Plain1.0.ttf
 create mode 100644 jsPracticeHell/index.html
 create mode 100644 jsPracticeHell/pics/star.jpeg
 create mode 100644 jsPracticeHell/script.js

dankamzik@Dan MINGW64 ~/documents/github/JavaScript-Learning-and-Examples (master)
$ git push origin master
Enumerating objects: 23, done.
Counting objects: 100% (23/23), done.
Delta compression using up to 8 threads
Compressing objects: 100% (18/18), done.
Writing objects: 100% (22/22), 254.43 KiB | 6.52 MiB/s, done.
Total 22 (delta 0), reused 0 (delta 0)
To https://github.com/dankamzik/JavaScript-Learning-and-Examples.git
   a16fa5a..334551d  master -> master

dankamzik@Dan MINGW64 ~/documents/github/JavaScript-Learning-and-Examples (master)
$ ^C

dankamzik@Dan MINGW64 ~/documents/github/JavaScript-Learning-and-Examples (master)
$
