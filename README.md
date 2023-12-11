# Log-Driven Development (LDD) - [ldd.coders.info](http://ldd.coders.info)


## LDD Patterns

**LDD** align closely with Test-Driven Development (TDD) and behaviour-driven development (BDD), but with a particular focus on understanding system behavior through logs, is working based on such main principles:

+ TDD - Test-Driven Development
+ BDD - Behaviour-Driven Development
+ Reverse Engineering
+ Modular design to create monorepo
+ Continouous improvement with CI/CD integration


### Benefits of Developing Code with Logs and Alerts

Development and test cycles are becoming quicker and more efficient, so organizations need to use log-driven development for stricter monitoring
Log-Driven Development method allows you to create an autonomous system that, starting from only the system logs, will be able to recreate it, step by step, using humans and machines
You can start with legacy code and just conenct the decorator to record behaviours
After you know how behaoviuuor the seoftware
You can develop new module and test the code based on before genrated logs with the same decorator and after time with refactored data - migrated to a new format
you can use 2 format of logs data through connect two different data logs through different decorator format

#### Responsibility
A developer who creates and releases a feature must be accountable himself or herself for its success. LDD places developers closer to the releases of their own features and keeps them aware of their code’s influence on system behavior and end users


### Log-Driven Development (LDD)
Log-Driven Development (LDD) is a software development approach where the design and construction of software are primarily informed and driven by the analysis of system logs. 

Logs are used as the fundamental source of truth for determining how a system should behave in both routine and exceptional circumstances. 

Developers use logs to abstract system requirements and functionality, write targeted tests, and then develop system features iteratively while respecting the guidance provided by the logs.
LDD as the natural evolution of TDD (test-driven development) in production, and it gives R&D teams the transparency that they need to have to enable code to ship to production more quickly while maintaining the necessary checks and balances.


## Definitions


### Logging 

Logging is the process of recording information about the operation of a program. This can include a variety of data, such as informational messages, warnings, errors, and debugging messages. The purpose of logging is to provide insights into the behavior of the application, facilitate debugging, and help with monitoring and troubleshooting. 
Logs are usually persistent, which means they are saved to files or databases for later review and analysis. 
They historically have different levels of severity, such as DEBUG, INFO, WARN, ERROR, and CRITICAL, which help categorize the log entries based on their importance or urgency.

Key aspects of logging include:

- **Auditing* Keeping a record of significant events, which could be important for security audits, compliance, or business analysis.
- **Diagnostic* Helping developers or system administrators understand the system's behavior, particularly useful when an error occurs or for post-mortem analysis of a failure.
- **Performance Monitoring* While not as focused on performance as profiling, certain logs can help to indicate slow operations or resource bottlenecks.
- **Event Recording* Logging all manner of events, from routine operations like user logins to rare occurrences like configuration errors.


### Debugging

Debugging is the systematic process of identifying, isolating, and fixing bugs or defects within a software application or system. A bug is typically an error or flaw in the software that causes it to produce incorrect or unexpected results, or to behave in unintended ways.

Key aspects of debugging include:

- **Problem Reproduction* Attempting to reproduce the reported issue under controlled conditions to understand the circumstances under which it occurs.

- **Hypothesis Formulation* Developing theories about the root cause of the bug based on an understanding of the code and its behavior.

- **Instrumentation* Adding logging statements or using debugging tools to collect more information about the software's behavior during execution.

- **Breakpoint Setting* Using a debugger to pause execution at specific points in the code in order to inspect the state of the application.

- **Step-by-Step Execution* Running the program one line or instruction at a time to observe how the state changes and where it deviates from expected behavior.

- **Variable Inspection* Examining the contents of variables and the state of the application at various points of execution to identify anomalies.

- **Fix Implementation* Applying code changes aimed at correcting the identified problem.

- **Testing and Verification* Running the application to confirm that the fix resolves the issue without introducing new bugs.

 
### Profiling
Profiling is the practice of measuring the space (memory) and time complexity of a program's operation. It is a form of dynamic program analysis that can be performed either during development (to optimize code) or after deployment (to diagnose performance issues). Profiling aims to identify parts of a software program that are consuming disproportionate amounts of system resources, such as CPU time, memory usage, disk I/O, or network bandwidth.

Key aspects of profiling include:

- **Performance Bottlenecks* Discovering which parts of the code are slowing down the program's execution or using too many resources.

- **Function Calls Analysis* Measuring the frequency and duration of function calls to determine which functions are called most often and which take the most time to execute.

- **Memory Allocation* Tracking the memory allocation and deallocation to find memory leaks or spots of inefficient memory use.

- **CPU Utilization* Analyzing how the program uses the CPU to identify heavy computation or concurrency issues that may be limiting performance.

- **Hotspots Identification* Identifying "hotspots" in the code—sections that are executed most frequently and become candidates for optimization.

- **Input/Output Operations* Measuring the I/O operations to optimize file handling and data transfer processes, especially in data-intensive applications.

Profiling tools typically provide reports that help developers focus their optimization efforts where they will have the greatest impact on performance. Some profiling tools also offer visual representations of the data, such as call graphs or heat maps.

Profiling is essential for:

- Improving the efficiency of an application by optimizing the use of system resources.
- Ensuring that an application can scale effectively to handle increased loads.
- Providing a better user experience by making software more responsive.

[Jack Whitham - Profiling versus tracing](https://www.jwhitham.org/2016/02/profiling-versus-tracing.html)


### Tracing

Tracing is the practice of recording a chronological log of events or operations within a software application or system. It is a form of dynamic analysis that captures detailed information about a program's execution path, data flow, and interactions with system components or external systems. Tracing helps developers and system administrators understand the behavior of complex systems in real-time or after the fact.

Key aspects of tracing include:

- **Event Logging* Collecting detailed records of discrete events that occur as the software runs. These records typically include timestamps, event types, and context-specific data.

- **Execution Flow* Monitoring the flow of execution through the application, often capturing function or method calls, returns, and exceptions.

- **Data Flow Analysis* Observing the movement and transformation of data within the application, which can be useful for diagnosing issues related to data processing or corruption.

- **Systems Interaction* Recording how the application interacts with other systems, services, or components, which can be crucial for distributed systems or service-oriented architectures.

- **Distributed Tracing* When dealing with microservices or distributed architectures, tracing can provide insight into how requests propagate through various services, helping to pinpoint latency issues or failures in the system.

- **Performance Monitoring* Although tracing is not primarily focused on performance analysis, it can highlight where delays or bottlenecks occur within the execution chain.

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




## Software development practices

The Log-Driven Development (LDD) method you are describing appears to be a combination of several advanced software development practices. It uses logs as a primary source of truth in recreating and understanding system behavior, as well as for informing the development of new features and the migration of legacy systems. Here's a breakdown of how such a method could be structured:

#### Behavior Recording with Decorators
   - Legacy systems or existing components are instrumented with decorators that generate detailed logs of behavior. These decorators capture function calls, arguments, return values, and possibly exceptions or error messages.
   - The recorded logs serve as an empirical baseline representing the current behavior of the system.

#### Behavior Analysis
   - The system logs are then analyzed by developers and potentially processed by automated tools to understand the behavior and interactions of various parts of the system.
   - A collection of typical and atypical use cases can be derived from this log data, capturing both normal operations and edge cases.

#### Test Generation
   - Based on the log data, automated test cases can be generated to capture the expected behavior of the system. Alternatively, developers can manually write tests that reflect the observed behavior.
   - These tests become the specifications for ensuring that the system's behavior remains consistent, especially during refactoring or the development of new features.

#### Module Development and Testing
   - New modules can be developed in isolation and then integrated with the legacy system. The integration can be verified using the previously generated tests to ensure compatibility and correctness.
   - The decorators are also applied to the new modules to continuously update the log data and refine the system's behavioral profile.

#### Data Migration and Refactoring
   - When migrating data or refactoring code, the same logging decorators are used to ensure that the system's behavior remains consistent with the behavior captured in the logs.
   - If log formats change or newer versions of logs are required, different decorators can be applied that output the logs in the new desired format, enabling parallel recording during a transition period.

#### Behavior Evolution
   - Over time, the accumulation of log data enables developers to refine their understanding of the system and evolve the codebase while monitoring the system to ensure that changes do not deviate from expected behavior.
   - The collection of logs can also support root cause analysis for new issues and help inform the design of future system enhancements.

#### Continuous Verification
   - The system logs, along with the tests derived from them, facilitate a continuous verification process. As the system evolves or is refactored, developers can routinely check that the behavior continues to match the historical logs.

This approach relies heavily on the detailed logging of system behavior and the belief that logs represent a comprehensive and accurate picture of the system in action. Deviations from the logged behavior during new development, refactoring, or migration are indicative of potential issues that need addressing.

In practice, Log-Driven Development as outlined here embraces principles from behavior-driven development (BDD), test-driven development (TDD), and continuous integration and deployment (CI/CD). It represents an ambitious attempt to blend automated logging with human oversight to iteratively build and maintain complex software systems.






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


## Intro EN

One day in the software development department of Softreck, Irena, an experienced programmer, shared a new idea with the team. She wanted to talk about a unique approach that could transform the way we work with code - especially legacy code, the confusing guts of applications that every developer has to deal with sooner or later.

"How about a revolution in debugging and documentation?" - Irena started over her morning coffee.
"Imagine a method that allows you to 'talk' to the code like a good friend who explains exactly what he is doing step by step."

Intrigued, developers began to listen more carefully.

Irena continued: "Let's call it Log-Driven Development or LDD. The system is based on decorators that wrap our functions, creating descriptive logs in the form of sentences - clear to each of us and at the same time fully understandable to machines. Each function will be documented over time real, not only through static comments, but by actively logging her behavior."

The team was full of doubts. “Won't this make us overloaded with data?” - asked Marek, a junior in the team.

"No," Irena replied. "The key is intelligent logging. Instead of logs full of unnecessary data, our decorators will save only what is crucial: intentions and performed actions, all supplemented with data in JSON format for easy deserialization."

"Interesting..." Ewa, the second programmer, whispered, imagining how much time such a system could save. “We can use this data to automatically generate tests, right?”

"Exactly!" - Irena confirmed.
"By observing our applications in action, we can generate sets of inputs and expected results from the logs. Tests suddenly become more effective because they reflect real-world scenarios."

The team began to understand the potential of LDD. It wasn't just about solving current problems, but about creating a foundation for future developments and refactorings. An autonomous system that, learning based on generated logs, will become more efficient every day and independently offer suggestions for improvements.

"The feeling that working on code is like talking to an application that understands its behavior and helps to improve it - this is a real paradigm shift," noted Rafał, the team's tech leader. "Irena may have just found a way to build a bridge between the machine and the programmer, opening the way to a modular and autonomous future of software."


A world where applications and developers **work in harmony with machines** is one step closer.


## PL

Pewnego dnia w dziale rozwoju oprogramowania firmy Softreck, Irena, doświadczona programistka, podzieliła się z zespołem nowym pomysłem. Chciała opowiedzieć o pewnym wyjątkowym podejściu, które mogłoby przekształcić sposób pracy z kodem — zwłaszcza legacy code, zagmatwanych bebechów aplikacji, które prędzej czy później każdy deweloper musi zmierzyć się.

"Co powiecie na rewolucję w debugowaniu i dokumentacji?" — zaczęła Irena przy porannej kawie. 
"Wyobraźcie sobie metodę, która pozwala 'rozmawiać' z kodem jak z dobrym znajomym, który dokładnie wyjaśnia, co robi krok po kroku."

Zaintrygowani programiści zaczęli słuchać uważniej.

Irena kontynuowała: "Nazwijmy to Log-Driven Development lub LDD. System opiera się na dekoratorach, które otulają nasze funkcje, tworząc logi opisowe w formie zdań — klarowne dla każdego z nas i jednocześnie w pełni zrozumiałe dla maszyn. Każda funkcja będzie udokumentowana w czasie rzeczywistym, nie tylko poprzez statyczne komentarze, ale przez aktywne logowanie jej zachowań."

Zespół był pełen wątpliwości. "Czy to nie sprawi, że będziemy przeładowani danymi?" — zapytał Marek, junior w zespole.

"Nie," — odpowiedziała Irena. "Kluczem jest inteligentne logowanie. Zamiast logów pełnych zbędnych danych, nasze dekoratory będą zapisywać tylko to, co kluczowe: intencje i wykonane akcje, a wszystko to uzupełnione o dane w formacie JSON dla łatwej deserializacji."

"Interesujące..." — wyszeptała Ewa, druga z programistek, wyobrażając sobie, jak wiele czasu mógłby zaoszczędzić taki system. "Możemy użyć tych danych do automatycznego generowania testów, prawda?"

"Dokładnie!" — potwierdziła Irena. 
"Obserwując nasze aplikacje w działaniu, możemy generować z logów zestawy danych wejściowych i oczekiwanych wyników. Testy suddenly stają się efektywniejsze, ponieważ są odzwierciedleniem rzeczywistych scenariuszy."

Zespół zaczął rozumieć potencjał LDD. Nie chodziło tylko o rozwiązywanie bieżących problemów, ale o tworzenie fundamentu dla przyszłych rozwojów i refaktoryzacji. Autonomiczny system, który ucząc się na podstawie generowanych logów, będzie z każdym dniem wydajniejszy i samodzielnie oferował sugestie usprawnień.

"Poczucie, że praca na kodzie jest jak rozmowa z aplikacją, która rozumie swoje zachowania i pomaga w ich udoskonaleniu — to prawdziwa zmiana paradygmatu," — zauważył Rafał, tech leader zespołu. "Irena mogła właśnie znaleźć sposób na zbudowanie mostu między maszyną a programistą, otwierając drogę do modułowej i autonomicznej przyszłości oprogramowania."


Świat, w którym aplikacje i programiści **współpracują w harmonii z maszynami**, był już o krok bliżej.


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
+ [Test-driven development - Wikipedia](https://en.wikipedia.org/wiki/Test-driven_development)
+ [coders-info/reverse-design: reverse-design.coders.info - Reverse design is focusing on logs and step by steps to unit test and code](https://github.com/coders-info/reverse-design)
+ [dialoget/python: python.dialoget.com is a test framework for multilanguage source code, based on decorators](https://github.com/dialoget/python)
+ [An Introduction to Log-Driven Development | Logz.io](https://logz.io/blog/log-driven-development/)
+ 

 
## Contributors



## Contribution







