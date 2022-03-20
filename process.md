# Exactly Labs Development Process

Exactly Labs manages projects differently depending on their stage. Our process also includes a scope beyond just the development of software directly. We involve ourselves in the following different areas:

* Requirement discovery
* Product Design
* Validation of requirements and design
* Implementation
* Testing and code quality
* Operations and End User Support

At different phases in a project's life, each of the above may take different levels of focus. Earlier on, we may be primarily focused on requirement discovery and validation. This may mean a much lighter weight design, implementation, and operation approach is taken. As time goes on and it becomes clear of the value of the various functionality added, a much more robust set of processes around software implementation, testing, and operations will be used.

## Early Life

Early in a project, we focus on the identification of specific end-user needs which are well aligned with goals of the project's owners / funders. In this phase, we will be primarily focused on the discovery of possible requirements and the validation of the need for these requirements. We use design and software development as tools to these ends in these phases. Speed of implementation is optimized for over correctness -- the primary goal is to learn.

In this phase, most structure used will be around requirements discovery. Each week, we'd track the following types of metrics:

* What user groups are we currently focused on
* How do we "access" these user groups for gathering feedback quickly
* What hypothesis are we currently trying to validate
* Who are key partners in the current project who will more likely lead to a successful outcome
* What are the key metrics for us to track and optimize for in future phases of the project
* How many users have we been able to schedule for and complete interviews with
* What are key learnings from the current "batch" of individuals interviewed

Note the above goals are primarily _not_ focused on the need for software, however, software may significantly contribute to our ability to learn with key partners and early adopters. Early one, software and design may be completed by a very small team of individuals who build new functionality reactively given direct feedback. Techniques such as scrum, code reviews, sprint/cycle planning, release management may be adopted but also may be deferred until we feel strongly which we've identified a fit between market needs and a potential software offering.

## Product-Market Needs Validated

Once we've established the need for specific functionality, we'll introduce much more structure and a stable cadence to the area of functionality. The following are an inventory of practices and techniques which are used:

* Established, recurring two-week cycles of software development composed of:
  * **Cycle Planning**: Locks-in a list of new features and bug fixes to be built in the next two-week cycle. This is also when releases will be discussed and upcoming new releases are added to the calendar. If design work or other early work is needed before software development, it will be included in an earlier cycle ahead of the cycle in which development occurs. We use a "Fibonacci" numbering to describe the level of effort for a given task. A "1" is a task which is less than 30 minutes, "2" is less than 1-2 hours, a "3" is 2-4 hours, "5" is 4-8 hours, and "8" may be more than a day -- typically an 8 is broken into many tasks as we intend every task to be less than a day. In each planning session, we request contributors to state whether they have 90% confidence in the current deadlines set for their tasks. If the answer is not yes, the tasks are adjusted until the answer to this question is yes.
  * **Cycle Check-in**: After the first week, the list of current tasks is reviewed for the current status. Releases are discussed to ensure we're still on track for hitting deadlines related to them. We also again ask if each individual is 90% confident in their tasks' completion.
  * **Cycle Retrospective**: The end of each cycle, the team reviews how things went in the last cycle. Each participant shares a list of what went well, what didn't go well, and what improvements may lead to improvements in our next cycle. After the lists are created, they are shared and discussed. Each cycle retrospective results in a list of specific tasks or changes to be included in the next Cycle Planning.
* Release scheduling as follows which happens during Cycle Planning:
  * The creation of a new release and the creation of placeholder tasks which describe the high-level objectives for the release.
  * Typically releases are timed to be at the end of cycles. Sometimes releases contain more functionality than one cycle but will never not be broken into 2 cycle segments. The ensures rapid forward progress even with the introduction of heavier process. This is possible given web-based and mobile-based software's ease of publication. Given no physical mediums or publisher requirements, we attempt to maintain this to ensure we're able to continue to learn from new features as fast as possible. When not possible due to a physical constraint, we attempt to build our software such that upgrades to that physical device or constraint and still be done on a regular basis.
  * Each project and release will have different risks associated with it. Given the short release cycle, testing typically also doesn't need a huge investment. As a result, we reserve approximately 3-4 days of time before a release to "Lock" the contribution of new features for that release. In this time, internal automated and manual testing takes place. Any issues discovered are fixed in this timeframe. In the last few days issues are triaged based on their severity and proximity to the release date. If an issue will cause previously released features to no longer function, or the issue prevents usage of a new features, this would take priority or issues which do not prevent usage or prevent the business goal of that release. If needed, issues of lower priority may be scheduled for a future release
* Software quality control
  * We use Git for all source code tracking and development. Our preferred platform for hosting this is Github.
  * Feature and issue tracking is used to enable our workflows. Every issue / feature is assigned out to an owner. Inbound feature requests or bugs reported are left unassigned but marked to be triaged. Triage happens with every cycle planning or sooner if a current bug is significant enough to require more timely review and response.
  * Github Pull Requests are used for all new contributions to code bases. At least one person will always review a new contribution. The contribution description also describes which issue is solved within the pull request. Feedback given within a pull request is then either fixed or a discussed before it the feedback is considered "resolved". If automated testing is available, pull requests are also blocked until all testing is completed successfully. As needed, pull request templates may be used when projects begin to have specific requirements for all code going into a codebase (such as security requirements).
  * Depending on the coding language used, "linting" rules are used to ensure consistent code syntax and formatting are used.
* Continuous Deployment / Continuous Deployment / Delivery (CI/CD)
  * Depending on the project style and the number of contributions, CI/CD is introduced to ensure the project meets deployment requirements in an automated way. Additionally, deployment to staging or test environments will happen in a fully-automated way. Given the nature and small scale of projects we work on, we rarely or never use CD to a production environment. If a project hits a level of maturity where all testing and monitoring is completed in an automated way, CD to production may be used as well.
* Testing and Automation
  * Testing automation investments happen in a way that is different per project based on the language / technologies used as well as based on the requirements of the project. Similarly, the frameworks used depend on the project requirements and language used.
  * We use techniques such as Test Driven Development -- especially once written in scripted languages such as Ruby or Python or if the program has easily compartmentalizable components.
  * Integration tests will be used in some projects where workflows are complex and hard to test per-release otherwise.
  * As is needed, manual testing happens before each release. A list of specific manual "integration" tests are created as time goes on to describe ways to hit the majority of core functionality.
* Monitoring and Alerting
  * We use monitoring and alerting tools where operating software as projects become more mature. The types of tools used are specific to the project's requirements.
  * Exception tracking is involved in most projects at a relatively early phase using tools such as Sentry.
  * Metrics tracking using tools such as Prometheous and Graphana are introduced when usage volume and performance begins to matter more.
  * Logging using tools such as ELK (Elastic Search, Logstash, Kibana) are introduced if the service begins to be scaled beyond a single process. We generally recommend this be the case if uptime for the service is critical or if the volume of usage begins to reach an amount that requires multiple backend services, but otherwise would recommend simplifying deployments to not need this.
