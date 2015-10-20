# Palantir Behat Drupal Extension

The Palantir Behat Drupal Extension provides additional step definitions for testing Drupal sites using [Behat](http://behat.org),
[Mink Extension](https://github.com/Behat/MinkExtension).


## What can I do with this?

### Extra step syntax

* `NodeContext`: test viewing and editing nodes by title
* `DrupalCommentContext`: test commenting functionality
* `DrupalOrganicGroupsContext`: test access to Organic Groups
* `EntityDataContext`: test field data and properties on nodes, terms, and users directly, without relying on output (or write a simpletest...)

### Disable module functionality during tests

* `DrupalAutoNodetitleContext`: tag scenarios with `@disableAutoNodetitle` to bypass automatic title generation; sometimes this is required in order to have predictable test content
* `DrupalWorkbenchModerationContext`: tag scenarios with `@disableWorkbenchModeration` to bypass moderation

### Extend for your project's needs

* `MarkupContext`: extend this class to use the `assertRegionElementText` method, and encapsulate complex markup in a custom context rather than in the Gherkin acceptance criteria

## How do I add this to my project?

If you are already using the `Drupal\DrupalExtension` Behat extension, it is very easy to add these contexts--and if not, go set that up before attempting to use these custom contexts.

First, add this package to your `composer.json` file:

```
    "repositories": [
        {
            "type": "vcs",
            "url": "git@github.com:palantirnet/palantir-behat-extension.git"
        }
    ],
    "require": {
        "palantirnet/palantir-behat-extension": "dev-master"
    },
```

Then, add the specific contexts you want to use to your project's `behat.yml` file:

```
default:
  suites:
    default:
      contexts:
        - Palantirnet\PalantirBehatExtension\Context\NodeContext
```

----
@copyright (c) Copyright 2015 Palantir.net, Inc.
