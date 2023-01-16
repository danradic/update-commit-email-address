If you encounter one of these situations:

 &#8226; Changing development machine <br>
 &#8226; Commits aren't showing up on GitHub contributions graph <br>
 &#8226; Not seeing your avatar next to your commits <br>
 &#8226; Getting the following github error: 'remote: error: GH007: Your push would publish a private email address' <br>

Issue: your local Git email may not be linked to your account.

It is advisable to first verify that your username and email on your local machine match the ones used in your commits:

 &#49;. Open Git Bash / cmd <br>
 &#50;. Check the current email and username: <br>
```
git config --global user.email
git config --global user.name
```
 &#51;. Check the email and username used for a commit:<br>
 ```
 add .patch to the end of a commit URL, e.g. 
 https://github.com/octocat/octocat.github.io/commit/67c0afc1da354d8571f51b6f0af8f2794117fd10.patch
 ```
If the email and username used in your local machine and commits do not match, follow these steps:

 &#49;. Update the email and username<br>
 ```
git config --global user.name "yourUserName"
git config --global user.email yourEmail@email.com
```
`yourUserName = https://github.com/yourUserName` <br>
`yourEmail@email.com = https://github.com/settings/emails > Primary email address` <br>

 &#50;. Confirm that you have set the email and username correctly<br>
 ```
git config --global user.email
git config --global user.name
```
 &#51;. Change the email and username for all commits following the specified commit id (SHA), while maintaining the original timestamps:<br>
```
cd into your .git folder
git rebase -i YOUR_SHA -x "git commit --amend --author 'yourUserName <yourEmail@email.com>' -CHEAD"
```

 &#52;. Sync changes on your local machine
