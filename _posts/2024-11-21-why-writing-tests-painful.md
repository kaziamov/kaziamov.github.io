---
layout: post
title: Why Writing Tests Can Be Painful
date: 2024-11-21 14:59
category: development
author: Ilia Kaziamov
tags: [testing, development, tips]
---

I found several reasons why it can be painful to write tests, and decided to briefly describe how to solve this.

**Situation 1. When it's unclear how to test and what exactly**

This is an indicator that the inputs for the task are not complete or there's no understanding of what really needs to be done. In this case, you just need to go and ask whoever is responsible for the task, clarify requirements, what the final result should be and from what to assemble this result (if it's an external data source, for example).

Then you simply prepare fixtures and write a test that describes the logic from beginning to end (e2e, if we're talking about backend). In the future, the internal implementation just needs to match this test. Then the branch is deployed to a stage where the user or testers can check that everything works as intended. All cases that don't work as needed are added to the rest in the format of new fixtures and new test cases.

**Situation 2. When code has high coupling and values are hardcoded inside the code**

If when writing code things like Dependency Injection are ignored and objects are either initialized inside other objects or taken from the global scope, this is an indicator that refactoring should be done, because tests will also be painful to write. The solution in a specific situation with global variables: move them to a separate module and create mocks for these objects to repeat the necessary logic. In tests, we patch the needed services with mocks and do everything the same as when writing regular tests.

**Situation 3. Code involves calls to an external service where data can change**

Testing code on real services is generally a bad practice because it's unethical and slow. In situations involving deletion of any objects inside another service, this is generally impossible. Let's imagine a simple case: we go to an external service to download data, filter data on our side and send a list of what should be deleted. In such a situation, all this can be tested locally. For the first request with data download, we prepare a fixture that can be a JSON response. We go to the service once, get data, save and mock real request with them. The second call for deletion, for example, with element IDs for deletion, we also mock. Create a fixture with send data based on documentation as an example. To check that everything is mocked correctly, you can enable airplane mode on the computer. If the test doesn't fall with network errors, it means everything is mocked correctly and you can just work on the code.

Share this post and write in comments what problems you have with tests.
