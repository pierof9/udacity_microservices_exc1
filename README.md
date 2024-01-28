# Building and running containers with AWS CodeBuild and ECR (Elastic Container Registry)
## Steps:
1. You need to create a Project in AWS CodeBuild. E.g: sample-udacity-test-project
2. Choose the Origin --> GitHub with OAuth
3. Provision you Environment: O.S: Amazon Linux, Runtime: Standard, Img: One standard
4. It will automatically provision a role. E.g: codebuild-sample-udacity-test-project-service-role
5. Create the IAM policy to allow the previous created role to connect to the ECR
    Look for the codebuild-sample-udacity-test-project-service-role and add a new policy
    Add a new policy. The json format is in the "FullECR_Access.json" file.
5. Create an ECR for the project
    Follow the standard tool to create the ECR
    Flag as private
    Enable the control on override images
6. Create a buildspec.yml file that builds and pushes a Docker image to ECR. Store it in the root of your GitHub repository.
7. The project requires 4 variables:
- $AWS_DEFAULT_REGION
- $AWS_ACCOUNT_ID
- $IMAGE_REPO_NAME
- $IMAGE_TAG
On the project, modify button with "Change Environment". Scroll down to add the four variables.
8. Run the compilation
