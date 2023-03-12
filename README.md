# Smartcow Assignment

### Task 1 - Dockerize the Application
#### Assumptions

##### Things that were added
* There is no docker-compose.yaml file
* Updated the requirements.txt file
* Updated the React application so that the DNS resolution is not being done at the client end. The below code snippets were replaced in the sys-stat application in the App.js file
```
const res = await fetch('/stats');
```

#### Why I choose the specific image:
* Ubuntu Image Due to less size as compared to Python based base image
* User is 785(nobody)
* Entrypoint has been used to prevent command override
