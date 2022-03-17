# NUSFintechSG B16 PC3 Devops Course Show and Tell - Currency Exchange API NodeJS
Credit to Prof Uli Hitzel for the application [https://github.com/u1i/nodejs-api/](https://github.com/u1i/nodejs-api/) as well as the guidance to deploy the application on Google Cloud!

Live Endpoint (after CI/CD Deployment): [https://alvinnodejsapi-g7wysuozqa-as.a.run.app/](https://alvinnodejsapi-g7wysuozqa-as.a.run.app/)

What does Currency Exchange API NodeJS do?

* On every GIT push and pull Github issues instructions to update and run Currency Exchange API NodeJS on my Google Cloud instance
* The endpoint is available @ [https://alvinnodejsapi-g7wysuozqa-as.a.run.app/](https://alvinnodejsapi-g7wysuozqa-as.a.run.app/)
* Able to run these GET commands:  GET https://alvinnodejsapi-g7wysuozqa-as.a.run.app/, GET https://alvinnodejsapi-g7wysuozqa-as.a.run.app/api/, GET https://alvinnodejsapi-g7wysuozqa-as.a.run.app/fx-static/, https://alvinnodejsapi-g7wysuozqa-as.a.run.app/fx/, GET https://alvinnodejsapi-g7wysuozqa-as.a.run.app/random/

Show and Tell Instructions:

1. Clone Github repository. There are some minor changes that need to be made, e.g. Setup gcloud CLI uses setup-gcloud@v0, I am using main branch and not master branch. App.js can be amended to change some of the get outputs, i.e. I have added my name to the version number to make it clear that my Endpoint is working.

2. Enable the necessary Google Cloud APIs. I have enabled these APIs: Cloud Build API, Cloud Run Admin API, Google App Engine, Cloud Resource Manager API, Identity and Access Management API.

3. IAM Management: Need to enable the following roles for the principal in the project in Google Cloud - Cloud Build Editor, Cloud Build Service Account, Cloud Run Admin, Service Account User, Storage Admin, Viewer.

4. Service Account set up: After enabling Service Account, set up a service account key by going to IAM -> Service Accounts -> Keys -> Add Key -> JSON -> Create in Google Cloud.

5. With the Service Account set up, Github has to store these variables to run CI/CD correctly. In the cloned and edited repository, Github settings need to be updated. Settings -> Secrets -> Actions -> New Repository Secret.

GCP_APPLICATION: Desired application name. Take note that the Endpoint address will be this name.
GCP_CREDENTIALS: Service account key in JSON format.
GCP_EMAIL: Service account email.
GCP_PROJECT: Google Cloud instance project ID.

6. Push the changes to Github and Github runs the CI/CD commands in deploy.yaml to Google Cloud. Check the changes at the endpoint.