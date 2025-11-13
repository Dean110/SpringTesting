# Types of Tests
## Unit Tests vs Integration Tests
I group tests into two separate classes: unit and integration.

Unit tests are for testing the behavior of one specific _unit_
of code.
A unit of code is a class or function.
Unit tests run fast, have specific expectations, and are limited in scope.
Their strength is in the fact that many unit tests can be run very quickly provide specific insight into what behavior went wrong.
We want unit tests to break if we are working on a feature request for modifying behavior.
We also want to make sure that we are not testing dependencies when we write unit tests.
The scope of a unit test is that one class or function under test.
When we decide to create dependencies in our code it should be because we are using a tested tool, or because we have recognized that our code is starting to get too complicated and the solution lies in injecting a layer of abstraction. 
A unit test's job when it meets a dependency is not to test the dependency's behavior.
Again, because this is important, a unit test's job when it meets a dependency is not to test the dependency's behavior.
Dependencies are named as such because we depend on them:
they are either trusted tools provided from external sources,
or tools that we develop ourselves that have (hopefully) already been tested internally.
A unit test's job is to make sure the code under test communicates with its dependencies in a way that we expect and handles the returned message in a way we expect.
If a unit of code has no dependencies, we expect the unit test to affirm the primitive data given to it was handled in a way we desire.
Writing code that is easily tested with unit tests is a sign that you are following good principles of software development.
If you write code that is hard to unit test without complicated setups, you might be in a position where you are writing code that is difficult to maintain and overly complex.

Integration tests are for testing the behavior of multiple units of code working together.
Pretty much every test that is not a unit test is an integration test.
Integration tests have many different flavors: component, layer, contract, acceptance, end to end, ect.
Since integration tests combine different parts of an application, they are more expensive.
They are more complicated to setup, maintain, time intensive to run, and difficult to troubleshoot.
Integration tests that are written poorly can end so expensive that there is a natural tendency to not write them at all.
However, when they are well written, with clear purpose, they are a powerful tool to confirm the orchestration of all the units of code you have assembled are performing as expected.
