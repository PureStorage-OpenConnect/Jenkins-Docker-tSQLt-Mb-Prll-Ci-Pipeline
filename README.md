This repository contains a SQL Server data tools project and a Jenkinsfile written using the opinionated declarative syntax for a build pipeline that:

- Checks the project out from SCM
- Spins up a container to deploy the DacPac to **in parallel**, the container:
  - is named **[SQLLinux|branch name]**
  - has a unqiue external port so as to avoid port clashes
- Deploys the DacPac to the container
- Performs tSQLt unit tests **in parallel**
- Renders the tSQLt unit test results to Jenkins using the JUnit plugin
- Tears down the container
