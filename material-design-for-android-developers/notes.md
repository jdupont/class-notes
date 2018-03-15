# [Material Design for Android Developers](https://www.udacity.com/course/material-design-for-android-developers--ud862)

## Lesson 1: Android Design Fundamentals

+ Density Independent Pixels (dips)
    + Multiple factors to consider when targeting a variety of devices
        + Physical size
        + Screen resolution
    + Dips abstract away the relationship between physical size and screen resolution so that the designer can think in general design terms even when pixel density changes
    + Devices can also be broken in density buckets for things where resolution does matter (e.g., icons)
+ Asset Crispness
    + Assets scaled for each density bucket
    + Preferable: vector graphics
+ View size
    + Content + Padding + Margin
+ Padding and content are part of the element
    + Clickable
    + Affected by element’s background changes
+ Margin is part of the parent view
+ Common Design Patterns
    + Toolbar
        + Ubiquitous
        + AppBar is a specific example
    + Tabs
    + Navigation Drawer
    + List to details view
        + List of items
        + Click on item to get to details
    + Themes and Styles
        + Style -- one element
        + Theme -- cascade to children

## Lesson 2: Surfaces

+ UI is composed of Surfaces, which should contain visual hints as to their affordances
    + Surfaces can create intuitive hierarchies
    + Surface can help differentiate between heterogeneous and homogeneous content types
    + Elevations create and differentiate between surfaces
+ Floating action buttons
    + Highlight one action
    + Make it constantly available to the user
+ Surfaces can react to touch
    + Radial ripples
    + Elevation change
    + Crucial for communicating feedback to the user
+ Transform surfaces with motion
    + For example, circular reveal
    + Communicates information about what is happening

## Lesson 3: Bold Graphic Design

+ Past user experience influences understanding of current UI
+ Grouping is key for communicating relationships between UI elements
    + 8 dp grid
    + Keylines for vertical and horizontal alignment
+ Dimension files
    + Centralize values for grids, grouping, and placement
    + Avoid magic numbers
+ Color
    + Highly encouraged
        + Make things pretty
        + More importantly, make things easier to understand
    + Color system
        + Primary color: your app’s personality (whimsical, serious, etc)
        + Accent color: emphasize certain elements
        + Shades of primary and accent to have some more variety
    + In Android
        + Colors.xml to unify color specs
        + In theme with colorPrimary, etc
+ Typography
    + Sp
        + Best practice unit
        + Allows user to customize font size

## Lesson 4: Meaningful Motion

+ Transitions
    + Lots of implementation details for Android
    + Probably can look this up as needed
+ Instructive Motion
    + How an element moves gives hints about how to interact with it
    + Common design language helps ensure that users are aware of these relationships
    + Goldilocks rule for length of animations
        + Too fast -- feels accidental
        + Too slow -- feels frustrating
        + Just right (suggested time is 300ms)
    + Motion should often (almost always) be user-initiated
+ Coordinate motion
    + If many items move, their motion should be coordinated
    + Otherwise, the motion appears chaotic and is confusing
+ Avoid accidental zoom by animating width and height at different rates
    + Remember to animate details too (like icons)

## Lesson 5: Adaptive Design

+ So many form factors
    + Screen size
    + Ratio
    + Devices (watches, etc)
+ Checklist of design goals to consider
    + Balanced use of space
    + Reading comfort
    + Image quality
    + Maintaining context
    + Aesthetic
+ Breakpoints
    + Dip points where layouts change as screen width changes
    + These should be content-first
    + On android, these can be implemented using resource qualifiers
        + Screen width
        + Screen height
        + Portrait/landscape
+ Techniques for adapting to screen size
    + Reveal: reveal content that was previously hidden (e.g., drawers)
    + Reflow: adjust layout to size (e.g., flow cards from single column to grid)
    + Expand: expand content and add margins (e.g., like my blog)
+ Android specifics
    + Layout include
    + Change values based on resource qualifiers

## Lesson 6: Constraint Layout

+ Multiple passes for render
    + Measure pass
    + Layout pass
+ Double taxation: multiple measure passes
    + Bad for performance
    + Can happen with constraint layout because first pass cannot definitively ascertain where elements belong
