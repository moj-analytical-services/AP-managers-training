# 4. Quality assurance and code storage with git and GitHub

## What are our coding standards?

Maintaining high quality code is an important part of analytical quality assurance.

It helps to promote readable, understandable code with fewer bugs.  A separate website has been developed [here](https://moj-analytical-services.github.io/our-coding-standards/) with a set of coding standards for analysts at the MoJ.


## How can you ensure appropriate analytical quality assurance on your project?


# Not actually sure what the current state of guidance is here?!







## Why should I use GitHub, and how does version control work?

Github is a central place to store our analytical projects - particularly those which are built primarily in code.  All analytical work done on the analytical platform should be stored on Github.

### How do I use Github?

There is a guide to using Github in the platform user guidance, which can be found [here](https://user-guidance.services.alpha.mojanalytics.xyz/github.html#using-github-with-the-platform)


### What are the benefits?

Github keeps track of who wrote what, when, why they wrote it, why we can trust its correctness, and which version of the code was run to produce an analytical result.  You can read more about the benefits of using Github in the user guidance [here](https://user-guidance.services.alpha.mojanalytics.xyz/annexes.html#what-are-the-benefits-of-github-and-why-do-we-recommend-it)



## What are automated tests, and when should they be used?

Automated tests are a way of writing down the checks that have been performed on your work.  Rather than write these checks in prose, the test is written in code.  This is similar to, for example, a 'check' column in Excel that makes sure percentages add up to 100%. Advanced tools are available on the analytical platform which enable a wide ranges of different tests to be applied, from low level 'unit' tests, to very high level 'integration' and sense checks.

This means it's:
- easy to see precisely what quality assurance checks have been completed
- easy to run these checks again when code or data changes

For work on the Analytical Platform, automated tests (witten in code) should motly replace manual logs of what QA has been performed.

You can find out more about testing in our coding standards, [here](https://moj-analytical-services.github.io/our-coding-standards/accurate.html#unittest).

You can read more about effective automated testing for analysts [here](https://medium.com/@robin.linacre/effective-testing-of-analytical-models-using-automated-sense-checks-c0c5f4480d7a)
