[![License: CC0-1.0](https://img.shields.io/badge/❤-Open%20Source-lightgrey.svg)](http://creativecommons.org/publicdomain/zero/1.0/)
[![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg)](http://creativecommons.org/publicdomain/zero/1.0/)
[![GitHub](https://img.shields.io/github/stars/PayDevs/awesome-oss-monetization?style=social)](https://github.com/PayDevs/awful-oss-incidents)
     [![Twitter](https://img.shields.io/twitter/follow/paydevs_com?label=Follow&style=social)](https://twitter.com/paydevs_com)
[![GitHub](https://img.shields.io/github/followers/paydevs?label=Follow&affiliations=OWNER%2CCOLLABORATOR%2CORGANIZATION_MEMBER&style=social)](https://github.com/paydevs)
[![Reddit](https://img.shields.io/reddit/user-karma/combined/paydevs?label=Karma&style=social)](https://www.reddit.com/user/paydevs)

# Awful OSS Incidents
A categorized list of incidents caused by unappreciated OSS maintainers or underfunded OSS library projects. Feedback welcome!

The Goal of this classification and list of incidents is to identify and analyze reasons why some OSS maintainers do intentionally cause problems for the larger software ecosystem and to determine potential solutions.

__Table of Contents__
- [Awful OSS Incidents](#awful-oss-incidents)
  - [Context](#context)
  - [Incident Categories](#incident-categories)
    - [Trademark infringements](#trademark-infringements)
    - [Programming mistake](#programming-mistake)
    - [Package Ownership Disputes](#package-ownership-disputes)
    - [Usage Disputes](#usage-disputes)
    - [Security Problems / Hacked Accounts / Criminal Intentions](#security-problems--hacked-accounts--criminal-intentions)
    - [Cyber-Warfare / Protestware](#cyber-warfare--protestware)
    - [Developer Burnout](#developer-burnout)
  - [Examples for working Monetization](#examples-for-working-monetization)
  - [Misc / Aftertoughts](#misc--aftertoughts)
  - [General Links](#general-links)

## Context

In the beginning developing OSS is often great for the maintainer - there are no constraints on the tech or features, only few bugs exists, the maintainer can work as and when he wants, there are only his own expectations to fulfill, and the few users appreciate the project. Furthermore, working on the open-source project helps them to sharpen their skills, build a reputation for themselves, gain perspectives on the topic from the community, or simply help the industry by making innovations available at no cost.

But if a project gets more attention and users the heat increases. More and more users want new features, bug-fixes, more docu and tutorials, etc. Companies using the project want fixes to problems asap (e.g., for [cURL](https://onezero.medium.com/the-internet-relies-on-people-working-for-free-a79104a68bcc)) - esp. if it concerns their own SLAs - all without previously funding or currently supporting the project. And most of Companies systems and the Internet's infrastructure at large are using open-source libraries developed by few maintainers and without funding - wonderfully visualized in a xkcd comic.

![xkcd comic](https://imgs.xkcd.com/comics/dependency.png)

This ever increasing workload and lack of funding often causes maintainers to get unhappy and sometimes even leave their project or even "run amok" and cause problems for the user base. With more funding most of the identified problems can be mitigated. Funding enables maintainers of open-source projects to:
* **pay themselves** a (part-time or full-time) salary to have more time to develop new features, fix bugs, and better maintain the software
* **pay contributors** to develop new features & fix bugs (e.g., via bug bounties), hire a logo designer, hire a website designer, etc.
* **improve their project** by registering trademark(s), buy a domain, pay for hosting, ...
* **sponsor other projects** (e.g., dependencies, tools, etc.)
* **advertise their projects**, sponsor meetups & conferences, etc.
* **sponsor team events** for other maintainers, contributors or the community itself
* **sponsor team expenses** such as hardware (laptops), conference tickets, local hosting cost, etc.
* **found a Startup** and pay initial legal fees, taxes, etc.

---

## Incident Categories
Many incidents occurred since the advent of the registries and became famous especially in frontend web development, which has a large developer base.

We classified these incidents based on the core problem, describe them briefly, and state potential solutions to prevent them from happening again.

> Please note that when descibing these incidents, we try to not take sides as every side has it's own story. We just try to categorize and describe the problems, history, and consequences based on available articles.



### Trademark infringements
A part of an open-source project can sometime cause problems when the name of the project, the logo, or something else used in the project causes an infringement on the Trademark, Figurative Mark, Brand, etc. Furthermore, a trademark might even have been registered after the project was created or in different jurisdictions that have not been checked (e.g., trademarks can be registered in a country (e.g., Italy), a union of countries (e.g., the EU) or internationally).

Trademark infringements are often caused by an oversight or ignorance from the open-source maintainer as well as the trademark owner or by "Trademark Trolls" registering the trademark to harm the project.

__Examples__
* (March 2016): Azer Koçulu unpublished over 250 modules (esp. `left-pad`) from npm due to trademark infringement over the name "kik" - breaking tens of thousands of projects that depended on it. [[Blog Post](https://www.theregister.com/2016/03/23/npm_left_pad_chaos/)] [[Azer's version](https://web.archive.org/web/20160330050734/https://medium.com/@azerbike/i-ve-just-liberated-my-modules-9045c06be67c)] [[kik's version](https://medium.com/@mproberts/a-discussion-about-the-breaking-of-the-internet-3d4d2a83aa4d#.ld8o5zqz7)]

__Potential Solutions__
* Register trademark for the open-source project [drawback: extra cost]
* Research trademarks periodically and rename OSS project[drawback: extra work & loss of own brand]



### Programming mistake
All software system can have minor or major bugs that prevent their intended use in different scenarios. When a open-source maintainer publishes a faulty project the effect can be felt by many of its users.

Programming mistakes are causes by oversights, missing tests, integration problems, corrupt dependencies, and in general due to no having enough time for checking the system in production-like environments.

__Examples__
* (Apr 2014): A programming mistake by a single maintainer of `openSSL` led to a vulnerability (a.k.a. **Heartbleed**) that allowed stealing information and passwords from users. [The Heartbleed Vulnerability Website](https://heartbleed.com/)
  * OpenSSL, received just $2,000 per year in donations which grew to $9,000 per year after the issue was found. (The global cost for the software industry was [estimated to be as high as $500 million](https://www.eweek.com/security/heartbleed-ssl-flaw-s-true-cost-will-take-time-to-tally/))
* (April 2020) Forbes Lindesay released version 2.2.0 of the `is-promised` library that didn't adhere to the proper ES module standards causing wide-spread build errors. This release led to bugs in popular build tools used to create new projects, such as Facebook's create-react-app, Google's firebase-tools, Amazon's AWS Serverless CLI, Nuxt.js, AVA, angular-cli, and others. [[Blog Post](https://www.zdnet.com/google-amp/article/another-one-line-npm-package-breaks-the-javascript-ecosystem/)] [[Forbes' Post-mortem](https://javascript.plainenglish.io/is-promise-post-mortem-cab807f18dcc)]
* (Dec 2021): `log4j` enabled a feature from 2013 by default that allowed loading of malicious code on any log server. [[The Log4j Vulnerability](https://www.cisa.gov/uscert/apache-log4j-vulnerability-guidance)]
  * The exploitation of this vulnerability did cost ONE company already $ 700 million [[Equifax exposed user data](https://www.ftc.gov/policy/advocacy-research/tech-at-ftc/2022/01/ftc-warns-companies-remediate-log4j-security-vulnerability)]

__Potential Solutions__
* Write more tests / safe-guards [drawback: extra effort]
* Use Quality-Gates (other people check OSS) [drawback: extra effort]
* Use Bug bounties [drawback: extra cost]



### Package Ownership Disputes
The maintainer of a open-source library is often the owner of a package on a registry and is the only one allowed to change, delete, or publish new versions. The account of the owner in the registry is often linked to an email address and can only be transferred by the registry operators. If the ownership of a package is transferred this can lead to incompatible libraries (with the same name) or malicious code deleting data or stealing information.

Package ownership problems are often caused by hacked password / credentials, an oversight or misunderstanding by the registry operator, or general contact problems.

__Examples__
* (Aug. 2021) During the process of getting packages for a project called `bebop` published in various software repositories, Andrew Sampson found that it was unclaimed except in NPM. After inquiring the NPM registry the ownership of the package `bebop` was auto-transferred to Andrew due to a corrupt contact address of the former owner Zach Kelling. [[Blog Post](https://www.theregister.com/2021/08/10/github_npm_package/)]

__Potential Solutions__
* Stronger authentification (e.g., 2FA) [drawback: extra effort]
* Continuous contact confirmation [drawback: extra effort]
* Always use scopes / usernames [depends on registry]



### Usage Disputes
The usage of an open-source project can sometime cause problems when third-parties (e.g. Cloud provider) offer them commercially and/or the maintainer community wants to commercialize and builds a Startup.

Usage disputes are causes by different point of views how an open-source project should be used or commercialized. Even if the positions are legally clear the dispute can affect and impair the users.

__Examples__
* (Aug. 2021): Elasticsearch introduced a breaking change to its widely used JS client library `elasticsearch-js` to not work with AWS Elasticsearch and OpenSearch anymore. [[Github Issue](https://github.com/elastic/elasticsearch-js/issues/1519)]

__Potential Solutions__
* Not being dependent on OSS that has a Company behind it? [drawback: extra effort]



### Security Problems / Hacked Accounts / Criminal Intentions
Most software system have flaws that can be hacked, used to extract data, or otherwise exploited by criminals. While their existance does not necessarily break the system it is prone to be exploited.

Security problems are often caused by oversight, no time for tests, corrupt dependencies, or intended hacks.

__Examples__
* (Nov. 2018) A malicious package was added as a dependency to version 3.3.6 of the popular package `event-stream` by a new maintainer. The malicious package, called `flatmap-stream`, contained an encrypted payload that stole bitcoins from certain applications. [[NPM Incident Report](https://blog.npmjs.org/post/180565383195/details-about-the-event-stream-incident)]
* (Oct. 2021): The NPM account for the `UA-Parser-JS` library was hijacked, to infect dependent systems with cryptominers and password-stealing trojans in a supply-chain attack. [[Full Story](https://www.bleepingcomputer.com/news/security/popular-npm-library-hijacked-to-install-password-stealers-miners/)]
* (Apr 2022): A flaw in the NPM registry allowed adding random maintainers to own projects (a.k.a. "Package Planting") - giving a false sense of credibility / security of potentially harmful packages. [[Full Story](https://www.bleepingcomputer.com/news/security/npm-flaw-let-attackers-add-anyone-as-maintainer-to-malicious-packages/)]
* (Jul 2018) The credentials of a maintainer on NPM were compromised resulting in a malicious release of `eslint-scope`, version 3.7.2. The malicious code copied the npm credentials of the machine running eslint-scope and uploaded them to the attacker. [[Post-mortem](https://eslint.org/blog/2018/07/postmortem-for-malicious-package-publishes/)]

__Potential Solutions__
* Write more tests / safe-guards [drawback: extra effort]
* Use bounties for Hacks [drawback: extra cost]
* Stronger authentification (e.g., 2FA) [drawback: extra effort]
* Continuous contact confirmation [drawback: extra effort]



### Cyber-Warfare / Protestware
The usage of an open-source project can cause problems when both parties (i.e., the maintainer and user) are in a legal dispute or even war.

Cyber-warfare are causes by deliberate actions of the maintainer to harm or encumber the activities of a group of users.

__Examples__
* (Mar 2022) Maintainer Brandon Nozaki Miller released a version of the package `node-ipc` containing malicious code that would delete files from Belarusian and Russian users. This concerned even frameworks such as Vue.js, which uses node-ipc as a dependency. [[Full story](https://www.bleepingcomputer.com/news/security/big-sabotage-famous-npm-package-deletes-files-to-protest-ukraine-war/)]

__Potential Solutions__
* ???



### Developer Burnout
The unpaid nature of open-source projects in connection with increasing pressure from users for bugfixes or new feature sometimes brings maintainers at the edge of exhaustion. Mild versions of burnout can bring a maintainer just to abandon their projects while fully disgruntled maintainers might commit infocide (deleting all code and data) or introduce malicious code that causes harm to user's system.

Developer Burnout is causes by pressure from users, failure to monetize, disillusionment, sometimes in addition to private problems.

__Examples__
* (Jan. 2022): Marak Squiress intentionally introduced changes to break the functionality and later deletes his projects `colors.js` and `faker.js` after failing to monetize it and getting pushed to hard by corporates. [[Original Message](https://hacker-news.news/post/27252066)] [[Github issue](http://web.archive.org/web/20210704022108/https://github.com/Marak/faker.js/issues/1046)] [[Full Story](https://www.bleepingcomputer.com/news/security/dev-corrupts-npm-libs-colors-and-faker-breaking-thousands-of-apps/)]

__Potential Solutions__
* Better monetization mechanisms



## Examples for working Monetization
* `cURL`, which is maintained by [Daniel Stenberg](https://daniel.haxx.se/) seems to have a working monetization approach [[Story](https://onezero.medium.com/the-internet-relies-on-people-working-for-free-a79104a68bcc)]



## Misc / Aftertoughts
<!-- 
* other maintainer account takeovers [`ua-parser-js`](https://github.com/advisories/GHSA-pjwm-rvh2-c87w) 
-->

* GitHubs site-policy change after the Faker.js incident [2022](https://github.com/github/site-policy/issues/513) 
<!-- 
* NPM project reconstruction: 
... might be problematic as copyright, brand, and name (handle) is owned by the author/maintainer and assuming the identity of the author is borderline illegal (at least the companies are liable and take warranty that the offered (old) versions are correct)
-->



## General Links
* [Open source developers, who work for free, are discovering they have power (Jan. 2022)](https://techcrunch.com/2022/01/18/open-source-developers-who-work-for-free-are-discovering-they-have-power/)
* [Open source has a funding problem (Jan. 2021)](https://stackoverflow.blog/2021/01/07/open-source-has-a-funding-problem/)
* [Wikipedia: Notable breakages of NPM](https://en.wikipedia.org/wiki/Npm_(software)#Notable_breakages)
* [The Internet Relies on People Working for Free (Sep. 2019)](https://onezero.medium.com/the-internet-relies-on-people-working-for-free-a79104a68bcc)