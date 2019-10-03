## Installation Guide
- Install GIT - https://git-scm.com/book/en/v2/Getting-Started-Installing-Git
- Install Docker - https://www.docker.com/products/docker-desktop
- Run jenkins docker
  - Windows
    ```bash
    docker run -u root --rm -d -p 8080:8080 -p 50000:50000 --name jenkins -v //var/run/docker.sock:/var/run/docker.sock -v "C:/PATH-TO-JENKINS-DATA":/var/jenkins_home jenkinsci/blueocean
    ```
   - Unix
     ```bash
     docker run -u root --rm -d -p 8080:8080 -p 50000:50000 -v PATH-TO-JENKINS-DATA:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock jenkinsci/blueocean
     ```
  - Enter running docker container
    ```bash
     docker exec -i -t jenkins /bin/bash
     ```
  - More details about installation [Jenkins with Docker](https://jenkins.io/doc/book/installing/#docker)
- Verify Jenkins is running by opening going to url: http://localhost:8080
  
## Build/Run
- Source code of the React app is based on "react-shopping-cart" app made under MIT license by Jefferson Ribeiro
- App is deployed to [Firebase](https://tesena-ci-2019.firebaseapp.com)

#### Requirements

- Node.js
- NPM

```javascript

/* First, Install the needed packages */
npm install

/* Then start both Node and React */
npm start

/* To run the tests */
npm run test

/* Build sources */
npm run build

/* Running e2e tests */
npm run wdio

/* Deploy to Firebase */
./node_modules/.bin/firebase deploy --token=$FIREBASE_DEPLOY_TOKEN


```

## About tests .

- Unit tests
  - All components have at least a basic smoke test
- Integration tests
  - Fetch product and add to cart properly
- e2e
  - Webdriverio - Add and remove product from cart

### Copyright and license

The MIT License (MIT). Please see License File for more information.
