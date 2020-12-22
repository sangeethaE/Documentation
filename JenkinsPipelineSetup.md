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
 
 For Gradle follow the below step
 Login to Jenkins->Dashboard->ManageJenkins->GlobalToolConfiguration->AddGradle.
 <image src="images/JenkinsGradleIntegration.jpg"/>
 
 Provide Credentials for git,dockerhub,sonar,nexus, in Credential Store at Jenkins->Dashboard->ManageJenkins->ManageCredentials.
 
 <image src="images/GlobalCredentials.jpg"/>
 
 Create Docker File and Upload into GitHub:
<image src="images/dockerFile.jpg"/>

 Create Manifesto file for K8s and upload into GitHub:
<image src="images/K8mfFile.jpg"/>

### Jenkins-Nexus Integration
For Nexus integration with Jenkins follow the below step:

Dashboard->Manage Jenkins->Configuration->Nexus->Add Artifactory Server
<image src="images/JenkinsNexus.jpg"/>

### Jenkins-Jfrog Integration

For Jfrog Integration with Jenkins follow the below step:

Dashboard->Manage Jenkins->Configuration->Jfrog->Add Artifactory Server
<image src="images/JenkinsJfrog.jpg"/>

## Configure pipeline in Jenkins :

Login to Jenkins and Create Pipeline Project and add the pipeline Script and Build the Script.

 Maven PipeLine :

<image src="images/pipelineResult.jpg"/>

 Gradle PipeLine : 
 
<image src="images/JenkinsGradlePipeline.jpg"/>
