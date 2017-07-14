# Test plan — Payment Request API

This document provides specific information about testing related to the
Payment Request API spec.

## Tests are required for all normative spec changes

All PRs with normative changes to the spec source must have a corresponding PR in
[the web-platform-tests Payment Request API test suite](https://github.com/w3c/web-platform-tests/tree/master/payment-request)
— either adding new tests or modifying existing tests — or else must include in the PR
commit message an explanation why tests aren’t needed for the spec change.

Typically, both the PR for a spec change and the PR for the associated tests will be merged
around the same time. If the spec PR is approved but the tests PR needs more work, add the
[`needs tests`](https://w3c.github.io/spec-labels.html) label to the spec PR. Or if the
tests PR is approved but the spec PR hasn’t yet been OK’ed, add the
[`status:needs-spec-decision`](https://github.com/w3c/web-platform-tests/issues?utf8=%E2%9C%93&q=label%3Astatus%3Aneeds-spec-decision%20)
label to the tests PR.

Note that a test change which doesn’t conform to the current spec source on the `gh-pages`
branch should not be merged before the corresponding spec change is merged to `gh-pages`.

If testing a particular spec change isn’t practical due to web-platforms-tests limitations,
explain why in the spec-PR commit message, file a
[wpt issue](https://github.com/w3c/web-platform-tests/issues)
describing the limitation, and add the
[`type:untestable`](https://github.com/w3c/web-platform-tests/issues?utf8=%E2%9C%93&q=label%3Atype%3Auntestable%20)
label to the issue.

## How to contribute to the test suite

https://github.com/w3c/web-platform-tests/tree/master/payment-request
has existing tests for the Payment Request API.

https://w3c-test.org/payment-request is a Web mirror of those tests.

You run the Payment Request API tests in a browser to check whether the browser
passes the tests. So the tests are essentially browser tests—browser-conformance tests.

The Payment Request API tests are part of the W3C master test suite
maintained in https://github.com/w3c/web-platform-tests/ and we rely on `git` as
our version-control mechanism, so we seek contributors who ideally have
some general familiarity/experience in working with `git` (but that’s not a
hard requirement—you can learn `git` as you go).

The core of the W3C test infrastructure is a JavaScript-based test harness called
 _`testharness.js`_. The documentation for `testharness.js` is at
http://web-platform-tests.org/writing-tests/testharness-api.html

For contributors, understanding how `testharness.js` works and how to write
tests using it is the most important requirement.

The general how-to docs for W3C test contributors are at
http://web-platform-tests.org/ and
https://github.com/w3c/web-platform-tests/blob/master/README.md has
some other high-level getting-started info.

The best place for contributors to ask questions and get help quickly is
on the IRC channel `#testing` on the [`irc.w3.org`](http://irc.w3.org/)
server. We also use the mailing list `public-test-infra@w3.org`, which
contributors can subscribe to by sending a message with `Subject: Subscribe`
to `public-test-infra-request@w3.org`.

The best place for anyone to start reading in order to get familiar with
what skill set we need from test contributors is the `testharness.js`
documentation at
http://web-platform-tests.org/writing-tests/testharness-api.html

What we are ideally looking for in contributors is:

- skill in JavaScript

- general understanding about how JavaScript works in browsers (the
  execution model, the event loop, etc.)

- general understanding of core JavaScript APIs for the web runtime—for
  example, DOM APIs and the async nature of most of those APIs

- some existing experience with doing browser testing

See also https://lists.w3.org/Archives/Public/public-payments-wg/2017Jun/0023.html
