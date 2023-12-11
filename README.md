# Log-Driven Development (LDD) - [ldd.coders.info](http://ldd.coders.info)


## LDD Patterns

**LDD** align closely with Test-Driven Development (TDD) and behaviour-driven development (BDD), but with a particular focus on understanding system behavior through logs, is working based on such main principles:

+ TDD - Test-Driven Development
+ BDD - Behaviour-Driven Development
+ Reverse Engineering
+ Modular design to create monorepo
+ Continouous improvement with CI/CD integration

This method allows you to create an autonomous system that, starting from only the system logs, will be able to recreate it, step by step, using humans and machines



## Definition

Log-Driven Development (LDD) is a software development approach where the design and construction of software are primarily informed and driven by the analysis of system logs. In this approach, logs are used as the fundamental source of truth for determining how a system should behave in both routine and exceptional circumstances. Developers use logs to abstract system requirements and functionality, write targeted tests, and then develop system features iteratively while respecting the guidance provided by the logs.


## Specification


### Log Analysis
 Understanding Expected and Unexpected Behaviors:
 
- Collect and review logs from the system to examine successful operations, errors, warnings, and any other significant events.
- Document system behavior as described by the logs, distinguishing between normal behavior and exceptions.

Review system logs to understand how the existing software behaves. This step involves deducing requirements, specifications, and system functionality strictly from the information contained in logs, which may represent both expected and unexpected system behavior.


### Mock Implementation
Abstraction of Functionality:
- Develop mock implementations or skeleton functions/classes that encapsulate the expected behavior inferred from the logs.
- Ensure mocks provide expected outputs for various input scenarios as evidenced by the logs.

Developers create mock functions that produce the expected outputs for given inputs based on the analyzed behavior. 
These mocks serve as temporary stand-ins for the actual implementations until they are developed.


### Test Creation
TDD/BDD Principles:
- Derive and write a comprehensive suite of test cases to verify the correct behavior of system components.
- Adhere to classical TDD practices: tests should initially fail since the mocks only simulate real functionality.

Developers write tests for the expected functionality, essentially formalizing the behavior observed and expected from the logs. 
These tests are written to fail initially, as the actual functions are not implemented yet.

### Real Implementation
Code improvement:
- Step by step, replace the mock implementations with actual code, ensuring at each step that the code passes all tests.
- Optimize and refactor as necessary, always maintaining the integrity of the tests.

Actual functional code is gradually introduced to replace the mock bodies. 
The development follows the previously established tests.


### Continuous Integration and Testing
Iterative Development:
- Automatically build and test the system regularly — or even after every change — to reveal integration errors as soon as possible.
- Keep logs for ongoing analysis to feed back into the development cycle for continuous improvement.


### Summary 

By using the LDD principle to create software based on logs, you can create a more autonomous system based on its input and output data at the development stage, where the person responsible for the provided data and the designer will directly influence the generated code.
In LDD is no documentation, you just observe what comes out in the logs and create code that will react accordingly to the input data, and these logs must contain properly formatted input and output data
The Dialoget decorator can be used to describe a function in the form of a sentence that reflects how this function works
+ [dialoget/python: python.dialoget.com is a test framework for multilanguage source code, based on decorators](https://github.com/dialoget/python)

with one decorator you get 3 benefits: 
1. Creating a human/AI friendly csv log
2. Creating a schema for testing
3. Detecting when you use a similar sentence structure in another app and signaling reuse


Using such an approach can lead to a thorough understanding of the system and its interactions, as well as how to handle various types of data and errors. 
However, care must be taken when using logs as the sole source of truth; logs can sometimes be incomplete or misrepresentative. 
Thus, LDD should be complemented by additional information and insights from other system documentation and stakeholder input where possible.









