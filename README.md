# What is this?

A JavaScript technology that uses [D3](https://d3js.org/) to make a timeline from a simple text file.  The timeline code is maintained in 
this repository ([github.com/timelinez/timelinez.github.io/](https://github.com/timelinez/timelinez.github.io/)) on GitHub who kindly serve it up for web access  
on [timelinez.github.io](https://timelinez.github.io). It plucks a GitHub organization (or user) out of the domain, and the repo-name out of the anchor of the URL (if present - the bit to the right ot the '#') to extract data for a visual timeline. 

Here's a reference timeline on JFK's presidency (sibling repo to this one): 

* As you you would view it: [timelinez.github.io#jfk](https://timelinez.github.io#timelinez/jfk) (using this technology). 
* The source for that is in this repo: [github.com/timelinez/jfk](https://github.com/timelinez/jfk) 
* The main timeline file in that repo is [github.com/timelinez/jfk/blob/master/main.txt](https://github.com/timelinez/jfk/blob/master/main.txt) (editable in situ).

As mentioned, that repo is a sibling one inside the `timelinez` GitHub "organization". The intention is for multiple separate organizations to exist for various groups/agendas.

One built into this GitHub repo is about Sun/Oracle's patronage of Java (the programming language): 

* Timeline visual: [timelinez.github.io](https://timelinez.github.io) 
* Source for that: [github.com/timelinez/timelinez.github.io/blob/master/main.txt](http://github.com/timelinez/timelinez.github.io/blob/master/main.txt).

Here's an excerpt from the source for the JFK timeline:

```
1963-11-22 – President Kennedy and Texas Governor John Connally are shot in Dallas, with President Kennedy dying from his injuries.
```

## Why?

We're in an age where opposing political forces have different accounts of what did or did not happen. A Merkle tree 
[[↗]](https://en.wikipedia.org/wiki/Merkle_tree) with widely shared SHA1s is solid evidence one way or the other on the 
account of events. Git is a very solid history retaining Merkle tree. GitHub (and equivalents) are very solid portals for 
Git repo curation.

Groups, organizations and individuals can keep their own public Gi-backed Merkle tree timelines to help reinforce their 
account of events. Accounts of events that in a small way support democracy and honesty.  

# What is the reason for the GitHub-backed aspect to this?

## Because Git is a nearly perfect history-retaining merkle tree. 

Changes made to a timeline should be inspectable 
by all and Git's history as presented by GitHub make that easy and polished. Not only that, timelines could receive
contributions from anyone, including anonymous people, and subject to approval those contributions become accepted.
Changes to a timeline (as anything held in Git) can't be modified after the event without that being evident in 
the Git history. This is a useful feature of a system that wants position itself as canonical and trustworthy.

Say you were trying to maintain **the** canonical timeline for JFK's assassination, and wanted to represent that there was
a "second shooter" on the grassy knoll in downtown Dallas. You could maintain your claims in a text file like so: 

```
1963-11-22T12:30 – Second shooter fires shot at JFK's limo.
1963-11-22T12:30 – Second shooter packs up and leaves the grassy knoll
1963-11-22T12:36 – Second shooter catches bus to Plano, TX
```

As long as someone else (or some other org) has noted the SHA1 hash of the whole repo at a moment in time, then there's a witness to the 
fact that this timeline exists and has not been tampered with. Entries may of course be rewritten, revised or 
tweaked, but as long as the SHA1 is still in the history then it can be claimed that tampering did not happen. To be 
clear tampering is defined here as history being changed in a way there "no I/we did not say that" can't happen when 
the Git history say that it did. Say you messed up and implicated Philipp Oswald [[↗]](https://en.wikipedia.org/wiki/Philipp_Oswald) (born 1986, Austrian tennis player) 
as he who shot JFK (shooter #1, for your purposes), but realize six months later that you'd made a mistake and it as 
in fact Lee Harvey Oswald [[↗]](https://en.wikipedia.org/wiki/Lee_Harvey_Oswald). There may have been dozens of other legitimate changes to the timeline before this mistake 
was noted, so you should simply make the change to the latest version of the timeline and not the correction in the 
commit message, making it non-controversial. This would be similar to retractions in newspapers.

The Git feature "force push" is how history can be destroyed, so turn that OFF in the GitHub (or GitLab) project definition 
(protect the master branch). Also don't check in PDFs as researchers have proven SHA1 is not safe for PDFs [[↗]](http://shattered.io/) if someone has 
sufficient funds to spend on computing power to make a second PDF have the same SHA1 of the first.

## Because you trust GitHub (Microsoft)

1. To not tamper with the Git history itself
2. To not mis-represent anything during the serving and navigation of the timeline, despite some source being "open" (this repo)

# Making your own timeline

If you're interested in making your own timelines, take a look at 
[github.com/timelinez/jfk](https://github.com/timelinez/jfk) and make something similar in a new repo for your GitHub org (or user). Don't 
use "fork" for that as you're not going to keep abreast of the small amount of JFK data - your's will not just be wholly divergent, it won't have 
any common history at all.

Fork this repo too and maintain divergence with it. It should be forked into a `&lt;orgOrUserName&gt;.github.io` repo name, so that technology 
around the same origin policy (see "snafus" below) works.

Editing your timeline can be done through GitHub's web interface. You can process your own contributions using 
GitHub's Pull-Request system. Remember that you can have more than one .txt timeline in the same repo, and each will have a strong URL of its own.

# Features yet to add (contributions welcome)

1. Links to - other pages (should be markdown style)
1. "Drill in" to other/adjacent timelines (like "see JFK death")
1. Allow the overlay of HTML version of markdown source named in a link
1. Markdown Links - both "Drill in" to another timeline, and to regular pages, like "see JDK death ↗"
1. Live bookmarkable URL - as you move up and down the timeline, the URL changes to allow you to send that to someone else and they get to the same page.
1. Make sure that time line renders well in narrower page widths
1. Show SHA1 at time of serving, in case the pa
1. Show local rendering of date and time - e.g. 25th December 2018 2:05PM 
1. Show similar date/time entries from smushing into each other
1. InfiniScroll
1. Zoom in / zoom out
1. Arrowhead triangle is a little busted.

# Small snafus

1. PDFs in the repo being subject to shenanigans. Refer to [shattered.io](https://shattered.io). You can't even put their SHA1s in the Git repo and keep the binary without someone claiming the possibility of fakery.
2. The Web's "Same Origin Policy" [[↗]](https://en.wikipedia.org/wiki/Same-origin_policy) means that you have to fork this repo, including the JavaScript code rather than to referto the HTTP hosted JavaScript/CSS. You then have to keep abreast by pulling changes from "upstream" as you also maintain divergence.
