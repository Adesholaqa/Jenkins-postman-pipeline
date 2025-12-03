# Jenkins–Postman Pipeline

This project demonstrates how to automate Postman API tests using Jenkins pipeline and Newman CLI.

---

## Project Contents

- `Jenkinsfile`: Jenkins pipeline definition that runs Postman collections via Newman.
- Postman Collection JSON (`New-Rest-Broker.postman_collection.json`).
- Postman Environment JSON (`RestfulBooker.postman_environment.json`).
- Generated Newman HTML report (`newman/newman-report.html`).
- Screenshots folder 
- `README.md` (this file).

---

## Prerequisites

- Jenkins installed and running (tested on Jenkins 2.528.2).
- Newman CLI installed on Jenkins build agent (node.js/npm required).
- Postman API key stored as Jenkins credential (ID: `postman-api-key`).
- Git installed to clone this repo.

---

## How to run the pipeline

1. **Clone this repository** to your Jenkins workspace or local machine:

   ```bash
   git clone https://github.com/Adesholaqa/Jenkins-postman-pipeline.git
   cd Jenkins-postman-pipeline


2. Set up Jenkins:

 Add your Postman API key as a secret text credential in Jenkins with ID postman-api-key.

 Create a new pipeline job in Jenkins.

 Set the pipeline definition to use the Jenkinsfile from this repository.

3. Run the pipeline job:

 Jenkins will execute the stages:

 Verify files exist

 Login to Postman CLI using API key

 Run Newman CLI to execute Postman tests with HTML report generation

 Archive the HTML report as build artifact

4. View the HTML report:

 After the build completes, go to the build’s artifacts section.

 Download or view newman-report.html with full styling and colors.

