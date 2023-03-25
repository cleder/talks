Thanks a lot for for coming.
I'm Christian Ledermann, I work for Oomnitza, an enterprise technology management company and  today i will tell you a tale of two kitchens or how to go about hyper modernizing your code base.

What  i'm going to talk about is:
- what is hyper modern python?
- why we would like our code base to be hyper modern.
- how to get there, from our legacy code to a nice hyper modern code base.

What is hyper modern python modern python?
The idea stems from an article series with the same title by Claudio Jolowicz and is an opinionated guideline about best practices and clean code in python in the 21st century.

The title of the talk is 'A tale of two kitchens', what do I mean by that?

Kitchen one is messy, sink overflowing with unwashed dishes, dirty dishes with rests of food on the working surface next to the sink, dirty pots and pans partially blackened with dirt on the working surfaces and stove, scraps of food lying around.

Kitchen two is tidy and clean, sparkling steel pots, utensils carefully stored away on hooks on the wall, cupboards with well organized utensils and spices, high tech kitchen gadgets in immaculate white.

Which kitchen do you think is better in terms of security, health and safety, where would you deliver faster, deliver, higher quality out of.
If you had to work in those kitchens where would you get a better job satisfaction and personal growth?

If you think it's kitchen one please raise one hand and if it's question two please raise two hands.
I just wanted to see an entire auditorium doing a 'Mexican La Ola Wave' :-D
In conclusion that  in a game of would you rather, kitchen one is the unanimous winner.

But in reality some of us work in a kitchen that looks more like this:
A messy Kitchen with fire-damage, sink overflowing with unwashed dishes, dirty dishes with rests of food, mould growing on them, dirty, sooty, mouldy pots and pans on the working surfaces and stove, some trash lying around, a blazing grease-fire in a big pot on the stove, a fireman with a hose trying to extinguish the fire.


Let's talk about why we  want to clean up our code base and make it hyper modern.

Clean consistent code minimizes context switches.
If our code looks the same everywhere we need  less mental overhead to switch in between different code styles.
A 'LEAN' principle is to eliminate waste sorry to reduce friction, this helps us with it.
The Broken Window Theory suggests that when bad behavior is not corrected immediately, it shows people that there is no downside to breaking the rules, practices or standards. If there is no negative outcome, cutting corners becomes acceptable and in time quality always decreases.
Most engineers have heard of the 'boy-scout rule': 'Always leave the code better than you found it.' it's much easier to leave the place in a better state than you found it if you found it in good condition in the first place.

how do we start to improve the quality of our code?

we start small we start simple and start now!
where do we start?

'pre-commit' is nowadays pretty much our weapon of choice to execute code when you check in modifications.
I am not talking about the git pre-commit hook but the 'pre-commit' python package.

You won't have much discussion about imports, this is a good point to start:
- `isort` will sort the imports for you
- `absolufy-imports` converts relative imports to absolute.
- `removestar` replaces `import *` imports in Python files with explicit imports
- `unimport` removes unused import statements.


To get all your code into a consistent format the next step is to run a formatter.
I recommend `black`, the well-known uncompromising code formatter, which is the most popular choice.
Alternatives to `black` are `autoflake` and `yapf`, if you do not agree with `blacks` constraints.

`pyupgrade` and `flint` are examples of tools that modify your code base from earlier python versions into the newest python syntax, rewriting all string formats into f-strings and similar things.

Ultimately we want to test our code with `flake8` and plugins to enforce a more consistent code style and to encourage best practices.
When you first introduce `flake8` or a new plug-in commonly you have a lot of violations that you can silence with a `#noqa` comment.
When you first introduce a new `flake8` plugin, you will likely have a lot of violations, which you silence with `#noqa` comments. Over time these comments will become obsolete because you fixed the. `yesqa` will automatically remove these unnecessary `#noqa` comments.

A more modern alternative for `flake8` is `Ruff`: `Ruff` can be used to replace `Flake8` (plus a variety of plugins), `isort`, `pydocstyle`, `yesqa`, `eradicate`, `pyupgrade`, and `autoflake`, all while executing tens or hundreds of times faster than any individual tool. `Ruff` goes beyond the responsibilities of a traditional linter, instead functioning as an advanced code transformation tool capable of upgrading type annotations, rewriting class definitions, sorting imports, and more.

# security

Automated security scanning tools are out there as well. Bugbear is not a security tool, but it allows you to fix common mistakes, such as passing a list as the default value for a parameter, and alerts you if you should not do that. Bandit is a security scanner focused on security, such as SQL injection and cross-site scripting exploits. Safety and Dependenbots scan your dependencies, to see if they are up to date or have any security issues.
You improve what you measure, and the easiest thing to measure is your test coverage, with tools like Coverage and Diff Cover. The next thing that is easy to measure is the complexity of your code, with tools such as McCabe, Radon, Xenon, and Lizard. Lizard is particularly helpful as if it thinks the code is too complex, it most likely is. Cognitive Complexity, a Flake8 plugin, is a newer tool which takes into account how humans process code, including decision points and recursions.

# Typing

We want our code to be hyper-modern, so using Mypy is a great way to ensure that our types are correct. However, it can be a big challenge to manually type-annotate legacy code. Luckily, there's MonkeyType, which observes the types flowing into and out of your functions and provides a rough draft of type annotations. Facebook's answer to Mypy, Pyre, has a command called `infer` which infers the types from code flow, as well as the types that are already present in the code. Similarly, Google's PyType has a slightly different command-line interface. We can also type-check at runtime with tools like Typeguard. However, these come with an overhead and you may mot want to use them in a production environment. Typeguard can be used for testing to ensure that the right types are being passed around when you run your tests.

# Tests

Tests need a little love too when we are hyper modernizing our code.
Writing unit tests still makes the code much more readable and precise, and `Pytestify` and `Unittest2Pytest` are both tools to convert old unit tests into Pytests.
The Hyper Modern Python's article series doesn't have a strong opinion on testing, apart from `Pytest`.

The Hypothesis library is a property-based testing framework for Python that allows you to write tests that automatically generate input data based on certain properties or invariants of your code. Some of the advantages of using Hypothesis include:
- Comprehensive testing: By generating a wide range of input data, Hypothesis can help you find edge cases and unexpected behaviors that might not be caught by traditional, manually written tests.
- Reduced test maintenance: Since Hypothesis tests are based on properties of the code rather than specific input data, they are less likely to break when the code is refactored or changed.
- Increased confidence in code: By testing a wide range of inputs and edge cases, Hypothesis can give you more confidence that your code is correct and behaves as expected.
- Easy to use: Hypothesis is easy to integrate into existing test suites and has a simple, intuitive API.
- Easy debugging: In case of test failure, the Hypothesis library provides an easy way to reproduce the failing test case, which can help debugging the issue.
- Support for different types: Hypothesis supports different types of input, including integers, strings, lists, and dictionaries.
Using Hypothesis can help you write more comprehensive and robust tests that are less prone to break when your code changes and provides an easy way to debug test failures.
Writing tests with Hypothesis frees you from the tedium of deciding on and writing out specific inputs to test.
The `hypothesis.extra.ghostwriter` module can write your test functions for you!
The idea is to provide an easy way to start property-based testing, and a seamless transition to more complex test code - because ghostwritten tests are source code that you could have written for yourself.

For working with web APIs, there's `SchemaThesis`, which is built on `Hypothesis`.
It generates tests and data based on an OpenAPI or GraphQL specification and can be used as a service without any coding knowledge.

But who is watching the watchmen?
How do you know that your tests are actually testing what you think they are, and that 100% test coverage is really enough? Mutmut, a mutation testing tool, can help answer this. It runs all of the tests and then changes something in the code to see if the test breaks. If it passes, that's a surviving mutant, which is a bad thing, meaning the test didn't test for that. However, using Mutmut takes more time than MonkeyType, and the tests can take even longer to run - so you need to be specific about what you want to test.

# Upgrades

Upgrades on a regular basis are made easy with PyUpgrade, which ensures your Python syntax is up-to-date.
There are also tools for specific frameworks, such as Django-Upgrade and Django-Codemod, which can convert Django from version 1.11 up to 4.0.
If you're working with Django, these tools can be helpful in making the necessary changes. Alternatively, you can create your own code modifications tool using LibCST (CST stands for Contract Concrete Syntax Tree)
## Refactoring as a Service.
Sourcery is one of the sponsors at this event and is a great tool for small refactorings. Sonar Cloud is also in the same space and can be found downstairs.
For test coverage, Coverage.io is a great software that can highlight pull requests and show what is covered and what is not.

# Refactoring

Real refactoring is about creating code that is maintainable, extensible, and modular.
It involves finding patterns in the code to avoid repetition.
This is done by following certain principles such as the Don't Repeat Yourself (DRY) principle, the SOLID principles (Single Responsibility, Open-Closed, Liskov Substitution, Interface Segregation, Dependency Inversion) and the CUPID principles (from the lightning talk "Why Every Single SOLID Principle is Wrong").
These principles are not laws, but rather guidelines to help create better code.

When refactoring code, it is important to remember that "perfect is the opposite of done". Refactoring is an iterative process, and there may be times where code is not perfect, but is still useful and can be improved upon over time.
It is important to focus on creating code that is maintainable and extensible, rather than striving for perfection.

# Take Away

In summary, we discussed Hyper Modern Python, why we should strive to make our code as Hyper Modern as possible, and some tips and tricks for modernizing legacy code.
We also touched on refactoring in general.
Ultimately, the takeaway is that "done is better than perfect" - even for talks!
Thank you for listening.

# Questions
Q: If I have the worst legacy code base you've ever seen, what's one first step I can sell?

A: The first thing I would do is enforce an import order. This is usually a no-brainer and nobody will want to die on that hill or argue too much about it. Additionally, I would introduce a pre-commit hook so any time a change is committed, it will be checked and corrected.

# Notes:

GPT interprets the acronym CUPID as (Composability, Uniformity, Predictability, Idempotence, Discoverability)
