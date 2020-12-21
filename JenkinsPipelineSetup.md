## Jenkins PipeLine Setup Steps:
### Install below Plugins in Jenkins:
    o	Maven Integration Plugin
    o	Maven Invoker Plugin
    o	Nexus Artifact Uploader
    o	SonarQube Scanner for Jenkins
    o	SSH Agent Plugin
    o	SSH Credentials Plugin
    o	CloudBees Docker Build and Publish plugin
### Integrate Maven and Java in Jenkins:
 Login to Jenkins->Dashboard->ManageJenkins->GlobalToolConfiguration->AddJDK.
 <image src="images/JenkinsJDKPath.jpg"/>
 
 Login to Jenkins->Dashboard->ManageJenkins->GlobalToolConfiguration->AddMaven.
 <image src="images/JenkinsMavenPath.jpg"/>
 
 Provide Credentials for git,dockerhub,sonar,nexus, in Credential Store at Jenkins->Dashboard->ManageJenkins->ManageCredentials.
 <image src="images/GlobalCredentials.jpg"/>
 
 Create Docker File and Upload into GitHub:
<image src="images/dockerFile.jpg"/>

 Create Manifesto file for K8s and upload into GitHub:
<image src="images/K8mfFile.jpg"/>

### Login to Nexus and Configure the Repository:

Login to Nexus->ServerAdministartion and Configuration ->Repository->+Create Repository->Maven2(Hosted)

<image src="images/NexusArtifactory.jpg"/>

## Configure pipeline in Jenkins:

Login to Jenkins and Create Pipeline Project and add the pipeline Script and Build the Script.

<image src="images/pipelineResult.jpg"/>

 
 
