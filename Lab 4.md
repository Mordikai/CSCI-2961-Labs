#Lab 4
###9/25/2015

####FreeBSD Documentation
* The first step was installing Tortoise SVN, which took me a couple tries to determine proper usage.
* On line 3600 of 'disks\chapter.xml', I found the sentence `The administrator must decide which node has more important changes or merge them manually.`
* I then clarified the phrasing a little. `The administrator must either decide which node has more important changes, or perform the merge manually.`
* I've now generated `ch17tiny.patch`, and, after making a bugzilla account, submitted the patch file for consideration. My submission is here: https://bugs.freebsd.org/bugzilla/show_bug.cgi?id=203340

The only reason for me to perform this change, minor as it may be, is to add a modicum of clarity to the documentation. If the documentation for a given project is clear, straightforward, and complete, then the userbase can get much more out of the project than they would otherwise. Additionally, from the development side, any further changes to the project are expidited by the existence of such a body of knowledge.

####The Debate
Our debate from last class was a fairly well-rounded comparison of Open vs. Closed Source, though perhaps lacking in participation.
On the side of Open Source:
* Free software directly benefits the common good
* Community may contain project developers, who can provide assistence to those that need it
* Able to adapt quickly to new issues
* More customizable for a user possessed of discerning taste and a sufficient knowledge
On the side of Closed Source:
* Indirectly benefits the common good via philanthropy(e.g. Bill and Melinda Gates Foundation)
* Frequently possessed of well-designed, idiot-proof interfaces
* Formal management of the development team results in higher quality compared to Open Source after you pass a certain threshhold project size
* Often required by the industry, due to proprietary formats

I definitely think that Open Source provides more benefits to an individual, while Closed Source provides more benefits to a company. Open Source is free for use, customization, contribution, and distribution. It (usually) comes with an experienced community of both users and developers to learn from, and tends to have minimal legal baggage if any at all. For an unafilliated developer or a small team, this cuts costs, and provides important resources for them to draw from. On the other foot, Closed Source tends to have a better interface, a robust and idiot-proofed design, and is often the only good way to acheive a given industry standard(though this is an intentional limitation), all of which suit a large company.

Regardless of my hypothetical situation, I would choose Open Source. For a side project, I would be able to draw from another's work to serve as a starting point for my own, in addition to the reasons I've listed above. Were I in charge of a company's vendor choice, I would go with Open Source software for most purposes in order to reap the same benefits, save for where proprietary software would be a necessity to meet industry standards.
