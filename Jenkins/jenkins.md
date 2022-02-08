enkins follows master and slave architecture

![Jnekins architecture explained](file:///home/knoldus/.config/joplin-desktop/resources/d841bfdaf080487a89343b17550356eb.png)

Following are the key components in Jenkins

Jenkins Master Node

Jenkins Agent Nodes/Clouds

Jenkins Web Interface

### Jenkins Master (Server)

Jenkins’s server or master node holds all key configurations. Jenkins master server is like a control server that orchestrates all the workflow defined in the pipelines.

For example, scheduling a job, monitoring the jobs, etc.

### Jenkins Jobs

A job is a collection of steps that you can use to build your source code, test your code, run a shell script, run an Ansible role in a remote host or execute a terraform play, etc. We normally call it a Jenkins pipeline.

![](file:///home/knoldus/.config/joplin-desktop/resources/972d7807b0b44022a136df2d43353cfe.png)

Plugins are community-developed modules that you can install on your Jenkins server. It helps you with more functionalities that are not natively available in Jenkins.

For example, if you want to upload a file to s3 bucket from Jenkins, you can install an AWS Jenkins plugin and use the abstracted plugin functionalities to upload the file rather than writing your own logic in AWS CLI. The plugin takes care of error and exception handling.

### Jenkins Credentials

When you set up Jenkins pipelines, there are scenarios where it needs to connect to a cloud account, a server, a database, or an API endpoint using secrets.

In Jenkins, you can save different types of secrets as a credential.

1.  Secret text
2.  Username & password
3.  SSH keys

All credentials are encrypted (AES) by Jenkins. The secrets are stored in `$JENKINS_HOME/secrets/` directory. It is very important to secure this directory and exclude it from Jenkins backups.

Jenkins Global Security

Jenkins has the following type of primary authentication methods.

Jenkins’s own user database:- Set of users maintained by Jenkins’s own database. When we say database, its all flat config files (XML files).

LDAP Integration:- Jenkins authentication using corporate LDAP configuration.

SAML Single Sign On(SSO): Support single signon using providers like Okta, AzureAD, Auth0 etc..

Jenkins Nodes/Clouds

You can configure multiple agent nodes (Linux/Windows) or clouds ([docker](https://devopscube.com/what-is-docker/), kubernetes) for executing Jenkins jobs. We will learn more about it in the agent section.

## Jenkins Agent

Jenkins agents are the worker nodes that actually execute all the steps mentioned in a Job. When you create a Jenkins job, you have to assign an agent to it. Every agent has a label as a unique identifier.

[![image 25](file:///home/knoldus/.config/joplin-desktop/resources/179887609bba4a009ad5f9b039c03ca2.png)](https://devopscube.com/wp-content/uploads/2021/08/image-25.png)

When you trigger a Jenkins job from the master, the actual execution happens on the agent node that is configured in the job.

You can have any number of Jenkins agents attached to a master with a combination of Windows, Linux servers, and even containers as build agents.

## Jenkins Master-agent Connectivity

You can connect a Jenkins master and agent in two ways

1.  **Using the SSH method:** Uses the ssh protocol to connect to the agent. The connection gets initiated from the Jenkins master. Ther should be connectivity over port 22 between master and agent.
    
2.  **Using the JNLP method:** Uses java JNLP protocol ([Java Network Launch Protoco](https://docs.oracle.com/javase/tutorial/deployment/deploymentInDepth/jnlp.html)l). In this method, a java agent gets initiated from the agent with Jenkins master details. For this, the master nodes firewall should allow connectivity on specified JNLP port. Typically the port assigned will be 50000. This value is configurable.
    
3.  **Agent Nodes:** These are servers (Windows/Linux) that will be [configured as static agents](https://devopscube.com/setup-agents-on-jenkins-2/). These agents will be up and running all the time and stay connected to the Jenkins server. Organizations use custom scripts to shut down and restart the agents when is not used. Typically during nights & weekends.
    
4.  **Agent Clouds:** Jenkins Cloud agent is a concept of having [dynamic agents](https://devopscube.com/docker-containers-as-build-agents-jenkins/). Means, whenever you trigger a job, a agent gets deployed as a VM/container on demand and gets deleted once the job is completed. This method saves money in terms of infra cost when you have a huge Jenkins ecosystem and continuous builds.
    

Build Triggers:

1. on-demad run

2.other job finished

3.Cron schedule

4. scm check

-------------------------------------------------------

Freestyle Project:

The purpose of the freestyle project is to implement, develop, or run simple jobs like allowing you to specify the version control system from which you required to extract code and build it and call tests if available. Freestyle projects are meant to orchestrate simple jobs for a project.

Pipeline Project:

Pipeline Project is a new type of Jenkins project that is suitable either when you have to set up a continuous delivery pipeline or to define the deployment pipeline as code. The pipeline project is applicable to build pipelines for complex activities that are not suitable for freestyle project.