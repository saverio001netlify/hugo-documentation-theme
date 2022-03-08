---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Arista Exercises"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2022-03-02T10:30:31+01:00
lastmod: 2022-03-02T10:30:31+01:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

### Exercise 1
Confiugre BGP peer groups with dynamic peers. \
Redistribute selected static and IGP routes.
- Use the `network` command
- Use the `redistribute` command
- Use `ecmp-fast`, which causes the router to ignore the active-best rule.

### Exercise 2
On page 186 of the slide, there is a weird BGP-LU example where
the route reflector allocates labels and seem to change nh. \
This is totally wrong.

Build this:

                  10.100.0.0/30   AS65000   10.100.0.4/30
    [SRX1]-ge-0/0/1-----------eth1-[EOS]-eth2----------ge-0/0/1-[SRX2]
                  .2   br1  .1             .5   br2  .6


**Built**, using two vSRXs as PEs. \
But the EOS route-reflector refused 
to re-advertise LU prefixes. 



