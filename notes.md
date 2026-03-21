# Pycascades 2026

## Permacomputing and Python

Lukas Langa

> Will you be able to access your cloud data in 10 years? Are you able to easily access your photos and notes in an open format to analyze, aggregate, and backup? Is a device you bought in 2019 bricked now because the vendor stopped supporting it?
>
> Let's talk about computers and longevity, with special focus on how Python plays into sustainable computing and how you too can reclaim some agency over your data and devices.

no longer c dev in residence

Book: Practical Doomsday - Michal Zalewski

Peinciples

1. maximizing hardware life
2. Computational frugality



Bitrot project = https://pypi.org/search/?q=bitrot

What can you do?

1. backups, for real (test them, offisite etc)
2. Own your hardware, software and data
3. question the upgrade culture
4. choose repairable products
5. cull software subscriptions
6. keep learning

As a developer?

1. start with newest Python when making a new project
2. use trivial data formats
3. don't boil the oceans to open a garage door
4. keep things offline if possible
5. support the development of Python
   1. come to Pycon US
6. keep learning

---

## Climbing Out of Fixture Hell, Indirectly

Sammie Jiang

> Once you've moved past the basics of assert and test_ functions, developers often run into a new set of challenges when projects and test suites grow in complexity. This talk explores using pytest's indirect fixtures to create modular, maintainable test suites that scale with your codebase.

> Fixture overuse and mismanagement is one of the most common areas of difficulty with testing/pytest
>
>     passing data to fixtures: they want to parametrize a fixture itself (this is how I initially discovered indirect parametrization)
>     fixture hell: conftest.py becomes a dumping ground for poorly named, complex, and interdependent fixtures, making it hard to comprehend what a single test is doing
>     scope confusion: struggles with when to use function, class, module or session scopes that lead to tests that are either slow (re-creating expensive resources for every test) or flaky (tests interfering with each other via session-scoped fixtures).
>
> You'll discover how indirect=True parametrization can elegantly address each of these pain points and see examples of how to refactor messy, hard-to-read tests into clean, declarative patterns. Come away with a clearer mental model of fixture scopes and how to optimize them to reduce test run times.
>
> This talk is for intermediate developers who have basic experience with fixtures and parametrization, who may have encountered the pain points of maintaining a growing test suite.

---
