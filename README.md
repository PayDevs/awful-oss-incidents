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
- [Context](#context)
- [Incident Categories](#incident-categories)
  - [Trademark infringements](#trademark--brand-infringements)
  - [Faulty updates](#faulty-updates)
  - [Package Ownership](#package-ownership)
  - [Corporate Disputes](#corporate-disputes)
  - [Security Problems](#security-problems)
  - [Cyber-Warfare](#cyber-warfare)
  - [Developer Burnout](#developer-burnout--infocide--disgruntled-developers)
- [Examples for working Monetization](#examples-for-working-monetization)
- [Misc / Aftertoughts](#misc--aftertoughts)
- [OSS Funding related Links](#oss-funding-related-links)

## Context

In the beginning developing OSS is often great for the maintainer - there are no constraints on the tech or features, only few bugs exists, the maintainer can work as and when he wants, there are only his own expectations to fulfill, and the few users appreciate the project. Furthermore, working on the open-source project helps them to sharpen their skills, build a reputation for themselves, gain perspectives on the topic from the community, or simply help the industry by making innovations available at no cost.

But if a project gets more attention and users the heat increases. More and more users want new features, bug-fixes, more docu and tutorials, etc. Companies using the project want fixes to problems asap (e.g., for [cURL](https://onezero.medium.com/the-internet-relies-on-people-working-for-free-a79104a68bcc)) - esp. if it concerns their own SLAs - all without previously funding or currently supporting the project. And most of Companies systems and the Internet's infrastructure at large are using open-source libraries developed by few maintainers and without funding - wonderfully visualized in a xkcd comic.

![xkcd comic](https://imgs.xkcd.com/comics/dependency.png)

This ever increasing workload and lack of funding often causes maintainers to get unhappy and sometimes even leave their project or run amok and cause problems for the user base. With more funding most of the identified problems could be mitigated. Funding enables maintainers of open-source projects to:
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
... many incidents happened over time
... we classified them based on the core problem.

> Please Note that we do not take sides and every side has it's own story. We just try to categorize and describe the problems, history, and consequences based on some articles.

### Trademark infringements
Trademark / Brand infringements
Causes: Oversight (from both sides), Trademark Trolls
Examples:
* (March 2016): Azer Koçulu unpublished over 250 modules (esp. `left-pad`) from npm due to trademark infringement over the name "kik" - breaking tens of thousands of projects that depended on it. [Link](https://www.theregister.com/2016/03/23/npm_left_pad_chaos/)
  * [The left-pad Incident - original article](https://www.theregister.com/2016/03/23/npm_left_pad_chaos/)
  * [The left-pad Incident - kik's version](https://medium.com/@mproberts/a-discussion-about-the-breaking-of-the-internet-3d4d2a83aa4d#.ld8o5zqz7)

#### Potential Solutions:
* Buy Trademarks
* Initial trademark check

### Faulty updates
Causes: Oversight, No time for tests, Corrupt Dependencies
Examples:
* (April 2020) The updated `is-promised` library didn't adhere to the proper ES module standards causing wide-spread build errors. 
  * April 2020: (Faulty update) Over the weekend, the is-promised library was updated to receive support to work as an ES module -- the standardized module system used by the JavaScript language. However, the is-promise v.2.2.0 release didn't adhere to the proper ES module standards. As soon as the update was out, projects that used is-promise inside their build chain started failing due to the improper ES module support [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]. (https://www.zdnet.com/google-amp/article/another-one-line-npm-package-breaks-the-javascript-ecosystem/)
  * https://twitter.com/tmpreet
  * https://github.com/then/is-promise/network/dependents
* In April 2020, a small package called is-promise resulted in outage in serverless applications and deployments worldwide by virtue of being a dependency of many big and important applications.[18]


#### Potential Solutions:
* Write more tests
* Test & Bug bounties

### Package Ownership
Causes: Oversight, Contact problems
Examples:
* (Aug. 2021) The ownership of the package `bebop` was auto-transferred due to a corrupt contact address of the former owner
  * Aug. 2021: (Package Ownership) during the process of getting packages for a project called bebop published in various software repositories, they found that this name was unclaimed except in NPM. (https://hackaday.com/2021/09/08/the-dark-side-of-package-repositories-ownership-drama-and-malware/ )

#### Potential Solutions:
* Continuous contact confirmation

### Corporate Disputes
Causes: Business decisions
Examples:
* (Aug. 2021): Elasticsearch change its widely used JS client library `elasticsearch` to not work with AWS Elasticsearch and OpenSearch anymore.
  * https://github.com/elastic/elasticsearch-js/issues/1519

#### Potential Solutions:
* ???

### Security Problems
Causes: Oversight, No time for tests, Corrupt Dependencies, Hacks
Examples:
* (Apr 2014): A programming mistake by a single maintainer of `openSSL` led to a vulnerability (l.k.a. **Heartbleed**) that allowed stealing information and passwords from users.
  * OpenSSL, received just $2,000 per year in donations which grew to $9,000 after the issue was found. (The global cost for the software industry was [estimated to be as high as $500 million](https://www.eweek.com/security/heartbleed-ssl-flaw-s-true-cost-will-take-time-to-tally/))
  * [The Heartbleed Vulnerability](https://heartbleed.com/)
* In September 2018, a small package called `event-stream` was infected / enriched with malicious code that targeted a specific company and could steal passwords for crypto accounts [NPM Incident Report](https://blog.npmjs.org/post/180565383195/details-about-the-event-stream-incident)
* (Dec 2021): `log4j` enabled a feature from 2013 by default that allowed loading of malicious code.
  * [The Log4j Vulnerability](https://www.cisa.gov/uscert/apache-log4j-vulnerability-guidance)
* (Oct. 2021): The NPM account for the `UA-Parser-JS` library was hacked, to infect dependent systems with cryptominers and password-stealing trojans in a supply-chain attack. [Full Story](https://www.bleepingcomputer.com/news/security/popular-npm-library-hijacked-to-install-password-stealers-miners/)
* (Apr 2022): A flaw in the NPM registry allowed adding maintainers to own projects (a.k.a. "Package Planting") - giving a false sense of credibility / security of potentially harmful packages. [Full Story](https://www.bleepingcomputer.com/news/security/npm-flaw-let-attackers-add-anyone-as-maintainer-to-malicious-packages/)

from https://en.wikipedia.org/wiki/Npm_(software)#Notable_breakages
* In July 2018, the npm credentials of a maintainer of the popular eslint-scope package were compromised resulting in a malicious release of eslint-scope, version 3.7.2. The malicious code copied the npm credentials of the machine running eslint-scope and uploaded them to the attacker.[15] 
* In November 2018, it was discovered that a malicious package had been added as a dependency to version 3.3.6 of the popular package event-stream. The malicious package, called flatmap-stream, contained an encrypted payload that stole bitcoins from certain applications. npm administrators removed the offending package.[16][17]
* In March 2022, developer Brandon Nozaki Miller released a version of the package node-ipc containing malicious code that would delete files from users with Belarusian and Russian IP addresses, in protest of the Russian invasion of Ukraine. Vue.js, which uses node-ipc as a dependency, did not pin its dependencies to a safe version, meaning that some users of Vue.js became affected by the malicious package if the dependency was fetched as the latest package.[20][21] The affected dependency was also briefly present in version 3.1 of Unity Hub; a hotfix was released the same day to remove the issue, however.[22]



#### Potential Solutions:
* More tests
* Hack bounties

### Cyber-Warfare
https://www.vice.com/en/article/dypeek/open-source-sabotage-node-ipc-wipe-russia-belraus-computers

### Developer Burnout
Developer Burnout / Infocide / Disgruntled Developers
Causes: Pressure from Users, Disillusionment, Private problems
Examples:
* (Jan. 2022): Marak Squiress intentionally introduced changes to break the functionality and later deletes his projects `colors.js` and `faker.js` after getting pushed / bullied by corporates. [Original Message](http://web.archive.org/web/20210704022108/https://github.com/Marak/faker.js/issues/1046) [Full Story](https://www.bleepingcomputer.com/news/security/dev-corrupts-npm-libs-colors-and-faker-breaking-thousands-of-apps/)
  * https://hacker-news.news/post/27252066

#### Potential Solutions:
* Better monetization mechanisms

## Examples for working Monetization
* cURL? [Daniel Stenberg](https://daniel.haxx.se/) 
  * Story: https://onezero.medium.com/the-internet-relies-on-people-working-for-free-a79104a68bcc

## Misc / Aftertoughts
* maintainer account takeovers [`ua-parser-js`](https://github.com/advisories/GHSA-pjwm-rvh2-c87w)

* GitHubs site-policy [2022](https://github.com/github/site-policy/issues/513) 
* NPM project reconstruction 
... problematic as copyright, brand, and name (handle) is owned by the author/maintainer and assuming the identity of the author is borderline illegal (at least the companies are liable and take warranty that the offered (old) versions are correct)

## OSS Funding related Links
* [Open source developers, who work for free, are discovering they have power (Jan. 2022)](https://techcrunch.com/2022/01/18/open-source-developers-who-work-for-free-are-discovering-they-have-power/)
* [Open source has a funding problem (Jan. 2021)](https://stackoverflow.blog/2021/01/07/open-source-has-a-funding-problem/)
* [Notable breakages of NPM](https://en.wikipedia.org/wiki/Npm_(software)#Notable_breakages)
* [The Internet Relies on People Working for Free (Sep. 2019)](https://onezero.medium.com/the-internet-relies-on-people-working-for-free-a79104a68bcc)