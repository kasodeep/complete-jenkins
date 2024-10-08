### Jenkins:

- It is an open source automation server.
- Automate various parts of software development.
- `Building`, `Testing`, `Deploy`

#### Features:

1. Continous Integration & Continous Delivery
2. Easy Installation
3. Easy Configuration
4. Plugins
5. Extensible
6. Distributed

### CI/CD:

- It is a method of delivering apps to customers by introducing automation into the stages of app development.

#### Integration

      Build, Test, Merge

#### Delivery

      Automatically release to repository.

#### Deployment

      Automatically deploy to production.

### Install & Setup:

1. Install the Jenkins server from the website.
2. It is accessible on port `http://localhost:8080/`
3. Create a default admin user and install the basic plugins.

### First Job:

1. A simple job to print the outputs of echo into a file.
2. The file gets created in the .jenkins/workspace folder.
3. We can Schedule the jobs & also add the parameters.

### Git Demo:

1. We can use git source to handle the job.
2. Using Poll SCM, it will fetch the changes by checking every time frame and will trigger the job.
3. It will not trigger unless the changes are present.

### For Sending Email:

1. Go to system config and add the gmail's smtp server.
2. Then, add app password from google account and enable it.

### Post Build Action:

1. We can use post build action to send email when the build is completed.
2. We need to specify the email address where we want to send the email.

### Pipeline Docs:

1. `Scripted` and `Declarative` are the two ways to write Jenkins pipeline.
2. Two major ways are `Classic UI` and `SCM Jenkinsfile`.
3. `agent` instructs Jenkins to allocate an `executor` and `workspace` for the entire Pipeline.
4. We can also use the environment variables to provide the `credentials`.
5. We can use parallelism to parallelize the execution of the pipeline.

### Key Features:

- Key Pipeline Directives
- `agent`: Defines where the pipeline runs (e.g., Docker, node).
- `environment`: Sets environment variables.
- `options`: Set pipeline-level options like timeout or retry.
- `stages` and steps: Define the execution flow.
- `post`: Define post-build actions like sending notifications.
- `parameters`: Accept input from users (e.g., string or boolean).
- `tools`: Define tools like JDK, Maven, or Node.js.
