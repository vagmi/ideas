## Hubban - Kanban board for github issues

I love github and its issues. But the problem is that it is an issue tracking system and not very good at planning. 
I often use trello but I would like to have my issues in one place. Hubban, for the lack of a better name is a kanban
style board for github issues. Once you sign up with github, you can create multiple boards and add multiple projects
to each board. Usually, we tend to split our projects on github based on deployment units. For example, you might have
a server component in one repo and an android/web project which consumes it in another repo. Hubban lets you integrate
both into one view.

It would have the same semantics as cards and lanes. You can configure the number of lanes and name them and design your
own workflow. Each card will map on to one or more issues across repositories. We will use the github API to synchronize
between the issues on the cards. Also while pair programming or multiple people working on a feature will have more than
one assignee on to a card and one for the actual GH issue.

This is largely scratch my own itch sort of a project but I believe this has potential.
