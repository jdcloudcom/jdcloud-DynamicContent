# Create CodePipeline


JD Cloud provide users with two methods for creating CodePipeline, including:

* [Quick Creation](../Getting-Started/Quick-Creation.md)

* [Customized Creation](../Getting-Started/Create-Customized-Instance.md)

Of which, when using quick creation, CodePipeline will create three stages with the stage names of source, build and deploy which you can add more operations.

## Operation Steps
1. Create CodePipeline
If you need to conduct quick creation based on recommended templates, you select **Quickly Create** in the creation method. You can also create CodePipeline according to your business situation with the method of customized creation.

	CodePipeline name: you need set name for created CodePipeline, which the name cannot be null, only supports Chinese characters, numbers, capital and lower-case letters, English underline "_" and line-through "-", with at most 32 characters.

2. Create source stage
When conducting quick creation, the name of the stage is source by default, which supports users to modify the stage name. Each phase contains one or more actions (up to 5 actions). Stages are executed in series, and operations in each stage are executed in parallel. If any action in one phase fails, it is considered that the phase fails to execute.


	The operation elements of source code in the template are as follows:

	- Operation Type: Source Code
	- Operation name: Code source-default-1
	- Code Source: JD Cloud-CodeCommit, GitHub
	- Codebase: Select repo address
	- Branch: Compilation Branches
	- Webhook Trigger: Select **Yes** to automatically trigger the CodePipeline when changes occur in the source code

	

3. Create Compilation Stage
When conducting quick creation, the name of the stage is built by default, which supports users to modify the stage name.


     The construction elements in the template are as follows:     
	
     - Operation Type: Construction
     - Operation name: Build-default-1. The operation name is generated by default according to the operation type. The operation name in one CodePipeline shall be unique.
     - Operation Provider: CodeBuild
     - Code source: Select the source code added at the previous stage.
     - Task: Select the CodeBuild task corresponding to 「code source」.
     - Manual Confirmation: If manual confirmation is selected, the action will be executed after the user clicks **Confirm**. It is automatically executed by default.

4. Create Deployment Stage
When conducting quick creation, the name of the stage is deploy by default, which supports users to modify the stage name.


    The page elements are as below when the operation provider selects JCS for Kubernetes:
	
	
    - Operation Type: Deployment
    - Operation name: Deployment-default-1
    - Operation Provider: JCS for Kubernetes
    - Cluster: The corresponding project in JCS for Kubernetes. Select the JCS for Kubernetes that the user has created in the JD Cloud Console. Or go to the Console to create the JCS for Kubernetes and return to this task
    - Upload yaml: upload cluster deployment configuration files. Supports page to edit the deployment files.
    - Image sources: List the images used in the deployment file. The user can replace it with the image generated in the construction, click **Replace**, and select the construction action. Make sure that the construction type of the compilation task (construction action) is image.
    - Manual Confirmation: If manual confirmation is selected, the action will be executed after the user clicks **Confirm**. It is automatically executed by default.

      
    The page elements are as below when the operation provider selects CodeDeploy:
	
    - Operation type: deployment
    - Operation name: Deployment-default-2
    - Operation provider: CodeDeploy
    - Deployment source: It currently only supports the CodeBuild tasks with the construction type of application package
    - Deployment application: Select CodeDeploy-application
    - Deployment group: Select CodeDeploy-deployment group
    - Deployment command: Enter the deployment command or use the jdcloud-codedeploy.yml file under the code root directory
    - Manual confirmation: If manual confirmation is selected, the action will be executed after the user clicks **Confirm**. It is automatically executed by default.
	
  Save to complete creation according to the templates.

At the stage where the mouse is hovered for navigation, you can click the plus sign to add more stages. You can also create CodePipeline meeting your own business logic by means of customized creation.
