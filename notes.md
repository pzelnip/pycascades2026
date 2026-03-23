# Pycascades 2026

<https://2026.pycascades.com/>

## Permacomputing and Python

Lukas Langa

> Will you be able to access your cloud data in 10 years? Are you able to easily
> access your photos and notes in an open format to analyze, aggregate, and
> backup? Is a device you bought in 2019 bricked now because the vendor stopped
> supporting it?
>
> Let's talk about computers and longevity, with special focus on how Python
> plays into sustainable computing and how you too can reclaim some agency over
> your data and devices.

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

> Once you've moved past the basics of assert and test_ functions, developers
> often run into a new set of challenges when projects and test suites grow in
> complexity. This talk explores using pytest's indirect fixtures to create
> modular, maintainable test suites that scale with your codebase.
>
> Fixture overuse and mismanagement is one of the most common areas of
> difficulty with testing/pytest
>
>     passing data to fixtures: they want to parametrize a fixture itself (this is how I initially discovered indirect parametrization)
>     fixture hell: conftest.py becomes a dumping ground for poorly named, complex, and interdependent fixtures, making it hard to comprehend what a single test is doing
>     scope confusion: struggles with when to use function, class, module or session scopes that lead to tests that are either slow (re-creating expensive resources for every test) or flaky (tests interfering with each other via session-scoped fixtures).
>
> You'll discover how indirect=True parametrization can elegantly address each
> of these pain points and see examples of how to refactor messy, hard-to-read
> tests into clean, declarative patterns. Come away with a clearer mental model
> of fixture scopes and how to optimize them to reduce test run times.
>
> This talk is for intermediate developers who have basic experience with
> fixtures and parametrization, who may have encountered the pain points of
> maintaining a growing test suite.

jiangsammie on linkedin

Fixtures are modelling a named combination of states.

`indirect=True` parameterization

Parameterizes the fixture

Tests should describe what they need, not how to build it The fixture describes
how to build it

If fixtures feel magical, then you've lost clarity

SHARE (higher scope -- shared stuff like the DB conn) vs ISOLATE (mutable data)

### Best Practices

- Maintain test clarity
- prefer parameter factories for complex needs
- lazy fixture setup
- avoid a god fixture

---

## Graceful Deletes: Queues, Tasks and Distributed State Management in Python

Chantelle Chan Tanzim Mokammel

> Questionable queues, distributed storage chaos, stateful steps, and race
> conditions galore! Come join us as we dive into the wild world of queues and
> tasks in Python to perform asynchronous jobs, and how we built a system to
> manage user deletion across distributed storage systems and application
> isolation layers. We'll explore the pros and cons of common task queueing
> systems, and expose gotchas and workarounds that will hopefully save you
> future headaches! We'll navigate the challenges of sequential deletion in
> distributed storage systems as a case study, and ultimately show how we went
> from problem statement to deployed in production.

Cohere, company Stephen went to.

<http://mtanzim.com>

The problem: cleanup across application and network boundaries

(that doesn't resonate at all 😅)

Task Queue options: Celery vs [Inngest](https://www.inngest.com/) (can't use
SQS, on prem?)

chantellechan on linkedin

---

## Anti-Patterns in A/B Testing - or How does AB Testing Scale?

Stephen Pettinato

> AB testing is a tried and true standard across technology companies used
> extensively for 20+ years, Still it's hard to get right. With vendors and
> libraries, with better statistics and more experience, companies still
> struggle to scale AB Testing beyond one artisanal test at time.
>
> Learn the language and systems required to scale AB Testing. Tips and tricks
> for talking to your manager and stakeholders about the importance of AB
> Testing as a system and the benefits that happen when it runs like a song.
>
> A basic understanding of AB Testing and Python will make this talk fully
> understandable, but attendees that lack both of these things will still get
> the general idea of how AB Testing can be hard to scale

Anti patterns

1. experimentation is a library
2. all users are in all experiments
3. a pile of data dropped on an analyst

Do we even need AB testing anymore? Kinda interesting thought experiment

---

## No More Spreadsheets! Building PyLadiesCon Infrastructure with Python and Django

Mariatta

> PyLadiesCon is an online conference for the Global PyLadies community. It is
> one of a kind conference with programming spans 24 hours and offering talks
> and contents in multiple languages. Run entirely by volunteers, we face unique
> challenges specific to the nature of our conference.
>
> One of the ways we have been managing the various aspects of PyLadiesCon is by
> using spreadsheets. Spreadsheets for volunteer sign ups, spreadsheets for
> program scheduling, spreadsheets for sponsorship. Any information you want
> about the conference, we have a spreadsheet for that.
>
> While spreadsheets are great for capturing data, they come with drawbacks when
> it comes to online collaboration with various team members, causing
> frustrations and confusion among our team of volunteers.
>
> In 2025, PyLadiesCon team said no to spreadsheets and instead started building
> our conference infrastructure: an open source web app for managing various
> aspects of our conference. Learn more our challenges in managing the online
> PyLadiesCon conference, and how we're solving our problems with Python and
> Django. Contribute to the project, and support the PyLadies community.

<https://mariatta.ca/>

<https://www.instagram.com/mariatta81>

<https://conference.pyladies.com/docs>

<https://portal.pyladies.com>

[django-import-export](https://pypi.org/project/django-import-export) ->
exporting data to spreadsheets

---

## The Future of Python: Evolution or Succession?

Brett Slatkin

> A decade from now there's a reasonable chance that Python won't be the world's
> most popular programming language. Many languages eventually have a successor
> that inherits large portions of its technical momentum and community
> contributions. With Python turning 35 years old, the time could be ripe for
> Python's eventual successor to emerge. How can we help the Python community
> navigate this risk by embracing change and evolving, or influencing a
> potential successor language?
>
> This talk will cover the past, present, and future of the Python language's
> growing edge. We'll learn about where Python began and its early influences.
> We'll look at shortcomings in the language, how the community is trying to
> overcome them, and opportunities for further improvement. We'll consider the
> practicalities of language evolution, how other languages have made the shift,
> and the unique approaches that are possible today (e.g., with tooling and AI).
>
> All levels of experience are welcome!

Why do programming languages matter anymore?

---

## Airflow Beyond the Cloud: Python Workflows at the Edge

Constance Martineau

> Apache Airflow is famous for orchestrating massive data pipelines, but what if
> you could also use it to orchestrate things in your physical workspace?
>
> In this talk, we'll explore how Airflow 3's new lightweight architecture makes
> micro-orchestration possible on resource-constrained devices. I'll demonstrate
> a real working system where an Airflow Edge Worker running on a Raspberry Pi
> controls an "On Air" LED that automatically lights up when a Zoom call starts.
> All built with standard Python and familiar Airflow patterns.
>
> What starts as a desk toy points to a bigger trend: orchestration breaking
> free from the data centre and moving closer to where work actually happens.
> You'll walk away seeing Airflow (and Python orchestration in general) not just
> as a data-engineering tool, but as a bridge between the digital and physical
> worlds.
>
> Basic familiarity with Python is all you need, no prior Airflow experience
> required.

cmarteepants on Github

airflow-edge-demo on Github

---

## To Notebook or Not to Notebook: Multilingual Workflows for Exploratory Data Analysis

Rodrigo Silva Ferreira

> Notebooks have become the default environments for exploring data, prototyping
> ideas, and sharing results. Yet, their influence extends far beyond code
> execution, as they shape how we think, collaborate, and communicate with data.
> As real-world projects increasingly rely on multiple programming languages,
> magic commands and cross-language kernels open new possibilities for combining
> Python, R, SQL, markdown, and more within a single workflow, blending
> computation with storytelling in powerful ways.
>
> This talk explores how multilingual workflows transform exploratory data
> analysis (EDA), highlighting where notebooks shine and where they introduce
> new challenges around testing, version control, and scaling. Through
> real-world examples, we’ll look at how these tools lower barriers, reinforce
> trust and integrity in data science workflows, and change the way we reason
> about problems. Attendees will gain practical strategies for integrating
> multiple languages in their notebooks and a deeper understanding of how these
> tools shape modern data science. Basic familiarity with Python and EDA is
> helpful but not required.

Blog: <https://rodrigosf.com>

Referenced this talk: <https://www.youtube.com/watch?v=0i-r3gl4WLU>

Notebook demo <https://github.com/rodrigosf672/pycascades2026-multilingual_eda>

rsf309 on Linkedin

---

## Getting Started with Open Source Contributions

> The open source community is all about giving back and learning from one
> another. No matter how small, every contribution is valuable. And everyone can
> contribute something with a little bit of help. The hardest part is finding
> something to work on that fits your interests and skills.
>
> In this talk, I will provide five ways that I used to get started contributing
> to different open source projects. I also share some guidance on selecting
> projects to contribute to and how to set yourself up for success. Get ready to
> start your open source journey!
>
> This talk is for anyone that has wanted to contribute to open source, but
> didn’t know where to start or thought they wouldn’t be able to do it with
> their skill set or time. Come learn how to get started!

Stefanie Molin

<https://stefaniemolin.com/>

<https://stefaniemolin.com/talks/#getting-started-with-open-source-contributions>

---

## Variables and objects in Python: it's pointers all the way down

Trey Hunner

> In Python, assignment statements don't copy objects, and data structures don't
> actually contain objects. These two surprising facts have a lot of interesting
> consequences and are the reason behind many of Python's design decisions.
>
> In this talk, we'll explore the reference-like nature of Python's variables
> and objects, noting both the benefits and gotchas involved.
>
> Among other ideas, we'll see that in Python:
>
>     The word "change" is ambiguous
>     Copying is usually explicit
>     Tuples aren't always immutable
>
> During the process, we'll consider our own mental model of Python.
>
> In Python, it's pointers (or references, names, bindings, or aliases) all the
> way down.

<https://trey.io/pycascades26>

---

Day 2

## Python Stings Your Ego: Finding Pride in Community, Not Just Code

> In tech, it’s easy to get caught up in ego. Chasing the smartest solutions,
> writing the most complex code, or proving who’s the best in the room. But
> Python has a funny way of humbling us. Its simplicity reminds us that good
> code isn’t about showing off; it’s about making things clear, accessible, and
> collaborative.
>
> This talk is about what happens after that sting of humility. Python doesn’t
> just strip away ego, it builds communities that make you feel proud to belong.
> I’ll share stories from my journey with Black Python Devs and other Python
> groups, showing how people from all walks of life come together, support one
> another, and create space for growth.
>
> By the end, you’ll see that the real magic of Python isn’t just the language.
> It’s the people, the openness, and the sense of pride that comes from being
> part of something bigger than yourself.

Emmanuel Ugwu

(virtual talk)

"Ego is not your enemy it is the story the mind uses to feel safe"

What would tech look like if we measured success by the people we lift, not the code we write?

- Who are you mentoring?
- Who helped you grow?
- What community are you building?

---

## Am I ready to be a Senior Engineer?

Michelle Brenner

> When you move from Junior to Mid-level Software Engineer, you’re mostly
> building on what you already know. You get better at writing clean code, you
> pick up speed, and you start to really understand how your team works. But
> making the leap from Mid to Senior? That’s a whole new game. Suddenly, you’re
> expected to make technical decisions, work across teams, and help drive your
> team’s success. I’ll talk about what being a Senior Engineer actually means,
> and what people are really looking for. These days, on-the-job training is
> rare. Managers want to see these skills early, not just when you have the
> title.
>
> Here’s a challenge: the most experienced engineers are often working remotely,
> so it’s harder for newer folks to pick things up just by being around them.
> How are you supposed to know what’s expected if you never get to see it in
> action? That’s what I want to help with. We’ll dig into everything from system
> design to working with other teams, the stuff nobody really explains. This is
> a sneak peek from my upcoming book (coming Fall 2026), pulled from both my own
> experience and the many engineers I interviewed.
>
> You’ll leave with practical skills you can start using right away, and a
> clearer picture of what it really means to be a Senior Engineer, so you can
> stop guessing and be ready for your next step.

<https://www.michellebrenner.com/>

---

## There and back again... but by I-5 or the ferry?

Justin Castilla

> Living on Washington State’s peninsula offers endless beauty, nature, and
> commuting challenges. In this talk, I’ll share how I built an agentic AI
> system that creates and compares optimal routes to the mainland, factoring in
> ferry schedules, costs, driving distances, and live traffic. Originally a
> testbed for the Model Context Protocol (MCP) framework, this project now
> manages my travel schedule, generates expense estimates, and sends timely
> notifications for events. I’ll give a comprehensive overview of MCP, show how
> to quickly turn ideas into working agentic AI, and discuss practical
> integration with real-world APIs. Attendees will leave with MCP Server
> resources and tutorials and a roadmap for building their own agentic AI
> solutions. A comfortable grasp of Python functions, API calls, framework
> decorators, and the role of context with LLMs is recommended.

---

## When the Baby App Crashed: Coding for Chaos (and Parenthood)

Laura Meng

> As a first-time parent and a developer, I relied on an app to log sleep and
> feedings. If I was going to lose sleep, at least I’d have data. But one night,
> the app crashed right when I needed it most. Half-awake and fully frustrated,
> I decided to build my own version: one that could survive offline and my
> occasional parental meltdowns.
>
> This talk explores how everyday chaos (whether in parenting or in production)
> can inspire better engineering. I’ll share how concepts like caching and
> feature flags turned a midnight side project into a small, reliable system.
>
> Attendees will walk away with practical ideas for making their own
> applications more dependable under real-world conditions. Basic programming
> experience is helpful, but the talk is accessible to anyone interested in
> software reliability, distributed systems, or stories from the trenches of
> sleepless nights.
>

<https://streamlit.io/>

---

## More. Better.

Mario Munoz

> What would it look like to be a good software engineer? Would it mean that you
> are able to solve complex problems with proven solutions? Or would it mean
> that you can provide novel and creative ways to solve hard problems? The
> introduction of AI tooling into a developer's workflow promises gains in
> productivity. But what does that mean? More code? Better Code? Less toil? More
> time?
>
> Some executives bullish on this technology claim that AI assistants will
> eventually shorten workers' work weeks. However, the likeliest scenario is not
> a shorter work week, but increased demands within the same time constraints.
>
> How do we become better engineers within the current climate of overhyped AI
> technologies?

---

## A bridge over (not) troubled waters: Collecting marine data from your couch

Sarah Kaiser

Cassandra Granade

> Do you ever have a weird feeling that something around you is off? I certainly
> do, and one recent recurring thought I have is that the vintage boat I'm
> helping restore has sunk. I decided to use the tools available to me to put my
> mind at ease: software, a soldering iron, and stubbornness. My crewmate and I
> have built a way to get live data from our boat while on the couch at home at
> 3 am :) Data is a great way to reduce anxiety, and in this case has also
> generated a rising tide of interest in marine tech infrastructure. In this
> talk, we will give you a tour the cool OSS tools I have discovered for
> collecting telemetry on boats, a specialized marine data collection platform
> (Signal K), and an MQTT bridge to bring it all into my smart home dashboards
> on Home Assistant.

---

## Creating Music with Python!

Herve Aniglo

> In this talk attendees will learn about Jython, an open source implementation
> of the Python programming language, integrated with the Java platform for
> music making and creative programming activities.
>
> Attendees will leave this talk with an understanding of Jython libraries for:
> music making image manipulation building graphical user interfaces (GUIs),
> connecting to external MIDI and OSC devices music transcription and playback
> audio looping, computer-aided music composition development of computer-based
> musical instruments (including hybrid instruments) live performance. Live demo
> where I will turn my computer into a musical instrument to play music made by
> Beethoven, Deep Purple, Tupac Shakur, Mozart, and Deep Purple.

<https://jythonmusic.me/>

Neat demo of using Python code to create music

---

## Visual Unit Tests and Live Coding

Don Kirkby

> When I write Python code to build graphical reports or user interfaces, I wish
> it felt more like Inkscape or Powerpoint where you can immediately see the
> effect of your changes.
>
> In this talk, I'll demonstrate techniques I've developed that combine unit
> testing and live coding to create a Python environment that feels closer to
> Inkscape or Powerpoint. I'll also talk about some of the challenges of writing
> visual unit tests.
>
> If you haven't written unit tests yet, you can still get some ideas from this
> talk. You could also read my essay on test-driven development to get a head
> start.

<https://donkirkby.github.io/>

<https://donkirkby.github.io/testing>

<https://pypi.org/project/space-tracer/>

Example of using visual diffing for tests on matplotlib snippets

---

## Introducing t-strings: f-strings with superpowers

Dave Peck

> Python 3.14 introduces t-strings: template string literals that look like
> f-strings but evaluate to a Template instance instead of a str. This opens up
> exciting possibilities for safer string processing (avoiding injection
> vulnerabilities in SQL and HTML) and powerful custom formatting (like HTML
> templating directly in Python), all while using the familiar f-string syntax
> developers already know and love.
>
> In this talk, I'll describe what t-strings are and how they differ from
> f-strings and other common Python formatting tools. I'll explore when they're
> a good fit for new projects and how to use them effectively in everyday code.
> I'll also demonstrate two libraries — tdom (HTML) and t-sql (SQL) — and close
> with a live tooling demo in VS Code showing the current state of formatting,
> linting, and syntax highlighting support.
>
> Attendees will leave knowing when to reach for t-strings, how to adopt them
> safely, and which tools can improve their developer experience.

T strings are not strings

<[fstrings.wtf](https://fstrings.wtf/)>

<https://pypi.org/project/tdom/> -- t-string based HTML templater library

Possibly use as an alternative to Django templates?

Similar to JSX

<https://t-strings.help>

<https://davepeck.org>

---

## Closing Remarks

organizers@pycascades.com

Ask your work to sponsor this conference
