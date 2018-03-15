# Talks & Presentations

Some of the software content I watch doesn't fit into the class or training category. For example, podcasts and 
talks at conferences don't lend themselves well to the notetaking I usually do for classes.

But, I'd still like to keep track of what I'm watching and the main ideas of each talk, so I'll do that here.

## DevOps

+ [How Netflix Thinks About DevOps](https://www.youtube.com/watch?v=HmM4V33ReCw)
    + _Speaker_: Dave Hahn
    + _Watched_: 3/15/2018
    + Describes how Netflix relies on company culture and personal ownership of code to keep everything inside 
    Netflix working smoothly (as opposed to creating a bunch of specific DevOps processes and procedures). Also
    had some interesting numbers about Netflix as a company.

## Numerical Computing

+ [Numerical Tools for Non-Experts](https://www.microsoft.com/en-us/research/video/numerical-tools-for-non-experts/)
    + _Speaker_: Pavel Panchekha
    + _Watched_: 3/12/2018
    + Describes a couple of cool tools for finding problems in floating point computations. It's easy to inadvertently 
    introduce defects in numerical by introducing innacuracy with floating points (e.g., underflow, loss of precision,
    etc). Pavel Panchekha presents one tool that compares floating point operations in compiled code (assembly) with the
    same computation executed with arbitrary precision arithmetic; if the results diverge, there has been a 
    floating point problem. Then Panchekha presents a second tool that can refactor the mathematical expression
    underlying the floating point operations to eliminate or mitigate the source of error. Cool!
