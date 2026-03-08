# UNDERSTANDING DEVOPS

- In traditional IT operations, the developers delivered new software versions periodically to the Quality Assurance (QA) team, who test the software and provide it to the operations team for deployment. This way of working involved ticket systems, and thus was not suitable for environments where new releases were needed all the time

- In Continuous Integration (CI) developer teams use automated systems to compile, test and produce deployable artifacts while developing sofware. Since different teams are involved this process can be lengthy, but transitioning from on-premise IT systems to cloud-based systems created a new way of working, facilitated by programmable APIs provided by these systems

- After the Devops phase of Continuous Integration, the artifacts needs to be present for use:
	- In Continuous Delivery the artifacts are delivered to the appropriate location, from where a person can move it into production
	- In Continuous Deployment the artifacts are delivered to the appropriate location, from where it is automatically moved into production
	- Both Continuous Delivery and Continuous Deployment are referred to as CD in CI/CD - it really depends on the environment which one we choose

- In DevOps the developer and operator practices are combined into a system that shortens the development life cycle. It is a state of mind, and the exact implementation depends on the specific DevOps team. So there are many ways that exist in which DevOps is realized

- Microservice is an application that consists of different components that are independently developed and maintained (and thus each has its own CI/CD pipeline). They are efficient, as components can be reused in different applications, and because the development team can focus on small, individual components, which reduces the development life cycle. Components are provided as container images in a containerized cloud environment

- Benefits of DevOps:
  - Better collaboration between developers and operators
  - More frequent releases and updates

# GITOPS

- GitOps provides tools that uses DevOps practices and applies them to infrastructure automation and containerized application deployment. GitOps applies version control on Infrastructure as Code (IaC) and Configuration as Code (CaC) while being stored in Git repositories. CI/CD tools are used to deploy that infrastructure as well as that code into a Kubernetes environment in a fully automated way. In GitOps, the Git version control systems is used to track and approve changes

- Benefits of GitOps:
  - All benefits of version control applied to all aspects of the environment (configuration and infrastructure) and application
	- Everything is code mananged across multiple git projects:
		- Infrastructure as Code - defining which resources to create
		- Configuration as Code - defining how to configure these resources
		- Application manifest files - defining which applications to run in which way
	- It's efficient and reliable as common process (code reviews and automated testing) are easily repeated, and specific solutions provided by different teams (development, infrastructure, etc) can be implemented in an automated way using GitOps operators
  
- Kubernetes is a perfect target for GitOps, as it uses declarative manifest files that can be managed in GitOps

- GitOps workflow:
  - The desired state of the managed system is stored in Git
  - Changes are applied to Git branches where they can be reviewed and approved
  - When changes are approved they will be merged in the main branch
  - An operator process (automated process running in Kubernetes) is used to change the system's current state to the new desired state. The Kubernetes operator detects changes, automatically applies them if you want to

[DevOps X GitOps](./images/image.png)

- Benefits of Kubernetes in GitOps:
	- Kubernetes is the solution to orchestrate containerized applications. It offers different resources to represent any stage of the current configuration:
	- Deployement strategies that integrate perfectly in pipelines that are defined in the GitOps environment
	- Declarative API allows application changes to be pushed to the environment easily
	- Operators can automate the process of updating application code that is ready to be updated

# DEVOPS ENVIRONMENTS AND STAGES

- Applications in DevOps and infrastructure configuration in GitOs are implemented through environments and stages
	- Environment - where the software is used before it is moved into production. Once the software is cleared in one environment, it is cleared to be used in the next environment, where each environment has its own CI/CD pipeline:
		- QA - Quality assurance - which is where it is ensured that the software runs on the specific hardware and other specific dependencies
		- E2E - End-to-End testing - which is about testing the workflow from beginning to end
		- Staging - All dependencies that exist in the production environment can be tested
		- Production - This is the final deployment in the production environment
	- To manage the software implementation in a specific environment stages are implemented in CI/CD pipelines. They manage the release process for your application that can be used in each of these environments
		- Code submission / review
		- Build
		- Testing (Unit tests)
		- Container Image build / image push - For containerized environments
		- 

![Environments and Stages](./images/image1.png)

- 