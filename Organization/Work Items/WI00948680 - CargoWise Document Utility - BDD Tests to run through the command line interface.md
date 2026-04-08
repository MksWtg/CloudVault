JW4 11-Aug-25 09:34 GMT+10:00:

  

Most of the BDD tests interact with business objects directly. Whilst there is nothing wrong with having BDD tests that work with business objects the real intention of them is to test required behaviour. To that end the BDD tests should be extended so that wherever possible they go through the command line interface. Only in the cases where we must use mocks to implement some environmental behaviour should we revert to testing the business objects directly.

  

Further to this, the tests should isolate each feature that is exposed on the command line. That way the tests are a list of requirements, not just a set of scenarios that achieve code coverage.

  

M22 10-Oct-25 14:03 GMT+11:00:

  

Update documentation to include the fact that running the UT is now a valid form of functional testing (in cases except those where we mock environmental behaviour)