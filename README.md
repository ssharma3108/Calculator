# Calculator – Git Branching, Merging & Conflict Resolution

## Problem Statement
This repository demonstrates the use of Git for collaborative development using a simple Calculator application.  
The project covers Git branching, merging, rebasing, fetching, pulling, stashing, and merge conflict resolution.

---

## Repository Overview
The Calculator repository contains basic arithmetic operations implemented using Java.  
Each operation is developed in a separate Git branch and later merged into the main branch.

---

## Branching Strategy

The following branches were created:

- `main` – Stable and final branch
- `addition` – Implements addition operation
- `subtraction` – Implements subtraction operation
- `multiplication` – Implements multiplication operation

Each feature was developed independently in its respective branch.

---

## Calculator Operations

### Addition (`addition` branch)
```java
import java.util.Scanner;

public class Add {
  public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);
    int a = sc.nextInt();
    int b = sc.nextInt();
    System.out.println("Addition -: " + (a + b));
  }
}

```

---

### Subtraction ('subtraction' branch)
```java
import java.util.Scanner;

class Sub {
  public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);
    int a = sc.nextInt();
    int b = sc.nextInt();
    System.out.println("Subtraction -: " + (a - b));
  }
}
```

---

## Multiplication ('multiplication' branch)

```java
import java.util.Scanner;

class Sub {
  public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);
    int a = sc.nextInt();
    int b = sc.nextInt();
    System.out.println("Multiplication -: " + (a * b));
  }
}
```
---

## Git operations performed


1. Git Stash and Git Stash Pop
Purpose

To temporarily save uncommitted changes without committing them.

Commands Used
git stash
git stash pop

Explanation

git stash stores uncommitted changes and cleans the working directory.

git stash pop restores the most recently stashed changes back to the working directory.

2. Git Fetch vs Git Pull
Purpose

To understand the difference between fetching and pulling changes from a remote repository.

Commands Used
git fetch origin
git pull origin main

Explanation

git fetch downloads updates from the remote repository without merging them into the local branch.

git pull downloads and merges updates into the current branch.

3. Merging Branches Using Git Merge
Purpose

To merge feature branches into the main branch.

Commands Used
git checkout main
git pull origin main
git merge addition
git merge subtraction
git merge multiplication
git push origin main

Explanation

git merge combines the history of a feature branch into the current branch.

This approach preserves the complete commit history.

4. Merging Using Git Rebase
Purpose

To create a clean and linear commit history.

Commands Used
git checkout subtraction
git rebase main
git checkout main
git merge subtraction

Explanation

git rebase moves the commits of one branch on top of another branch.

This results in a cleaner and linear commit history compared to merge.

Merge Conflict Demonstration
Creating a Merge Conflict

A merge conflict was intentionally created by modifying the same line in the same file (Add.java) in two different branches.

Change in addition branch
System.out.println("Addition Result = " + (a + b));

Change in subtraction branch
System.out.println("Sum is: " + (a + b));


Both changes were committed and pushed to their respective branches.

Identifying the Conflict

While merging branches into the main branch, Git displayed the following conflict markers:

<<<<<<< HEAD
System.out.println("Addition Result = " + (a + b));
System.out.println("Sum is: " + (a + b));
>>>>>>> subtraction


This indicates that Git could not automatically resolve the conflict and required manual intervention.

Resolving the Conflict

The conflict was resolved manually by selecting a final correct statement:

System.out.println("Final Addition Result = " + (a + b));

Commands Used
git add Add.java
git commit -m "Resolved merge conflict in Add.java"
git push origin main

---
## Final Outcome

All feature branches were successfully merged into the main branch.

Calculator operations are working correctly.

A merge conflict was intentionally created, identified, and resolved.

All required Git commands were executed and documented successfully.





