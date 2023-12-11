# Log-Driven Development (LDD) - [ldd.coders.info](http://ldd.coders.info)


## LDD Patterns

**LDD** align closely with Test-Driven Development (TDD) and behaviour-driven development (BDD), but with a particular focus on understanding system behavior through logs, is working based on such main principles:

+ TDD - Test-Driven Development
+ BDD - Behaviour-Driven Development
+ Reverse Engineering
+ Modular design to create monorepo
+ Continouous improvement with CI/CD integration

### Benefits

Log-Driven Development method allows you to create an autonomous system that, starting from only the system logs, will be able to recreate it, step by step, using humans and machines
You can start with legacy code and just conenct the decorator to record behaviours
After you know how behaoviuuor the seoftware
You can develop new module and test the code based on before genrated logs with the same decorator and after time with refactored data - migrated to a new format
you can use 2 format of logs data through connect two different data logs through different decorator format


### Log-Driven Development (LDD)
Log-Driven Development (LDD) is a software development approach where the design and construction of software are primarily informed and driven by the analysis of system logs. In this approach, logs are used as the fundamental source of truth for determining how a system should behave in both routine and exceptional circumstances. Developers use logs to abstract system requirements and functionality, write targeted tests, and then develop system features iteratively while respecting the guidance provided by the logs.


## Definitions


### Logging 

Logging is the process of recording information about the operation of a program. This can include a variety of data, such as informational messages, warnings, errors, and debugging messages. The purpose of logging is to provide insights into the behavior of the application, facilitate debugging, and help with monitoring and troubleshooting. 
Logs are usually persistent, which means they are saved to files or databases for later review and analysis. 
They historically have different levels of severity, such as DEBUG, INFO, WARN, ERROR, and CRITICAL, which help categorize the log entries based on their importance or urgency.

Key aspects of logging include:

- **Auditing**: Keeping a record of significant events, which could be important for security audits, compliance, or business analysis.
- **Diagnostic**: Helping developers or system administrators understand the system's behavior, particularly useful when an error occurs or for post-mortem analysis of a failure.
- **Performance Monitoring**: While not as focused on performance as profiling, certain logs can help to indicate slow operations or resource bottlenecks.
- **Event Recording**: Logging all manner of events, from routine operations like user logins to rare occurrences like configuration errors.


### Debugging

Debugging is the systematic process of identifying, isolating, and fixing bugs or defects within a software application or system. A bug is typically an error or flaw in the software that causes it to produce incorrect or unexpected results, or to behave in unintended ways.

Key aspects of debugging include:

- **Problem Reproduction**: Attempting to reproduce the reported issue under controlled conditions to understand the circumstances under which it occurs.

- **Hypothesis Formulation**: Developing theories about the root cause of the bug based on an understanding of the code and its behavior.

- **Instrumentation**: Adding logging statements or using debugging tools to collect more information about the software's behavior during execution.

- **Breakpoint Setting**: Using a debugger to pause execution at specific points in the code in order to inspect the state of the application.

- **Step-by-Step Execution**: Running the program one line or instruction at a time to observe how the state changes and where it deviates from expected behavior.

- **Variable Inspection**: Examining the contents of variables and the state of the application at various points of execution to identify anomalies.

- **Fix Implementation**: Applying code changes aimed at correcting the identified problem.

- **Testing and Verification**: Running the application to confirm that the fix resolves the issue without introducing new bugs.

 
### Profiling
Profiling is the practice of measuring the space (memory) and time complexity of a program's operation. It is a form of dynamic program analysis that can be performed either during development (to optimize code) or after deployment (to diagnose performance issues). Profiling aims to identify parts of a software program that are consuming disproportionate amounts of system resources, such as CPU time, memory usage, disk I/O, or network bandwidth.

Key aspects of profiling include:

- **Performance Bottlenecks**: Discovering which parts of the code are slowing down the program's execution or using too many resources.

- **Function Calls Analysis**: Measuring the frequency and duration of function calls to determine which functions are called most often and which take the most time to execute.

- **Memory Allocation**: Tracking the memory allocation and deallocation to find memory leaks or spots of inefficient memory use.

- **CPU Utilization**: Analyzing how the program uses the CPU to identify heavy computation or concurrency issues that may be limiting performance.

- **Hotspots Identification**: Identifying "hotspots" in the code—sections that are executed most frequently and become candidates for optimization.

- **Input/Output Operations**: Measuring the I/O operations to optimize file handling and data transfer processes, especially in data-intensive applications.

Profiling tools typically provide reports that help developers focus their optimization efforts where they will have the greatest impact on performance. Some profiling tools also offer visual representations of the data, such as call graphs or heat maps.

Profiling is essential for:

- Improving the efficiency of an application by optimizing the use of system resources.
- Ensuring that an application can scale effectively to handle increased loads.
- Providing a better user experience by making software more responsive.

[Jack Whitham - Profiling versus tracing](https://www.jwhitham.org/2016/02/profiling-versus-tracing.html)


### Tracing

Tracing is the practice of recording a chronological log of events or operations within a software application or system. It is a form of dynamic analysis that captures detailed information about a program's execution path, data flow, and interactions with system components or external systems. Tracing helps developers and system administrators understand the behavior of complex systems in real-time or after the fact.

Key aspects of tracing include:

- **Event Logging**: Collecting detailed records of discrete events that occur as the software runs. These records typically include timestamps, event types, and context-specific data.

- **Execution Flow**: Monitoring the flow of execution through the application, often capturing function or method calls, returns, and exceptions.

- **Data Flow Analysis**: Observing the movement and transformation of data within the application, which can be useful for diagnosing issues related to data processing or corruption.

- **Systems Interaction**: Recording how the application interacts with other systems, services, or components, which can be crucial for distributed systems or service-oriented architectures.

- **Distributed Tracing**: When dealing with microservices or distributed architectures, tracing can provide insight into how requests propagate through various services, helping to pinpoint latency issues or failures in the system.

- **Performance Monitoring**: Although tracing is not primarily focused on performance analysis, it can highlight where delays or bottlenecks occur within the execution chain.

Tracing tools typically generate large amounts of data. To manage this, the tools may allow for varying levels of detail (verbosity), or developers may implement selective tracing to capture information only about specific components or under certain conditions.

The value of tracing lies in its ability to provide a comprehensive, time-ordered account of what the system does at runtime. This visibility makes tracing particularly useful for:

- Diagnosing complex, intermittent issues that might not be replicable in a debugging environment.
- Understanding system behavior under load or during interactions that involve multiple components.
- Providing context for performance metrics, helping to turn raw data into actionable insights.
- Ensuring that systems are behaving as designed and can help validate system logic and data flow.



### Debugger Driven Development (DDD)
is a technique where the developer iteratively writes and tests their code using a debugger to understand the behavior of the software at each step. This approach can be particularly beneficial when working with poorly documented or complex APIs where the actual behavior may not be apparent from the documentation alone.

Using a debugger in this way allows developers to:

- Inspect the state of the application at various execution points.
- Examine the contents of variables and data structures.
- Step through code execution line-by-line or jump to specific points of interest.
- Verify assumptions about how certain functions or APIs behave with real input data.
- Explore and learn about the codebase in an interactive manner.

As for the sentiment against debuggers, there are some arguments that suggest relying solely on a debugger can hamper the development of other important programming skills, like being able to reason about code and predict its behavior without seeing it run. Proponents of this view might also argue that if a piece of code is well-designed and backed by a robust suite of automated tests, the need for a traditional debugger diminishes.

However, this doesn't mean debuggers aren't useful. They are invaluable tools, especially in the scenarios you've described. They provide a practical and often fast way to get feedback on what the code is doing at runtime. Moreover, for many developers, especially those working in complex, legacy, or poorly documented environments, debuggers can significantly aid understanding and expedite development.

Perhaps a more balanced view is that debuggers are an essential tool in a developer's toolbox, but they shouldn't be the only tool. Developers should use debuggers when they add value and are the most effective means of solving a problem but should also work to develop a suite of complementary skills and tools, including writing clean, testable code, and building comprehensive tests.







## Specification

### Logs Data
The Logs data are comming from decorator so, there are more detailed data, then jast outputs
We can work in **debugger mode** thta's why it's important to separate the usual logs and the **decorator driven logs in debugger mode**

### Logs format 
+ logs are designed to describe each inputs and outputs
+ In simple form each function can be saved in a csv file as text with colums as Variable
+ If we expect all data in one logs file, it should support multi columns format line by line, such Newline Delimited Objects Format - [NDOF](https://www.ndof.org/) 

### Stages in SDLC

The Logs provided by dialoget solution are working in debugger mode, where you can see more details, so you should care about securite on production stage and tuirn off it through pipeline or save in another machine, not production server with secure layer and protocol.

+ dev/test - printed data input and outputs and behaviours (remember to disable extensive logging as soon as you go into production)
+ production - printed behaviours without sensetive data  


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


## Keywords


+ decorator driven logs in debugger mode
+ Log-Driven Development (LDD)
+ Debugger-Driven Development (DDD)
+ Debugging Code With Decorators in Python 

## links

+ [How would you write a @debuggable decorator in python? - Stack Overflow](https://stackoverflow.com/questions/862807/how-would-you-write-a-debuggable-decorator-in-python#862899)
+ [Debugging Code With Decorators – Real Python](https://realpython.com/lessons/debugging-code-decorators/)
+ [Debugging decorators in Python - GeeksforGeeks](https://www.geeksforgeeks.org/debugging-decorators-in-python/)
+ [Primer on Python Decorators – Real Python](https://realpython.com/primer-on-python-decorators/)
+ [DDD (Debugger Driven Development) | PPT](https://www.slideshare.net/carlosgranados/ddd-debugger-driven-development)
+ [i6systems/stackdriver-debugger-php-extension: Investigate your code’s behavior in production](https://github.com/i6systems/stackdriver-debugger-php-extension)
+ [googleapis/google-cloud-php-debugger](https://github.com/googleapis/google-cloud-php-debugger)
+ [GoogleCloudPlatform/snapshot-debugger](https://github.com/GoogleCloudPlatform/snapshot-debugger)
+ [Log-Driven Development - DEV Community](https://dev.to/alexsergey/log-driven-development-3jmf)
+ 

 
## Contributors



## Contribution







