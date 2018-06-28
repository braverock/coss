Contributing to Open Source Software
================
Soumya Kalra and Brian G. Peterson

-   [Introduction](#introduction)
-   [Getting Started](#getting-started)
    -   [*Documentation*](#documentation)
    -   [*Bug Reports*](#reports)
    -   [*Testing*](#testing)
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
-   <span id="reports">bug reports</span>
-   <span id="testing">testing</span>
-   <span id="features">small new features</span>
-   <span id="porting">porting code to a different language</span>
-   <span id="replicating">replicating published research</span>
-   <span id="packages">writing targeted plugins, libraries, or packages</span>

Anyone can contribute to open source. Individuals who are not programmers, data scientists, or data analysts can contribute bug reports, documentation, and testing directly to existing open source projects. Non-developers also often have other talents in communications, design, writing, or networks that may be useful to an open source ecosystem. Just because you are not a "coder" doesn't mean that you have nothing to contribute.

*Documentation*
---------------

-   past you
-   future you

*Bug Reports*
-------------

One of the earliest places that people contribute to open source ecosystems is through reporting bugs that they find as users.

If you want the open source community to quickly help fix your bug, you should endeavor to make it easy for the developers (whether or not you are one of those developers) to replicate your error (and thus verify that the error is fixed after changing something). We've included a few in-depth resources, below, on reporting bugs, but here are the basics.

-   describe what you were trying to do, and what you expected to happen
-   construct and proved a minimal reproducible example
-   describe your environment

It is very hard for developers to do anything with a report that says little more than "this feature is broken".

Start by trying to make a clear description of what you were doing when the suspected bug occured, and what you expected. Make sure to clearly describe any errors that the software gave you, or any odd output from the code you were attempting to use.

Construct a minimal resproducible example. The smaller the example is, the easier it is for a developer to replicate and verify the bug. There are many resources online describing how to do this. Your goal should be to use the smallest set of steps or amount of code and data to replicate your problem that you can manage. Often, the process of attempting to create a repeatable example will either identify the problem, or make clear that something else is wrong, so this step is key.

Don't forget to describe your environment. Your operating system, software stack, and library or package versions all have an impact on finding the bug.

If you are running an older version of the software, make sure to test on a newer version, as the bug may already have been fixed in the newer version. Also, before reporting a bug, search the bug reporting system for a similar bug to yours, and try to make sure you're not reporting a duplicate bug.

If you find yourself testing the same features or functions over and over again, consider writing testing scripts or automated tests, see <span id="testing">Testing</span>, below.

Developers really appreciate good bug reports. Try to give them something useful, and you should be rewarded.

**Bug Resources:**

-   [Principles of Good Bug Reporting](http://qablog.practitest.com/principles-of-good-bug-reporting/)
-   [Stack Overflow: How to create a Minimal, Complete, and Verifiable example](https://stackoverflow.com/help/mcve)
-   [Short, Self Contained, Correct (Compilable), Example](http://sscce.org/)
-   [Stack Overflow: How to make a great R reproducible example?](https://stackoverflow.com/questions/5963269/how-to-make-a-great-r-reproducible-example)

*Testing*
---------

All Code Has Bugs.

At least, all code (probably) has (a) bug(s) (somewhere). Generally, the best that may be hoped for is that the bugs are small, isolated to infrequent circumstances, and in a portion of the code that doesn't have major painful implications if it breaks in a production process.

The way to push the (remaining) bugs into low-impact corners is through testing.

If you have found a bug in open source software that you want to report, and potentially help fix, see <span id="reports">Bug Reports</span>, above.

Both manual and automated tests are important, but we'll start with manual testing.

Manual testing is fundamentally a process of creating checklists. Atul Gawande (2010) , in *The Checklist Manifesto*, examines the many ways that having appropriate checklists can improve consistency and reduce errors in multiple different fields and endeavors. Software testing is no different. Long before the possibility of automating software tests, formal software quality assurance teams used testing scripts or checklists to test key features of applications.

Anyone can create a software test. In its simplest form, a test is a list of expected inputs and expected (correct) outputs. To be more complete, test scripts for specific features should also try to feed incorrect inputs into a feature and verify that an appropriate error, warning, or failure mode is reached, an that the software does not return incorrect results and continue without notice. A collection of multiple tests is often combined into a formal *test plan*.

Tests are often created after a bug is located. These tests, once they exist, can be used to verify the corrected behavior of the software after the bug is fixed. If maintained and re-tested on new versions of the software, they can also be used to guard against *regression*, or the re-emergence of previously incorrect behavior in future versions of the software.

-   automated tests
-   testing tools, preferences
-   test coverage

Very few open source projects without corporate sponsors have dedicated testers. If you are not a developer, but a particular piece of code is important to you, then contributing testing reports, scripts, and if possible automated tests can have a positive impact on the stability and correctness of that code going forward.

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

Gawande, Atul. 2010. “The Checklist Manifesto: How to Get Things Right.” London: Profile Books.

Peterson, Brian G. 2016. “Research Replication.” Braverock Investments, University of Washington. <https://www.researchgate.net/publication/319298241_Research_Replication>.

R Core Team. 2014. *R: A Language and Environment for Statistical Computing*. Vienna, Austria: R Foundation for Statistical Computing. <http://www.R-project.org/>.

Raymond, Eric S. 2008. “The Cathedral and the Bazaar: Musings on Linux and Open Source by an Accidental Revolutionary.” Sebastopol: O’Reilly Media, Inc. <http://www.catb.org/esr/writings/cathedral-bazaar/cathedral-bazaar/>.

Xie, Yihui. 2014. “R Markdown — Dynamic Documents for R.” <http://rmarkdown.rstudio.com/>.
