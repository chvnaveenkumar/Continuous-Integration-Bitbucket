# Continuous Integration - Bitbucket

## How to Add Continuous Integration to your Project.

1. Build a sample Node JS Appliction.
   [Sample NodeJS Application repo](https://github.com/chvnaveenkumar/Continuous-Integration-Bitbucket)
   
2. Implement Continous Integration with Bitbucket Pipelines.
    
    2.1. Login into  bitbucket and Create new repository.
       
    ![Create](/images/1.png)
       
    2.2. Maintain code in your bitbucket repository.
    
    2.3. Go to Pipelines by clicking on the corresponding menu item in the sidebar.
    
    ![Pipe](/images/2.png)
    
    2.4. Choose a language template and configured via the bitbucket-pipelines.yml file.
        
    ![Choose](/images/3.png)
    
    2.5. The below example should have the command npm install.(Remove npm test because we are not testing here. if you have test cases you can use.)
    
    ![YML](/images/4.png)
    
    2.6. Finally do commit.
    
 3. Deploy this repository to Heroku via the Git interface.
    
    3.1. Login into Heroku and create new app.
    
    3.2. Set HEROKU_API_KEY and HEROKU_APP_NAME environment variables in the repo.( go to repo settings click on Environment Variable under piplines )
    
       ![YMLCode](/images/5EnvironmentVariables.png)
    
    3.3. Add below script to bitbucket-pipelines.yml in the repository.
    
    - script:
    
       - git push https://heroku:$HEROKU_API_KEY@git.heroku.com/$HEROKU_APP_NAME.git HEAD
      
       ![YMLCode](/images/7Ymlfile.png)
    
    3.4. After adding script into bitbucket-pipelines.yml then do commit.
    
    3.5. Goto Pipelines then check the pipeline status. if it is green then application deployed successful. Red shows build failed then check your code and deploy.
      
       ![final](/images/8succes.png)

# Tutorial

https://www.atlassian.com/continuous-delivery/continuous-integration-tutorial
