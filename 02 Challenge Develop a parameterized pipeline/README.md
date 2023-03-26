# 02 Challenge: Develop a parameterized pipeline

You're on a development team using Jenkins to test and deploy a new application. Your team has already developed the outline for a pipeline. Now they need to update the pipeline so that it accepts parameters for multiple environments. 

You've been given several requirements for  the updates.

## Add Parameters
You will need to add three parameters to the existing pipeline:

|Parameter Name|Description|Default Value|
|:--|:--|:--|
|ENVIRONMENT|Selects DEVELOPMENT, STAGING, AND PRODUCTION|DEVELOPMENT|
|APIKEY|Passes a secret value into the pipeline|123ABC|
|CHANGELOG|Free-form text that can be added to a report|This is the change log.|

## Update Stages

There are three stages in the pipeline: `Test`, `Deploy`, and `Report`.

- [ ] Update the `Deploy` stage to only deploy to the production environment.
- [ ] Update the `Report` stage to use the contents of the changelog for the report content.
- [ ] Update the `Report` stage to use the environment as the name of the report file. 

## Tips
- Use the *Declarative Directive Generator* in the Pipeline Syntax tool to create snippets for the parameters and any other directives if needed.

- Start a new pipeline project and use the following code:
```Jenkinsfile
pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                echo "This step tests the project"
            }
        }
        stage('Deploy') {
            steps {
                echo "This stage deploys the project"
            }
        }
        stage('Report') {
            steps {
                echo "This stage generates a report"
                sh "printf \"This is the change log.\" > report.txt"
                archiveArtifacts allowEmptyArchive: true, 
                    artifacts: '*.txt', 
                    fingerprint: true, 
                    followSymlinks: false, 
                    onlyIfSuccessful: true
            }
        }
    }
}
```

_This challenge should take 15-20 minutes to complete._

## Solution

- Create a new pipeline 

![image](https://user-images.githubusercontent.com/58703269/227743797-68b3f5d0-e960-455a-841c-7b5796bc8531.png)

- using the following script 

![image](https://user-images.githubusercontent.com/58703269/227743855-6f32617e-5c58-4035-a53f-9e5761367daf.png)

```Jenkinsfile
pipeline {
    agent any
    parameters {
      choice choices: ['DEVELOPMENT', 'STAGING', 'PRODUCTION'], 
         description: 'Choose the environment for this deployment.', 
         name: 'ENVIRONMENT'
      
      password defaultValue: '123ABC', 
         description: 'Enter the API key to use for this deployment.', 
         name: 'API_KEY'
      
      text defaultValue: 'This is the change log.', 
         description: 'Enter the components that were changed in this deployment.', 
         name: 'CHANGELOG'
    }    
    stages {
        stage('Test') {
            steps {
                echo "This step tests the compiled project"
            }
        }
        stage('Deploy') {
            when {
              expression { params.ENVIRONMENT == "PRODUCTION" }
            }            
            steps {
                echo "This step deploys the project"
            }
        }        
        stage('Report') {
            steps {
                echo "This stage generates a report"
                sh "printf \"${params.CHANGELOG}\" > ${params.ENVIRONMENT}.txt"
                archiveArtifacts allowEmptyArchive: true, 
                    artifacts: '*.txt', 
                    fingerprint: true, 
                    followSymlinks: false, 
                    onlyIfSuccessful: true
            }
        }
    }
}
```

- build pipeline once as deployment and  production

![image](https://user-images.githubusercontent.com/58703269/227743953-6f292571-b454-4f5a-baad-5d1d86e80413.png)

