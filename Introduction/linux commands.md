## Working With Linux Command(s)

1. Directory Listing
ls is the linux command that helps in listing files and directories.
`ls`
Try ls with additional options such as -l. -l option instructs ls to display one file per line with additional details.
`ls -l`

2. Create a new directory
mkdir command helps in making (or creating) a new directory.
`mkdir my-directory`

3. Removing a directory
rmdir is the command used to remove (or delete) a directory.
`rmdir my-directory`

4. Save file using cat command
```
cat > filename <<EOL

Some text content
Some text content 2
Some text content 3

EOL
```

5. Output Redirection
`cat /etc/passwd > mypasswd.txt`
`cat /etc/passwd >> mypasswd.txt`

6. Cut Command
`cat mypasswd.txt | cut -d ':' -f 1`

7. grep command
`ps -aux | grep bash`

8. View Permissions
`ls -l myfile`
`stat myfile`

9. Give permissions
`chmod +x myfile`

10. Add a new user
`echo -e "pdevsecops\npdevsecops" | adduser --gecos "" john`

11. Add user the group
`usermod -aG sudo john`

12. Change user
`sudo su - john`

13. Exit code
`echo $?`

14. Initial git setup
To work with git repositories, we need to first setup a username and email.
```
git config --global user.email "student@pdevsecops.com"
git config --global user.name "student"
```

15. Download/clone/copy the repository
`git clone git@gitlab-ce-47pv40ou:root/django-nv.git`

16. Status Check
`git status`

17. Add the file(s) to the stage
`git add myfile README.md`

18. Commit the changes to the repository
`git commit -m "Add myfile and update README.md"`

19. Pushing Commits to the Remote Repository
`git push`

20. Pull the changes from the repository
`git pull`

21. SSH login
`ssh -i ~/.ssh/id_rsa root@prod-47pv40ou`
`ssh-keyscan -t rsa prod-47pv40ou >> ~/.ssh/known_hosts`

22. Working with jq
`echo '{"cloudprovider":{"name":"AWS","url":"www.aws.com"}} ' | jq '.'`
`curl https://randomuser.me/api/ | jq '.'`
`jq '.' learnjq.json`
`jq '.[] |  .details' learnjq.json`
`jq '.[1] | {name: .details.name, url: .details.url}' learnjq.json`
If you want to get the result as a single array, then you can also wrap the filter in a square bracket. jq will then collect the data in a single array in the resulting output.
`jq '[.[] | {name: .details.name, url: .details.url}]' learnjq.json`
`jq '.[] | {name: .details.name, url: .details.url, services: .services[]}' learnjq.json`

