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

Note that a test change which doesn’t conform to the current spec source on the `master`
branch should not be merged before the corresponding spec change is merged to `master`.

If testing a particular spec change isn’t practical due to web-platforms-tests limitations,
explain why in the spec-PR commit message, file a
[wpt issue](https://github.com/w3c/web-platform-tests/issues)
describing the limitation, and add the
[`type:untestable`](https://github.com/w3c/web-platform-tests/issues?utf8=%E2%9C%93&q=label%3Atype%3Auntestable%20)
label to the issue.
