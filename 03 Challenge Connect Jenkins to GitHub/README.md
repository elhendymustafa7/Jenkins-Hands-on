# 03 Challenge Connect Jenkins to GitHub

You're on a team developing an algorithm that calculates the value of pi.

The code for the project is being stored in a GitHub repository. The team wants to test the latest changes to the algorithm with every push to the repo.

They also want to display the status of that most recent test directly in the repo’s README file.

## Tasks
- [ ] Create a new GitHub repo and add the exercise files for this lesson.
  - [ ] [Jenkinsfile](./Jenkinsfile)
  - [ ] [algorithm.sh](./algorithm.sh)
- [ ] Create a new pipeline project that pulls the code from the repo and uses the Jenkinsfile for the project definition.
- [ ] Install the Embeddable status plug-in and update the GitHub repo to show the status of the project.

## Tips
- Successfully building the project will create a artifact named `report.txt`.
- Review the contents of the report for more information.

_*This challenge should take about 15 to 20 minutes to complete.*_

## Solution

- configure new pipeline with GitHub hook trigger for GITScm polling

![image](https://user-images.githubusercontent.com/58703269/227803565-3da33024-ab17-423d-8da6-0f67c7721ccb.png)

![image](https://user-images.githubusercontent.com/58703269/227803587-c5c6a7fe-6eb8-40c2-91f6-cc9969142cfb.png)

![image](https://user-images.githubusercontent.com/58703269/227803612-0c3ca8b2-7ddc-4b4d-96c1-46c2d5a6c9cf.png)

- add webhook 

![image](https://user-images.githubusercontent.com/58703269/227803751-d7143ede-5b17-4026-96d5-81034e27c03f.png)![image](https://user-images.githubusercontent.com/58703269/227803751-d7143ede-5b17-4026-96d5-81034e27c03f.png)

- add then edit in your repo to see new build

![image](https://user-images.githubusercontent.com/58703269/227804017-7b441109-f246-4ba6-9705-87f52814bf13.png)