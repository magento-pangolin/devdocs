---
title: Debugging MFTF Tests
mftf-release: 2.3.13
redirect_from: /guides/v2.3/magento-functional-testing-framework/2.3/debugging.html
---

Debugging within the Magento Functional Testing Framework can be helpful in identifying test bugs by allowing you to pause execution to either:

- Examine the page.
- Check returned data and other variables being used during run-time.

This is straightforward to do once you create a basic Debug Configuration.

## Prerequisites

- [Xdebug]
- PHPUnit configured for use in [PHPStorm]

## Creating Debug Configuration with PHPStorm

- Download the Codeception Framework plugin for PHPStorm (`PhpStorm->Preferences->Plugins`).
- Click `Edit Configurations` on the configuration dropdown.
- Click `+` and select `Codeception` from the available types.
- Find the `Custom Working Directory` option and set the path to your `dev/tests/acceptance/` directory.

If you get a warning `Path to Codeception for local machine is not configured.`:

- Click `Fix`, then `+`, and select `Codeception Local`.
- Click `...` and locate `/vendor/bin/codecept` in your Magento installation folder.

At this point, you have a couple choices in how to select the test you want to debug.
The easiest method of tagging a test for debugging is the following:

- In your Debug configuration, locate `Test Runner options:` and set `--group testDebug`.
- When you want to debug a test you are working on, simply add `<group value="testDebug"/>` to the annotations (be sure to remove this after done debugging).

Your Debug Configuration should now be able to run your test and pause execution on any breakpoints you have set in the generated `.php` file under the `_generated` folder.

<!-- Link definitions -->
[Xdebug]: https://xdebug.org/docs/install
[PHPStorm]: https://github.com/SeleniumHQ/selenium/wiki/PageObjects