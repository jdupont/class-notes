# Talks & Presentations

Some of the software content I watch doesn't fit into the class or training category. For example, podcasts and 
talks at conferences don't lend themselves well to the notetaking I usually do for classes.

But, I'd still like to keep track of what I'm watching and the main ideas of each talk, so I'll do that here.

## Career Development

+ [Common Pitfalls of Junior Developers](https://www.youtube.com/watch?v=tYOx8mA5p2c)
    + _Speaker_: Rachel Warbelow
    + _Watched_: 3/17/2018
    + Short talk about some of the common problems faced by junior developers. Mostly targeted towards potential
    mentors and teachers, not towards junior developers themselves.

## DevOps

+ [How Netflix Thinks About DevOps](https://www.youtube.com/watch?v=HmM4V33ReCw)
    + _Speaker_: Dave Hahn
    + _Watched_: 3/15/2018
    + Describes how Netflix relies on company culture and personal ownership of code to keep everything inside 
    Netflix working smoothly (as opposed to creating a bunch of specific DevOps processes and procedures). Also
    had some interesting numbers about Netflix as a company.
+ [What can programmers learn from pilots?](https://www.youtube.com/watch?v=we4G_X91e5w)
    + _Speaker_: Andrew Godwin
    + _Watched_: 3/15/2018
    + Describes how aviation has managed to make flying very safe when compared to the inherent dangers of being in
    the air. Very interesting points about concepts like excessive errors and warnings (which ultimately get
    ignored), the importance of checklists and process, and the importance of performing post-mortem investigations
    and analysis when things go wrong.

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

## The Future of Computing

+ [The Birth & Death of JavaScript](https://www.destroyallsoftware.com/talks/the-birth-and-death-of-javascript)
    + _Speaker_: Gary Bernhardt
    + _Watched_: 3/18/2018
    + Excellent talk. The premise is that the talk happens in the year 2035 and consists of the speaker recounting the
    history of computing from 1995 to 2035. So, the talk starts off with a brief history of JavaScript, and then 
    describes how Web Assembly and asm completely revolutionize how programming works. Very interesting talk -- I highly
    recommend it.
    
+ [The Future of Programming](https://www.youtube.com/watch?v=8pTEmbeENF4)
    + _Speaker_: Bret Victor
    + _Watched_: 4/17/2018
    + Very interesting premise about peering into the future of computing from the viewpoint of 1973, and seeing how those
    predictions match up with the next 40 years.
    
## Software Design

+ [Simple Made Easy](https://www.infoq.com/presentations/Simple-Made-Easy)
    + _Speaker_: Rich Hickey (author of Clojure)
    + _Watched_: 4/9/2018
    + This talk was action-packed. The first part focused on the difference between simple (concerning only a limited
    number of things, i.e. not complex) and easy (familiar or related to what you already understand). According to Rich
    software should be simple, but not necessarily easy. By keeping software simple, you limit the potential effects of
    future changes; by keeping it easy, you just make things go more smoothly for other developers in the short term.
    Then, the talk moves to the idea of constructs versus artifacts. Programmers use constructs (code and tools) to make
    artifacts (programs). Programmers tend to care a lot about constructs, but users only care about artifacts (as long as
    it works, it doesn't matter to the user how/why it works). Then Rich discusses various techniques for making projects
    simple (like avoiding state, which makes sense given that he's the author of a functional language). This was interesting
    food for thought.
+ [Simplicity Matters](https://www.youtube.com/watch?v=rI8tNMsozo0)
    + _Speaker_: Rich Hickey (author of Clojure)
    + _Watched_: 4/11/2018
    + This talk was a follow-up to [Simple Made Easy](https://www.infoq.com/presentations/Simple-Made-Easy). A lot of the fundamental
    ideas were repeated, but Rich then expanded on more approaches for building simple software. He discussed sources of complexity,
    such as state, time, and order, and then discussed ways to eliminate them. Great talk!
+ [Hammock Driven Development](https://www.youtube.com/watch?v=f84n5oFoZBc)
    + _Speaker_: Rich Hickey (author of Clojure)
    + _Watched_: 4/12/2018
    + Great talk about the importance of design and upfront problem solving in programming. Rich discusses how and why upfront
    design has gotten a bad name. Rich then goes into a discussion of various problem-solving strategies, focusing especially on
    taking time to allow deep thought on a problem.
+ [Get a Whiff of This](https://www.youtube.com/watch?v=PJjHfa5yxlU)
    + _Speaker_: Sandi Metz
    + _Watched_: 4/21/2018
    + Great talk about what a code smell is (a very specific indication of a defect), what a refactoring recipe is (a way
    to fix a specific code smell), and how knowledge of the two can help improve your programs.
+ [Rules](https://www.youtube.com/watch?v=npOGOmkxuio)
    + _Speaker_: Sandi Metz
    + _Watched_: 4/21/2018
    + Sandi Metz describes an OOP approach favoring many small objects, with a set of rules for writing programs in this style.
+ [Nothing is Something](https://www.youtube.com/watch?v=OMPfEXIlTVE)
    + _Speaker_: Sandi Metz
    + _Watched_: 4/23/2018
    + Great talk about identifying hidden abstractions and leveraging those to improve designs. Sandi spends a while discussing how 
    abstractions are hidden throughout code (like those hidden by the keyword `if`). She wraps up with a discussion of how
    inheritance can be dangerous, and how composition can lead to better designs.
+ [What does it mean to be R    eactive?](https://www.youtube.com/watch?v=sTSQlYX5DU0)
    + _Speaker_: Erik Meijer
    + _Watched_: 5/3/2018
    + Meijer applies mathematical precision to programming concepts.

## Debugging

+ [Debugging with the Scientific Method](https://www.youtube.com/watch?v=FihU5JxmnBg)
    + _Speaker_: Stuart Halloway
    + _Watched_: 4/10/2018
    + Well, this talk featured debugging advice from House M.D., which is a great start. The presenter talked about debugging
    methodically, starting with a hypothesis, then an experiment, and then a revaluation of the hypothesis (and iterating
    until that leads to a fix).

## Testing

+ [The Magic Tricks of Testing](https://www.youtube.com/watch?v=URSWYvyc42M)
    + _Speaker_: Sandi Metz
    + _Watched_: 4/24/2018
    + Sandi discusses why unit tests can become so painful so quickly, and then talks about what characterizes good tests (thorough,
    fast, and robust). Then, Sandi talks about what to test in order to avoid repeating yourself (which contributes to slow, fragile
    tests).

## Containers

+ [Demystifying Docker](https://www.youtube.com/watch?v=GVVtR_hrdKI)
    + _Speaker_: Andrew Baker
    + _Watched_: 4/18/2018
    + Great introduction to the basics of Docker. Does a good job of explaining the needs filled by Docker and why you'd want
    to start incorporating Docker into your own workflows.

## Functional Programming

+ [Running a Startup on Haskell](https://www.youtube.com/watch?v=ZR3Jirqk6W8)
    + _Speaker_: Bryan O'Sullivan
    + _Watched_: 4/28/2018
    + Interesting talk about using Haskell in a 3 person startup. Sounds like Bryan O'Sullivan re-invented the wheel for a lot of
    things that would have been available already in other languages, but he also says that they see high performance and low
    defect rates which he attributes the Haskell's language facilities.

## Language Design

+ [Why C++ Sails When the Vasa Sank]()
    + _Speaker_: Scott Meyers
    + _Watched_: 4/29/2018
    + Interesting talk about C++'s longevity. Scott Meyers gives a number of reasons why C++ became popular and has stayed popular.
    He also makes some commentary on the future of C++ and how the language might grow.

## Node.js

+ [Node.js Explained](https://www.youtube.com/watch?v=L0pjVcIsU6A)
    + _Speaker_: Jeff Kunkle
    + _Watched_: 4/30/2018
    + Great talk about the conceptual underpinnings of Node (i.e., the advantages of nonblocking programming for I/O intensive operations).
