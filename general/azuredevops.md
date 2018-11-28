# Instruction for Build - Release Umbraco Site

## Setup

* The code repo should be set up within the project

## Azure Subscription

* A new service connection should be set up to allow a release to deploy to the relevant Azure service (ie app service)
* This is done in Project settings > Pipelines > Service connections

# Builds

* A build needs to be set up, this will build the solution from your code repo
* The build for the HPS project involved the following...
  * NuGet restore, default options were used
  * MSBuild task
    * project - **/*.sln wildcard was used to build using the sln file
    * configuration - release
    * MSBuild Arguments - /p:DeployOnBuild=true /p:WebPublishMethod=Package /p:PackageAsSingleFile=true /p:SkipInvalidConfigurations=true /p:PackageLocation="$(build.artifactstagingdirectory)\\"
      * this is important as it create a publish package that will be used by the release pipline to deploy the application to azure
  * Publish Build Artifact (not sure if required, the build arguments may do the same thing)
    * this is need to place the package created in the previous step into the correct location
