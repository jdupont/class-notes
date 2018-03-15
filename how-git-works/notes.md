# [How Git Works](https://www.pluralsight.com/courses/how-git-works)

## Git Internals:

+ Everything represented (identified) by a SHA1
    + SHA1 based on content (which is hashed)
    + When content changes, identitifier changes (because SHA1 changes)
+ Four types of objects
    + Blob
    + Tree
    + Commit
    + Tag
+ References
    + Branches are references to a particular commit
    + Tag is a branch that doesn’t move
    + Head is a reference to a branch or a commit (latter is called a detached head)
+ Garbage collection
    + Objects that can’t be reached through a reference (branch, tag, or HEAD) can and will be deleted
    + So data can disappear (!!!)

## How Those Transfer Over to Git Usage:

+ Operations are based on compositions of objects
    + Merge -- commit with two parents
    + Rebase -- change parent of some commit
+ Commit points to a state of the object database at a given point in time
    + Object identifiers change based on content changes
    + Commit points to a set of identifiers to describe the content at a particular point in time

## Takeaways

+ Changes in my current practices
    + Try using command line instead of GUI
    + Great new conceptual understanding of branching, merging, and rebasing, which will allow me to manage a project as best as possible
+ More to learn:
    + Advanced commands
    + Workflows
+ Would recommend this training enthusiastically
+ Possible follow-up training: Mastering Git (Paolo Perrotta)

