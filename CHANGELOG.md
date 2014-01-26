Prospector Changelog
=======

Version 0.5
---
* Full PEP8 compliance can be turned on using the `--full-pep8` flag, which overrides the defaults in the strictness profile.
* The PEP8 tool will now use existing config if any is found in `.pep8`, `tox.ini`, `setup.cfg` in the path to check, or `~/.config/pep8`. These will override any other configuration specified by prospector. If none are present, prospector will fall back on the defaults specified by the strictness.
* Pylint version 1.1 is now used.
* The `--path` command line argument is no longer required, and prospector can be called with `prospector path_to_check`.

Version 0.4.1
---
* Additional blending of messages - more messages indicating the same problem from different tools are now merged together
* Fixed the maximum line length to 160 for medium strictness, 100 for high and 80 for very high. This affects both the pep8 tool and pylint.

Version 0.4
---

* Added a changelog
* Added support for the [dodgy](https://github.com/landscapeio/dodgy) codebase checker
* Added support for pep8 (thanks to [Jason Simeone](https://github.com/jayclassless))
* Added support for pyflakes (thanks to [Jason Simeone](https://github.com/jayclassless))
* Added support for mccabe (thanks to [Jason Simeone](https://github.com/jayclassless))
* Replaced Pylint W0312 with a custom checker. This means that warnings are only generated for inconsistent indentation characters, rather than warning if spaces were not used.
* Some messages will now be combined if Pylint generates multiple warnings per line for what is the same cause. For example, 'unused import from wildcard import' messages are now combined rather than having one message per unused import from that line.
* Messages from multiple tools will be merged if they represent the same problem.
* Tool failure no longer kills the prospector process but adds a message instead.
* Tools can be enabled or disabled from profiles.
* All style warnings can be suppressed using the `--no-style-warnings` command line switch.
* Uses a newer version of [pylint-django](https://github.com/landscapeio/pylint-django) for improved analysis of Django-based code.