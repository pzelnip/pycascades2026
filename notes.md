# Pycascades 2026

<https://2026.pycascades.com/>

## Permacomputing and Python

Lukas Langa

> Will you be able to access your cloud data in 10 years? Are you able to easily access your photos and notes in an open format to analyze, aggregate, and backup? Is a device you bought in 2019 bricked now because the vendor stopped supporting it?
>
> Let's talk about computers and longevity, with special focus on how Python plays into sustainable computing and how you too can reclaim some agency over your data and devices.

no longer c dev in residence

Book: Practical Doomsday - Michal Zalewski

Principles

1. maximizing hardware life
2. Computational frugality

Bitrot project <https://pypi.org/project/bitrot/>

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

jiangsammie on linkedin

Fixtures are modelling a named combination of states.


`indirect=True` parameterization

Parameterizes the fixture

Tests should describe what they need, not how to build it
The fixture describes how to build it

If fixtures feel magical, then you've lost clarity

SHARE (higher scope -- shared stuff like the DB conn) vs ISOLATE (mutable data)

### Best Practices

- Maintain test clarity
- prefer parameter factories for complex needs
- lazy fixture setup
- avoid a god fixture

---

## Graceful Deletes: Queues, Tasks and Distributed State Management in Python

Chantelle Chan
Tanzim Mokammel

> Questionable queues, distributed storage chaos, stateful steps, and race conditions galore! Come join us as we dive into the wild world of queues and tasks in Python to perform asynchronous jobs, and how we built a system to manage user deletion across distributed storage systems and application isolation layers. We'll explore the pros and cons of common task queueing systems, and expose gotchas and workarounds that will hopefully save you future headaches! We'll navigate the challenges of sequential deletion in distributed storage systems as a case study, and ultimately show how we went from problem statement to deployed in production.

Cohere, company Stephen went to.

<http://mtanzim.com>

The problem: cleanup across application and network boundaries

(that doesn't resonate at all 😅)

Task Queue options: Celery vs [Inngest](https://www.inngest.com/)
(can't use SQS, on prem?)

chantellechan on linkedin

---

## Anti-Patterns in A/B Testing - or How does AB Testing Scale?


> AB testing is a tried and true standard across technology companies used extensively for 20+ years, Still it's hard to get right. With vendors and libraries, with better statistics and more experience, companies still struggle to scale AB Testing beyond one artisanal test at time.
>
> Learn the language and systems required to scale AB Testing. Tips and tricks for talking to your manager and stakeholders about the importance of AB Testing as a system and the benefits that happen when it runs like a song.
>
> A basic understanding of AB Testing and Python will make this talk fully understandable, but attendees that lack both of these things will still get the general idea of how AB Testing can be hard to scale

Stephen Pettinato

Anti patterns

1. experimentation is a library
2. all users are in all experiments
3. a pile of data dropped on an analyst

Do we even need AB testing anymore? Kinda interesting thought experiment

---

## No More Spreadsheets! Building PyLadiesCon Infrastructure with Python and Django

Mariatta

> PyLadiesCon is an online conference for the Global PyLadies community. It is one of a kind conference with programming spans 24 hours and offering talks and contents in multiple languages. Run entirely by volunteers, we face unique challenges specific to the nature of our conference.
>
> One of the ways we have been managing the various aspects of PyLadiesCon is by using spreadsheets. Spreadsheets for volunteer sign ups, spreadsheets for program scheduling, spreadsheets for sponsorship. Any information you want about the conference, we have a spreadsheet for that.
>
> While spreadsheets are great for capturing data, they come with drawbacks when it comes to online collaboration with various team members, causing frustrations and confusion among our team of volunteers.
>
> In 2025, PyLadiesCon team said no to spreadsheets and instead started building our conference infrastructure: an open source web app for managing various aspects of our conference. Learn more our challenges in managing the online PyLadiesCon conference, and how we're solving our problems with Python and Django. Contribute to the project, and support the PyLadies community.

<https://mariatta.ca/>

<https://www.instagram.com/mariatta81>

<https://conference.pyladies.com/docs>

<https://portal.pyladies.com>

[django-import-export](https://pypi.org/project/django-import-export) -> exporting data to spreadsheets


---

## The Future of Python: Evolution or Succession?

Brett Slatkin

> A decade from now there's a reasonable chance that Python won't be the world's most popular programming language. Many languages eventually have a successor that inherits large portions of its technical momentum and community contributions. With Python turning 35 years old, the time could be ripe for Python's eventual successor to emerge. How can we help the Python community navigate this risk by embracing change and evolving, or influencing a potential successor language?
>
> This talk will cover the past, present, and future of the Python language's growing edge. We'll learn about where Python began and its early influences. We'll look at shortcomings in the language, how the community is trying to overcome them, and opportunities for further improvement. We'll consider the practicalities of language evolution, how other languages have made the shift, and the unique approaches that are possible today (e.g., with tooling and AI).
>
> All levels of experience are welcome!

---

## Airflow Beyond the Cloud: Python Workflows at the Edge

Constance Martineau

> Apache Airflow is famous for orchestrating massive data pipelines, but what if you could also use it to orchestrate things in your physical workspace?
>
> In this talk, we'll explore how Airflow 3's new lightweight architecture makes micro-orchestration possible on resource-constrained devices. I'll demonstrate a real working system where an Airflow Edge Worker running on a Raspberry Pi controls an "On Air" LED that automatically lights up when a Zoom call starts. All built with standard Python and familiar Airflow patterns.
>
> What starts as a desk toy points to a bigger trend: orchestration breaking free from the data centre and moving closer to where work actually happens. You'll walk away seeing Airflow (and Python orchestration in general) not just as a data-engineering tool, but as a bridge between the digital and physical worlds.
>
> Basic familiarity with Python is all you need, no prior Airflow experience required.


---

## To Notebook or Not to Notebook: Multilingual Workflows for Exploratory Data Analysis

Rodrigo Silva Ferreira

> Notebooks have become the default environments for exploring data, prototyping ideas, and sharing results. Yet, their influence extends far beyond code execution, as they shape how we think, collaborate, and communicate with data. As real-world projects increasingly rely on multiple programming languages, magic commands and cross-language kernels open new possibilities for combining Python, R, SQL, markdown, and more within a single workflow, blending computation with storytelling in powerful ways.
>
> This talk explores how multilingual workflows transform exploratory data analysis (EDA), highlighting where notebooks shine and where they introduce new challenges around testing, version control, and scaling. Through real-world examples, we’ll look at how these tools lower barriers, reinforce trust and integrity in data science workflows, and change the way we reason about problems. Attendees will gain practical strategies for integrating multiple languages in their notebooks and a deeper understanding of how these tools shape modern data science. Basic familiarity with Python and EDA is helpful but not required.
>



---

## Getting Started with Open Source Contributions

> The open source community is all about giving back and learning from one another. No matter how small, every contribution is valuable. And everyone can contribute something with a little bit of help. The hardest part is finding something to work on that fits your interests and skills.
>
> In this talk, I will provide five ways that I used to get started contributing to different open source projects. I also share some guidance on selecting projects to contribute to and how to set yourself up for success. Get ready to start your open source journey!
>
> This talk is for anyone that has wanted to contribute to open source, but didn’t know where to start or thought they wouldn’t be able to do it with their skill set or time. Come learn how to get started!


---

## Variables and objects in Python: it's pointers all the way down

Trey Hunner

> In Python, assignment statements don't copy objects, and data structures don't actually contain objects. These two surprising facts have a lot of interesting consequences and are the reason behind many of Python's design decisions.
>
> In this talk, we'll explore the reference-like nature of Python's variables and objects, noting both the benefits and gotchas involved.
>
> Among other ideas, we'll see that in Python:
>
>     The word "change" is ambiguous
>     Copying is usually explicit
>     Tuples aren't always immutable
>
> During the process, we'll consider our own mental model of Python.
>
> In Python, it's pointers (or references, names, bindings, or aliases) all the way down.
