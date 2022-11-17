# A Tale of two Kitchens, hyper modernizing your codebase.

When starting a new python project, the “hypermodern” python ‘template’ is a popular choice. Its style is opinionated and strict, and it brings a consistent style and today's best practices. How do I bring my legacy codebase up to this standard?

## Summary
A consistent style and standard and the consistent use of the same tools in all your code, makes it easier to reason about, reduces context switching, thus reducing waste (in the [LEAN](https://en.wikipedia.org/wiki/Lean_IT) sense). A clean environment is good for your health and safety, enabling you to deliver quality faster.

This talk goes deeper into how to modernize your legacy codebase to reduce your technical debt, to make it easier for you to tackle the real challenges without ever having to discuss a style guide again. It will provide tips, tricks and tools to make your “hypermodernization” effort as smooth and easy as possible.

# Hypermodern Python

> The most important thing I have done as a programmer in recent years is to aggressively pursue static code analysis.  Even more valuable than the hundreds of serious bugs I have prevented with it is the change in mindset about the way I view software reliability and code quality.
>
> -- <cite>John Carmack</cite>


- [Hypermodern Python](https://cjolowicz.github.io/posts/hypermodern-python-01-setup/)
- [Hypermodern Python Cookiecutter](https://github.com/cjolowicz/cookiecutter-hypermodern-python)
- [Hypermodern Python Tooling](https://www.oreilly.com/library/view/hypermodern-python-tooling/9781098139575/)
# Tools

- [Awesome Python Code Formatters](https://github.com/life4/awesome-python-code-formatters)
- [Awesome Flake8 Extensions](https://github.com/DmytroLitvinov/awesome-flake8-extensions)
- [Awesome Python Typing](https://github.com/typeddjango/awesome-python-typing)
- [Awesome Python Testing](https://github.com/cleder/awesome-python-testing)
- [Awesome PyTest](https://github.com/augustogoulart/awesome-pytest)

## Security

- [Bandit](https://github.com/PyCQA/bandit) is a tool designed to find common security issues in Python code.
- [GuardDog](https://github.com/datadog/guarddog) is a CLI tool that allows to identify malicious PyPI packages.
- [Safety](https://github.com/pyupio/safety) checks Python dependencies for known security vulnerabilities and suggests the proper remediations for vulnerabilities detected.

# Slides

[A Tale of Two Kitchens](https://github.com/cleder/ep2022/blob/main/slides.pdf) Hypermodernizing Your Codebase.

# Recording

[EuroPython 2022](https://youtu.be/uwmQgCrCh2s)

# Related Talks

[EuroPython 2022](https://ep2022.europython.eu/) featured related talks about tools and techniques I only touched on in my talk.

- [Clean Architectures in Python - presented by Leonardo Giordani](https://youtu.be/C7MRkqP5NRI)
- [Automate cleaning code in few easy steps! - presented by Ester](https://youtu.be/7_FyRR3yN-k)
- [Automated Refactoring Large Python Codebases - presented by Jimmy Lai](https://youtu.be/ouDnaZxZKkc)
- [Lint All the Things! - presented by Luke Lee](https://youtu.be/9psDYv4kVvE)
- [Scalpel: The Python Static Analysis Framework - presented by Jiawei Wang](https://youtu.be/KNR1ppKTu2Q)
- [Property-based testing the Python way - presented by Emma Saroyan](https://youtu.be/EQjZgwufkYU)
- [Managing the code quality of your project. Leave the past behind: Focus on new code - Andrea Guarino](https://youtu.be/KK2GZFZ9_uA)
- [Protocols - Static duck typing for decoupled code - presented by Ran Zvi](https://youtu.be/adxG_7bBy1w)
- [`typing.Protocol`: type hints as Guido intended - presented by Luciano Ramalho](https://youtu.be/0_IQoxBFepw)


# Further Readings

- [What is Code Quality?](https://refactoring.fm/p/what-is-code-quality) Lessons learned in over 10 years of helping engineering teams create high quality software.
- [Type Annotation via Automated Refactoring](https://medium.com/building-carta/type-annotation-via-automated-refactoring-fd8edfe123d4)
- [Tips for clean code in Python](https://pybit.es/articles/tips-for-clean-code-in-python/)
- [Tools for rewriting Python code](https://lukeplant.me.uk/blog/posts/tools-for-rewriting-python-code/)
- [Static Analysis at Scale: An Instagram Story](https://instagram-engineering.com/static-analysis-at-scale-an-instagram-story-8f498ab71a0c)

# Closing Remarks

This is a git repository, treat it as one.
If you have questions, corrections or additions do not hesitate to join the [discussion](https://github.com/cleder/ep2022/discussions), create an [issue](https://github.com/cleder/ep2022/issues) or a pull request ;-)
