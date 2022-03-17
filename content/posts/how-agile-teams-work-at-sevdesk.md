---
title: "How agile teams work at sevDesk"
date: 2022-03-17T11:58:42+01:00
draft: true
---

## End to end responsibility

A couple of months ago we re-organized most of our agile dev teams.

Our teams now have end-to-end responsibility which makes them much more autonomous. If you look at the frontend of sevDesk you’ll see different parts like “Invoices”, “ERP” and many more. One team now manages exactly one part of our app - from frontend over backend down to the database.

The teams themselves consist of members with different specialities: Product Owner, Agile Coach, Frontend Dev, Backend Dev and also UX/UI.

This make teams really powerful. They also got ownership over their part of the codebase and systems. And if you own something - you care a lot and make sure it works in the long run.

We call these teams “vertical” teams as they own one vertical slice of our application landscape.

## An exception to the rule

There is one team that does things differently. This team is our Platform Team. That team supports all other teams to bring their services live. It also makes sure that security is in place and all the basic network “wiring” is done properly (DNS/NAT etc). It’s not a vertical team, but a horizontal team.

The Platform Team works as an enabler for the other teams. It is there for all other teams in case of questions, but it does not run the systems for the teams. Normally, vertical teams are responsible to run their own services.

## The future

There are topics like “growth” or “internationalization” that span multiple teams. We could manage this this by using the POs of the teams to sync and distribute the topics to their teams. Sounds good. But is very slow in practice. Or we use horizontal teams that work on many parts of the application - together with our vertical agile teams.

We’ll experiment in the future with that setup. But for now we are happy with our agile setup :)


## More

 * Great book: “Team Topologies: Organizing Business and Technology Teams for Fast Flow” by Matthew Skelton and Manuel Pais