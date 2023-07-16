# SonarQube Integration with Jenkins

This project demonstrates the integration between SonarQube and Jenkins for continuous code quality analysis.

## Description

The purpose of this project is to provide a seamless integration between SonarQube and Jenkins for automated code quality analysis. It allows you to easily analyze your codebase for potential issues, bugs, and vulnerabilities, ensuring higher code quality and better maintainability.

## Features

- Automated code quality analysis using SonarQube
- Integration with Jenkins for continuous integration and deployment
- Generates comprehensive reports on code issues, bugs, and vulnerabilities
- Provides insights into code coverage, maintainability, and reliability
- Enables easy identification and tracking of code improvements over time

## Installation

To use this project, follow these steps:

1. Clone the repository to your local machine:
'
git clone https://github.com/Shahid199578/sonarqube_integration_with_jenkins.git

'

2. Install and configure SonarQube on your system. Refer to the SonarQube documentation https://docs.sonarqube.org/ for detailed instructions.

3. Set up Jenkins on your system. Refer to the Jenkins documentation  for detailed instructions.

4. Install SonarQube Scanner in your Jenkins environment:
- Go to Jenkins dashboard and navigate to "Manage Jenkins" > "Global Tool Configuration".
- Scroll down to the "SonarQube Scanner" section and click on "SonarQube Scanner installations..."
- Click on "Add SonarQube Scanner" and provide the necessary details, such as name and path to the SonarQube Scanner installation. Save the configuration.

5. Create a project in SonarQube:
- Log in to your SonarQube dashboard.
- Create a new project and generate a unique project key for it.

6. Configure SonarQube variables in Jenkins:
- Go to Jenkins dashboard and navigate to "Manage Jenkins" > "Configure System".
- Scroll down to the "Global properties" section and click on "Environment variables".
- Add the following environment variables:
  - `sonarurl`: The URL of your SonarQube server (e.g., `http://localhost:9000`).
  - `sonarkey`: The access token or API token generated in SonarQube for Jenkins integration.
- Save the configuration.

7. Create credentials in Jenkins for SonarQube integration:
- Go to Jenkins dashboard and navigate to "Manage Jenkins" > "Manage Credentials".
- Click on "Global credentials" and then "Add Credentials".
- Provide the necessary information, including the SonarQube access token or API token, and save the credentials.

8. Configure Jenkins job:
- Create or open the Jenkins job for your project.
- Add the necessary build steps to compile and analyze the code using SonarQube.
- In the build step configuration, specify the SonarQube project key and name (created in Step 5).
- Configure the SonarQube scanner properties, such as source code location, exclusion rules, etc.
- Add the SonarQube credentials (created in Step 7) for authentication.
- Save the job configuration.

## Usage

To use this project, follow these steps:

1. Make sure your Jenkins server and SonarQube instance are up and running.

2. Trigger the Jenkins job for your project to initiate the build and code analysis process.

3. Monitor the Jenkins job logs and console output for any errors or warnings.

4. Access the SonarQube dashboard to view detailed reports and analysis results.

5. Analyze the SonarQube reports and take necessary actions to improve code quality.

