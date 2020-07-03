# Check-list for easy-to-maintain quality software

This is a list of things to keep in mind during a software project. There are lots of other stuff too that will help you develop the quality into the system. Many times you don’t have to do everything mentioned here, but this list should help you to make a conscious decision instead of just forgetting stuff. 

## Use it in your project
Fork this repository, develop good quality software and hand this over to the team taking over the maintenance and see them appreciating.

## Why

For the project team this list provides a chance to learn about the life cycle of the software. It also reduces the time you need to help the maintenance team to fix stuff.  
For us at Orangit it reduces the risks that something unexpected will happen during taking over the software.  
For the client it shows that we know how to build robust systems in an agile way.

## How

In general there are few things to keep in mind during development project.
1. How long it does for a new developer to have a working development environment set up?
2. How long it on average take for a developer to understand the cause for the failure in production?
3. How long it on average take for a developer to restore to a working solution?
4. How long it on average take for a developer to develop a fix to the bug?
5. How long it on average take for a developer to deploy any change to production?

## What

### Documentation
Good documentation is important for many reasons. It reduces the amount of questions the original  developer needs to answer when a new one joins in. It reduces time needed for every developer to return back on developing. It reduces the risk of mistakes during deployment. It is a hygiene thing; if it is not ok, you will notice it at some point.
- [ ] Template is being used?
- [ ] Template is updated regularly, e.g. once every two weeks?
- [ ] All known issues, bugs or other things left undone are listed in the documentation?
- [ ] All documentation is available in VCS (or some other place where maintenance team has access)?

### Testing
Good tests make it safer to further develop the system. It can also work as a documentation; what the software can and can’t do. Testing the software on multiple levels can show errors in the (architectural) design.
- [ ] The software has unit tests?
- [ ] The software has integration tests?
- [ ] The software has acceptance tests?
- [ ] The software has performance tests?

### Automation
To err is human. To reduce the possibility of errors in integration or deployment we encourage to automate those parts that can be automated. And then document practices if needed.
- [ ] Continuous integration is possible?
- [ ] Continuous deployment is possible?
- [ ] Continuous integration and deployment practices are documented?

### Code quality
>Clean code is simple and direct. Clean code reads like well-written prose. Clean code never obscures the designer's intent but rather is full of crisp abstractions and straightforward lines of control.  

Tools will only get you so far, but they will point out some of the style errors preventing your code being clean. 
- [ ] Some kind of static analysis (e.g. SonarQube) is being used?
- [ ] Linter is being used?

### Environments
Well-documented environments make it safer to make changes to the working software. Setting them up should be easy. Also, operating with them should be a known set of things. 
- [ ] There is a setup for local development?
- [ ] There is a test environment?
- [ ] There is a production environment?
- [ ] All environments (dev, test, prod) are documented?
- [ ] The process for setting up new environment is documented?
- [ ] New environment can be set up with scripts?
- [ ] The management and operating of all environments are documented?
- [ ] Containers (e.g. Docker) or such are being used?
- [ ] It is easy to rollback changes to a previous state?
  
### Error handling
Software errors happen. No matter if the root cause is user error or bug in the code, the processing of errors should follow the same logic throughout the system.
- [ ] The software handles errors systematically (input validation, exceptions, etc)?

### Logging
Well planned logging makes it easier to find and fix errors in production. They might also be relevant for analytics or mandatory for audit trails. 
- [ ] Log level can be changed without a new deploy (via external configuration)?
- [ ] Log levels follow a common agreement?
- [ ] Logs provide enough context (people reading the logs can figure out what happened without having the surrounding code at hand)?
- [ ] Logs can be handled by machine for alert and monitoring purposes?
- [ ] A proper log framework is being used (avoid console or stout)?
- [ ] Error logs have an error ID?
- [ ] Logs can be used for auditing or statistics?

### Monitoring
It is vital to know that the software operates correctly. Testing that the service responses is trivial. But if the system relies on other services like database, authentication or such, being able to check that everything is working normally is a must.
- [ ] There is a health-api endpoint to check that all background systems are working?
- [ ] Server side errors can be easily detected with New Relic (or such)?
- [ ] Client side errors can be easily detected with Sentry (or such)?
- [ ] Errors in used 3rd party services can be easily detected with New Relic (or such)?

### Security
Software owners and users want that they are safe. Let’s not make the evildoing too easy for the hackers.
- [ ] The software does not expose too much information about itself (e.g. https://observatory.mozilla.org/)?
- [ ] All passwords and such secrets are stored in a password management system (e.g. LastPass) instead of VCS?

### Dependencies
We want to make software that lasts. Keeping good care of all the dependencies is one thing that makes further development easy.
- [ ] Dependencies are being updated during development process?
- [ ] Actively developed and maintained dependencies are preferred over outdated ones?
- [ ] Dependencies are updated automatically (e.g. with Renovate)?

### Data
Most software use data. Many errors are related to data - either the data is wrong kind or there’s too much of it. Data is also often one of the most valuable assets of the software. 
- [ ] Plenty of data can be generated with scripts for (performance) testing purposes?
- [ ] Test data is faked and masked following GDPR guidelines?
- [ ] It is easy to roll back data?

## Contributing?
If you have recognised some other thing that is relevant and needs to be on this list, please contribute by creating a pull request or contacting us by email  `github@orangit.fi`.
