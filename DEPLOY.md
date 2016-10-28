#Deploy

##Firebase

1. Create an account with [Firebase](https://firebase.google.com/)
2. Create a New Project
  1. Give your Project a Name e.g., WebGL Globe
  2. Select 'Create Project'
3. Navigate to the folder that holds this repository on your command line
4. Push all changes to github
5. Run firebase init on command line
6. Press the spacebar to deselect Database. Ensure that the 'Hosting' option is selected and push Enter.
7. Using the arrows, navigate to the firebase project you created in Step 2 and push Enter
8. For your public directory, use . and push Enter
9. Do not configure as a simple-page app, use N and push Enter
10. Do not overwrite ./index.html, use N and push Enter
11. Now your firebase initialization is complete!
12. To deploy, run firebase deploy on command line
  1. This will create a firebase.json, 404.html, and .firebasesrc file
  2. The output on your command line will provide the hosting site
13. Either copy and paste the Hosting Site in your browser, or run firebase open in your command line
  1. If you used firebase open, use your arrow keys to navigate to 'Hosting: Deployed Site' and press Enter

Congratulations, your site is now deployed to firebase!

If you have made changes to your code and want to update your deployed site:

1. Push all changes to github
2. Run firebase deploy on the command line

All of your changes should now be up on your deployed site!
