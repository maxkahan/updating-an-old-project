# Max's Python project improvement checklist!

This is a list of guidelines that can be referred to when starting to work on a Python project that needs some attention. The main motivation for this list was my work on the [Vonage Python SDK](https://github.com/Vonage/vonage-python-sdk).

## Understanding the project
* Look up documentation on the project and how it works.
* Check the project structure - how is code organised?
* Use the code! Make some "Hello, world" programs using it.
* What versions of Python does the project claim to support?
* Read the tests.
* Install the dependencies - check they're still compatible with current Python versions.
* Run the tests! (Run them on a Python version the project definitely supports, then on the most recent version.)
* Check what (if any) validation is done on inputs.
* Use static and behavioural analysis tooling to get in-depth code metrics.
* Use a code coverage tool (e.g. [coverage](https://coverage.readthedocs.io/en/6.5.0/)) to work out what parts of the code have been tested.
* Use mutation testing (e.g. [mutmut](https://mutmut.readthedocs.io/en/latest/)) to understand how reliable the tests are likely to be!
* Use [Snakeviz](https://jiffyclub.github.io/snakeviz/) to understand and visualise the call stack.

## Making changes
* Trust is key - make sure your users know they can trust your releases.
* Organise the code into logical modules/classes.
* Tests - are they sensible? Do they test expected behaviour?
* Use semantic versioning and deprecate in minor releases.
* Major release == breaking change, so only remove deprecated code in a major release.
* Leave some time between introducing a deprecation and removing the code, and leave time between major releases.
* Make changes to the code at the same time as you deliver new features, so your users have a reason to upgrade!

## Enhancing the project and looking forward
* Add custom errors and give specific messages when they're thrown in your code.
* Consider making code async if the project spends a lot of time waiting for IO-based operations, but only if it will really help your users.
* Consider validating input with [Pydantic](https://pydantic-docs.helpmanual.io/).
* Use metrics like mutation score to keep your test quality high.

## Handing over a codebase
2 weeks before handover:
* Stop accepting new work.
* Finish the existing features.
* Merge the PRs. 
* Close the feature branches.
* Document the state of the code.

## Trust is key
The code's users must be able to trust your releases, and your team must be able to trust you to deliver new features whilst fixing up the code.

Good luck, and happy fixing!
