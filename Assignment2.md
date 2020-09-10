  1)	 Describe what is the output of the following commands
1)	git branch
2)	git checkout BRANCH_NAME (USE THE NAME OF AN EXISTING BRANCH)
3)	git log --decorate

C:\Users\Alex_\Documents\GitHub\INF502\handson> git branch
* master

Shows the available branches and master.

C:\Users\Alex_\Documents\GitHub\INF502\handson>git checkout branch
Already on 'branch'

Changes to the branch name (in this example, a branch called “branch”)

C:\Users\Alex_\Documents\GitHub\INF502\handson>git log --decorate
commit 57bb14bf8dd3d1998a64fc7d1c0545ac55dc5f9c (HEAD -> master)
Author: Dahlmannnnn <54683052+Dahlmannnnn@users.noreply.github.com>
Date:   Mon Aug 24 16:34:20 2020 -0700

 	Initial commit

Shows the commits for this git

  2)Try git log --graph --all. What do you see?


C:\Users\Alex_\Documents\GitHub\INF502\handson>git log --graph --all
* commit 0f64887b3fec6ffb8f938d58a2876ca5b0f5ebe6 (origin/master)
| Author: Dahlmannnnn <54683052+Dahlmannnnn@users.noreply.github.com>
| Date:   Thu Aug 27 13:16:15 2020 -0700
|
|     Update Assignment1.md
|
* commit 8eaf2e2e632299ccc73433afbec6ae5b95bb253a
| Author: Dahlmannnnn <54683052+Dahlmannnnn@users.noreply.github.com>
| Date:   Thu Aug 27 13:15:57 2020 -0700	
|
|     Update Assignment1.md
|
* commit 1f7b2db65f472a2aedaed9de0b8cb1cce2a01eed
| Author: Dahlmannnnn <54683052+Dahlmannnnn@users.noreply.github.com>
| Date:   Thu Aug 27 13:14:47 2020 -0700
|
|     Update Assignment1.md
|
* commit 891b2394092844c201586f47cf6c83a90261ee84
| Author: Dahlmannnnn <54683052+Dahlmannnnn@users.noreply.github.com>
| Date:   Tue Aug 25 15:40:40 2020 -0700
|
|     Update Assignment1.md
|
* commit 370d68bb6473473591ea92ec0a9ef3801d3a0f16
| Author: Dahlmannnnn <54683052+Dahlmannnnn@users.noreply.github.com>
| Date:   Tue Aug 25 15:38:14 2020 -0700
|
|     Create Assignment1.md

  3)Use git diff BRANCH_NAME to view the differences from a branch and the current branch. Summarize the difference from master to the other branch.

C:\Users\Alex_\Documents\GitHub\INF502\handson>git diff Branch
diff --git a/Assignment1.md b/Assignment1.md
new file mode 100644
index 0000000..347fd86
--- /dev/null
+++ b/Assignment1.md
@@ -0,0 +1,251 @@
+    Alexander Dahlmann
+    Homework 1: INF 502
+
+
+Question 1:
+
+Example runs:
+
+    Please input length of side a: 2
+    Please input length of side b: 2
+
+    Length of side c is:  2.8284271247461903
+
+
+    Please input length of side a: 3
+    Please input length of side b: 4
+
+    Length of side c is:  5.0
+
+
+    Please input length of side a: 7
+    Please input length of side b: 8
+
+    Length of side c is:  10.63014581273465
+
+
+```python
+
+def pythagoreanTheorem(length_a, length_b):
+  Length_c = (length_a**2 + length_b**2)**0.5
+  return Length_c
+
+a = float(input("Please input length of side a: "))
+b = float(input("Please input length of side b: "))
+
+c = pythagoreanTheorem(a,b)
+
+print("Length of side c is: ", str(c))
+
+```
+
+Question 2:
:           


  4)Write a command sequence to merge the non-master branch into master


C:\Users\Alex_\Documents\GitHub\INF502\handson>git checkout master
Already on 'master'
Your branch is up to date with 'origin/master'.

C:\Users\Alex_\Documents\GitHub\INF502\handson>git merge branch
Already up to date.

  5)Write a command (or sequence) to (i) create a new branch called math (from the master) and (ii) change to this branch (yes, math is already there, just report what you've done, the error and the reason you got the error. If you deleted and recreated the branch, you are fine too)

C:\Users\Alex_\Documents\GitHub\INF502\handson>git checkout -b math
Switched to a new branch 'math'

  6) Edit B.py adding the following source code below the content you have there
print 'I know math, look:'
print 2+2


  7) Write a command (or sequence) to commit your changes

C:\Users\Alex_\Documents\GitHub\INF502\Assignment 2\handson\handson> git commit -av

8)

C:\Users\Alex_\Documents\GitHub\INF502\Assignment 2\handson\handson>git merge math
Merge made by the 'recursive' strategy.
 A.py | 10 +++++++++-
 1 file changed, 9 insertions(+), 1 deletion(-)

9)
C:\Users\Alex_\Documents\GitHub\INF502\Assignment 2\handson\handson>git merge --abort
fatal: There is no merge to abort (MERGE_HEAD missing).


10)
C:\Users\Alex_\Documents\GitHub\INF502\Assignment 2\handson\handson>git merge --abort
fatal: There is no merge to abort (MERGE_HEAD missing).


I needed to stop here as it became obvious that something was not working properly and I am at a complete loss as to what is going on, I have used github before and used repositories entirely on github and its associated github desktop applet so I am not entirely sure what is going on.
All the work I needed to do on github was fine, but everything done via git was a struggle and I think I am missing something big. Also it kept trying to look at assignment 1 for some reason.
