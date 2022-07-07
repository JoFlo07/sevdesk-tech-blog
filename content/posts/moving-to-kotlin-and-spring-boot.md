---
title: "Moving to Kotlin and Spring Boot"
date: 2022-06-09T11:58:42+01:00
featured_image: '/img/1622117103-ms00788.jpeg'
---


## Our beginnings in php

Historically, sevDesk is a Php shop. We started with Php and Zend 8 years ago. We adapted
Zend to fit our needs with a great persistence framework. We also added a lot of 
developer productivity features that made our lives easier. In terms of architecture the system is a pretty bigish monolith - perfect for a small team that we were a couple of years ago.

## Some problems

Php served us really well. But we slowly discovered a couple of problems.

###  Organizational growth

While the old system worked fine with one team it broke down when many teams worked with the codebase. That is not necessarily a Php problem, but a problem with the initial design of our monolith. We simply outgrew our wildest expectations.

### Framework
Zend is discontinued and we heavily modified the core for our needs. Moving to the sequel or to Symphony would roughly be a rewrite. If that's a rewrite then we could also move to another language / framework altogether.

### Talent
Finding senior Php talent was very hard for us. Especially finding developers that knew the difference between scripting a wordpress site and software engineering a large project.

## The alternatives

The alternatives for us were roughly:
- Staying with php but moving to Symphony. Cool: We know php really well and we'd be able to reuse some code.
- Using NodeJs and Express. Cool: Same programming language as in the frontend
- Kotlin and Spring Boot: Cool: Many new hires already knew Kotlin / Java and Sprint Boot. Finding talent seemed to be easy.

Of course there are downsides as well. In almost all cases we'd have to rewrite parts (or even all) of the application for the new language. Not a good place to be at. But sometimes rewrites have to be done - especially if a company is growing like ours.

## How to decide

The whole process was managed by our IT Architect in close collaboration with all teams. We knew that only if we could bring anyone into the boat the new system could be a success. That's why we ran multiple surveys and also made two large meetings with all engineers to talk about the topic. 

At the end the decision was pretty clear. Last place was NodeJs. First place was Kotlin and Spring Boot.

## Learnings

We made this decision one year ago. Since then we moved parts of our application to the new system. And we had some learnings already.

### Talent

Finding senior talent in Kotlin is no problem. All Java developers were happy to move to Kotlin.

### Architecture

In terms of architecture we are still on a monolith - but we are now using clean Domain Driven Design.
That approach allows us to create new services when we see the need for it. Our default is: Go with
the monolith, but split off when necessary.

### Language switch

The switch from Php and its ecosystem to Kotlin / Java and its ecosystem was a success. It was our top goal
that nobody would feel the need to quit sevDesk because of that tech decision. And nobody did. This was - by the way - also one of the reasons that we chose Kotlin over Java: Our Php pros really disliked Java, but were really happy to delve into Kotlin.

## Conclusion
After one year with our new stack we are quite happy with the choice. The rewrite to Spring Boot and Kotlin
enables a couple of really important things: 

- It supports the organizational growth
- It allows us to attract top talent
- It allows to continue our path towards continuous deployment and ultra high quality software

To be clear: All of that would have been possible with Php as well. Php is not a bad language. But for the reasons listed above we think that Spring Boot and Kotlin is a better decision for our company.

Your mileage may vary...

