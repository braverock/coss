Contributing to Open Source Software
================
Soumya Kalra and Brian G. Peterson

-   [Introduction](#introduction)
-   [Getting Started](#getting-started)
    -   [*Documentation*](#documentation)
    -   [*Testing*](#testing)
    -   [*Bug Reports*](#reports)
    -   [*Small New Features*](#features)
    -   [*Porting Code to a Different Language*](#porting)
    -   [*Replicating Published Research*](#replicating)
    -   [*Writing Plugins, Libraries, or Packages*](#packages)
-   [Why Companies Should Contribute to Open Source](#why-companies-should-contribute-to-open-source)
-   [Colophon](#colophon)
-   [Resources](#resources)

Introduction
============

This essay hopes to be a gentle introduction to contributing to open source software. The authors work in finance, and write open source software mostly in R (R Core Team 2014), though we have previously contributed to open source ecosystems across many industries (Finance, Customer Service, Telecommunications, Enterprise Resource Planning, Cryptography) and languages (R, C, C++, Java, matlab, perl, PHP). As such, we hope that this essay is useful in a general sense to those wishing to find ways to contribute to open source software ecosystems.

It is important to note that we are not the first people to grapple with the issues around contributing to open source. Eric S. Raymond's classic *The Cathdral and the Bazaar* (2008) looks at the contrast in software produced by loosely coupled team (the "bazaar") differs from the process for a centrally managed team (the "cathedral") through the lens of a long-time software guru and open source contributor's creation of the fetchmail project. Karl Fogel takes a more process oriented view in *Producing Open Source Software* (2017), looking at the organizational and management effects of running a project containing more than a few people. Both are excellent, and highly recommended reading.

We hope to cover narrower ground.

Our goal is to look at individual contributions, and as a possible extension, how those individual contributions may fit into contributions while at work, with the blessing of your firm or employer. We will cover the possible evolution from individual contributions to employer-sponsored teams and team contributions, but that is not our overall focus. We will try to point to external resources along the way to help a potential contributor be more successful in their desire to contribute to open source.

Getting Started
===============

Raymond writes that "Every good work of software starts by scratching a developer's personal itch." Most new contributors to open source don't start by creating a large project with a team and releases and hundreds of pages of documentation. Most new contributors start small. Some of those avenues, in roughly increasing order of complexity:

-   <span id="documentation">documentation</span>
-   <span id="testing">testing</span>
-   <span id="reports">bug reports</span>
-   <span id="features">small new features</span>
-   <span id="porting">porting code to a different language</span>
-   <span id="replicating">replicating published research</span>
-   <span id="packages">writing targeted plugins, libraries, or packages</span>

Anyone can contribute to open source. Individuals who are not programmers, data scientists, or data analysts can contribute bug reports, documentation, and testing directly to existing open source projects. Non-developers also often have other talents in communications, design, writing, or networks that may be useful to an open source ecosystem. Just because you are not a "coder" doesn't mean that you have nothing to contribute.

*Documentation*
---------------

-   past you
-   future you

*Testing*
---------

All Code Has Bugs.

At least, all code (probably) has (a) bug(s) (somewhere). Generally, the best that may be hoped for is that the bugs are small, isolated to infrequent circumstances, and in a portion of the code that doesn't have major painful implications if it breaks in a production process.

The way to push the (remaining) bugs into low-impact corners is through testing.

If you have found a bug in open source software that you want to report, and potentially help fix, see <span id="reports">Bug Reports</span>, below.

Both manual and automated tests are important, but we'll start with manual testing.

-   expected inputs and outputs
-   unexpected inputs and bounds testing

*Bug Reports*
-------------

**Bug Resources:**

-   [Principles of Good Bug Reporting](http://qablog.practitest.com/principles-of-good-bug-reporting/)
-   [Stack Overflow: How to create a Minimal, Complete, and Verifiable example](https://stackoverflow.com/help/mcve)
-   [Short, Self Contained, Correct (Compilable), Example](http://sscce.org/)
-   [Stack Overflow: How to make a great R reproducible example?](https://stackoverflow.com/questions/5963269/how-to-make-a-great-r-reproducible-example)

*Small New Features*
--------------------

-   adding to an existing function
-   creating a new function
-   fixing existing issues/bugs
-   compiling data sets

*Porting Code to a Different Language*
--------------------------------------

All sorts of people and organizations publish code. Unfortunately, many times that code is in a language other than your preferred language. Or, less usefully, "code" is really pseudo-code, and may not be executable at all, or may depend on commercial libraries to function.

The answer to this particular itch can be to port that code to a language of your choice.

This often ties into a larger effort of <span id="replicating">replicating published research</span>.

Whether as part of replication or not, porting code can be am accessible way of contributing. You have a piece of code that can presdumably be <span id="testing">tested</span>, you want that code in another language. You assume that some other user of your target language may also want that code.

When porting the code of others, you should always attribute *your* code as being derived from the original. This should include notes in the comments, in the documentation, and in any other references or bibliography that your work contains. You want to point people to the original source. You also want to make clear where you've chosen to deviate from the original source. Often porting code finds bugs in the original, but does not invalidate the original work. Reporting those bugs can help everyone. Often you will add features to better suit your use-case. This is part of the natural evolution of open source.

Also take care with the license the original code is released under. A full discussion of licensing, and the debates that can go along with licensing, is outside the scope of this document. It is important to note that if you plan to change the license of the original code, in most cases you need to choose a compatible license. You may also need to choose a license that is compatible with the software stack you are trying to extend or use, at least if you plan to distribute your code as open source.

**Licensing Resources**

-   [Open source licensing: What every technologist should know](https://opensource.com/article/17/9/open-source-licensing)
-   [Choose an Open Source License](https://choosealicense.com/)
-   [About Open Source Licenses](https://opensource.org/licenses)

*Replicating Published Research*
--------------------------------

Replication is core to good science. An experiment that can't be replicated also can't be verified, and therefore can't be relied upon. If you find published research that looks applicable to some problem you are facing, and want to implement it, the next reasonable step is to look for code. Unfortunately, the vast majority of papers are published without code and data, or are published in a language that you don't use in your own research that then needs <span id="porting">porting</span>.

By definition, the ideas contained in a published paper can't be trade secrets, and are rarely covered by patents or other encumbrances. As such, this is often a good hook to get your employers excited about contributions to open source, since it isn't viewed as 'competitive' to what you're doing internally, but can be very useful to work that you later apply in a proprietary and confidential fashion.

Replication of a published paper can provide an opportunity to publish in a journal such as [ReScience](http://rescience.github.io/), which is dedicated to open source replication of published research.

One of us (Brian) has written an essay with a process for replicating published research which is somewhat focused on quantitative finance, but should also have broader applicability to anyone wishing to replicate papers.(Peterson 2016)

*Writing Plugins, Libraries, or Packages*
-----------------------------------------

Why Companies Should Contribute to Open Source
==============================================

The software world has experienced a huge rise in open source offerings in the last 20 years. As the open source software stack for all levels of technical architecture has matured, solutions that are credible in the enterprise have emerged. At this point, almost all firms are using open source software *somewhere* in their architecture, whether through Linux servers, or through JavaScript widgets on their website, or in their data science and analasys stack. It seems clear that in many areas, companies of all types have seen the value in *using* open source software as a complement or alternative to commercial offerings of custom development.

Open source can feel somewhat more ‘raw’ than their commercial counterparts. Functionality is driven by a community process, so features are developed as people and companies using the software feel the need to develop them. This can leave gaps in functionality. On the other hand, Open source software has no licensing costs, and community development eliminates vendor lock-in and planned version obsolescence. It is our opinion that open source is mature enough that it provides an attractive alternative to commercial software or a complete custom application development effort.

We feel that contributing documentation, testing, bug fixes, and new features to open source software your firm depends upon is a virtuous cycle.

Companies that are users of open source can benefit from contributing to the open source ecosystems that they depend on. As described above for individual contributors, companies can facilitate all those contribution modalities by their employees. The firm benefits by having contributions accepted into the main body of software, reviewed by the community, and having a larger group of users finding and fixing bugs. Maintenance burdens are distributed among the community.

Companies can also gain reputational advantages by contributing. Major technology firms including Microsoft, Google, Red Hat, and Facebook have all allowed their employees to publish papers, contribute to open source code, and author new software in the open source ecosystem. This contributes to employee loyalty, makes recruiting top talent easier, and improves the reputation of the firm in that area of inquiry.

<!-- NOTE: there are a million news articles about this, we should link to them -->
We encourage firms to be open to contributing to open source, and to allowing their employees to contribute. Intitial steps can be small, in an area where the contribution is clearly non-proprietary, and where it will impact code that the firm is already using. A firm policy on things like bug fixes is relatively easy to create and enforce. A broader policy on what types of work on open source are permitted, and how approvals should be granted will take more work but we feel that work is often rewarded.

Colophon
========

This essay is a work in progress, and we welcome ideas and suggestions.

This document is rendered into LaTeX and HTML using *rmarkdown* (Xie 2014)

The BibTeX bibliography file is managed via [JabRef](http://jabref.sourceforge.net/).

------------------------------------------------------------------------

©2018 Soumya Kalra & Brian G. Peterson

![](cc_by.png)

This work is licensed under a [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/)

The contents of this essay do not necessarily reflect the ideas or policies of the authors employers, and do not imply that our employers have endorsed it in any way. We provide this work in the hope that it will be useful, and without warranty or assurance of any kind.

Thank you for your attention.

Resources
=========

Fogel, Karl. 2017. “Producing Open Source Software: How to Run a Successful Free Software Project.” Sebastopol: O’Reilly. <https://producingoss.com/>.

Peterson, Brian G. 2016. “Research Replication.” DV Trading, University of Washington. <https://www.researchgate.net/publication/319298241_Research_Replication>.

R Core Team. 2014. *R: A Language and Environment for Statistical Computing*. Vienna, Austria: R Foundation for Statistical Computing. <http://www.R-project.org/>.

Raymond, Eric S. 2008. “The Cathedral and the Bazaar: Musings on Linux and Open Source by an Accidental Revolutionary.” Sebastopol: O’Reilly Media, Inc. <http://gbv.eblib.com/patron/FullRecord.aspx?p=443450>.

Xie, Yihui. 2014. “R Markdown — Dynamic Documents for R.” <http://rmarkdown.rstudio.com/>.
