# What is this?

A JavaScript tech that uses [D3](https://d3js.org/) to make a timeline from a simple text file.  The timeline code is hosted in 
this (https://github.com/timelinez/timelinez.github.io/) repository and served by by the good people at Github 
on https://timelinez.github.io/. It plucks a Github organization (or user) and repo-name out of the anchor of the URL (the bit to the right ot the '#') to extract data for a visual timeline. 

Here's a reference timeline on JFK's presidency: 
[http://timelinez.github.io#timelinez/jfk](http://timelinez.github.io#timelinez/jfk) (shown visually with this technology). The source for that is here: [https://github.com/timelinez/jfk/blob/master/timeline.txt](https://github.com/timelinez/jfk/blob/master/timeline.txt) (very nearly plain text).

Here's another on Sun/Oracle's patronage of Java (the programming language): [timeline visual](http://timelinez.github.io) and [source for that](http://github.com/timelinez/timelinez.github.io/blob/master/reference.txt).

Here's a source excerpt for the JFK timeline:

```
1963-11-22 – President Kennedy and Texas Governor John Connally are shot in Dallas, with President Kennedy dying from his injuries.
```

# Why the Github-backed aspect to this?

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

As long as someone else has noted the SHA1 hash of the whole repo at a moment in time, then there's a witness to the 
fact that this timeline exists and has not been tampered with. Entries may of course be rewritten, revised or 
tweaked, but as long as the SHA1 is still in the history then it can be claimed that tampering did not happen. To be 
clear tampering is defined here as history being changed in a way there "no I/we did not say that" can't happen when 
the Git history say that it did. Say you messed up and implicated Philipp Oswald (born 1986, Austrian tennis player) 
as he who shot JFK (shooter #1, for your purposes), but realize six months later that you'd made a mistake and it as 
in fact Lee Harvey Oswald. There may have been dozens of other legitimate changes to the timeline before this mistake 
was noted, so you should simply make the change to the latest version of the timeline and not the correction in the 
commit message, making it non-controversial. This would be similar to retractions in newspapers.

The Git feature "force push" is how history can be destroyed, so turn that OFF in the Github project definition 
(protect the master branch). Also don't check in PDFs as Google has proven SHA1 is not safe for PDFs if someone has 
sufficient funds to spend on computing power to make a second PDF have the same SHA1 of the first.

## Because you trust Github (Microsoft)

1. To not tamper with the Git history themselves
2. To not mis-represent anything during the serving and navigation of the timeline, despite some source being "open" (this repo)

# Making your own timeline

You're interested in hosting your own timeline, in which case take a look at 
[https://github.com/timelinez/jfk](https://github.com/timelinez/jfk) and make something similar. Editing 
your timeline can be done through Github's web interface. You can process your own contributions using 
GitHub's Pull-Request system.

# Features yet to add (contributions welcome)

1. Links to - other pages (should be markdown style)
1. "Drill in" to other/adjacent timelines (see JDK death)
1. Allow the overlay of HTML version of markdown source named in a link
1. Markdown Links - both "Drill in" to another timeline, and to regular pages (see JDK death)
1. Live bookmarkable URL - as you move up and down the timeline, the URL changes to allow you to send that to someone else and they get to the same page.
1. Make sure that time line renders well in narrower page widths
1. Show SHA1 at time of serving, in case the pa
1. Show local rendering of date and time - e.g. 25th December 2018 2:05PM 
1. Show similar date/time entries from smushing into each other
1. InfiniScroll
1. Zoom in / zoom out
