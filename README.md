# HW2-DevOps

#### Name: Arshdeep Singh Syal
#### Unity Id: asyal
#### Link to screencast video: https://drive.google.com/file/d/1yV4d3RxhLtRfRnb_hat9ykNXFATjHRHQ/view?usp=sharing

I have written an ansible playbook which runs on a configuration server and allows us to automatically configure a web server to remotely run mattermost on it.

I have created 2 virtual machines, the first one is the configuration server which has Ansible installed on it and is used to run the Ansible playbook which I have created that contains . The second virtual machine is the web server on which the ansible script is creating and running the Mattermost server.

<img width="474" alt="screenshot 2019-02-08 at 11 42 52 pm" src="https://media.github.ncsu.edu/user/12952/files/29875a00-2bfc-11e9-9e59-090d6b667300">

<img width="646" alt="screenshot 2019-02-08 at 11 45 20 pm" src="https://media.github.ncsu.edu/user/12952/files/2be9b400-2bfc-11e9-9d8d-b07504637075">

I have divided the remaining project in 4 major parts:

1) Installation and setup of the MySql server

The first part which is in the file ab.yml, which takes care of the installation and setup of the mysql server and its required dependencies. In this we also create a user and a database.

```ansible-playbook ab.yml -i inventory```



2) Installation of the Mattermost server

The second part which is in the file cd.yml, takes care of installation of the mattermost server and its dependencies. Through this playbook we also create a directory a group and a user and set perm missions for them.

```ansible-playbook cd.yml -i inventory```



3) User creation in the mattermost server

The third part which is in the file ef.yml, takes care of user creation in the mattermost server. In this playbook we create a team and admin account and a user account.

```ansible-playbook ef.yml -i inventory```



4) Setting up the SMTP connection

The fourth and the last part which is in the file gh.yml, takes care of setting up the smtp connection with Zoho mail and restarting the mattermost server. 

```ansible-playbook gh.yml -i inventory```


Now that we have received success on running all the taks in our Ansible playbook, we verify if the server is up and running by going to the IP address of the mattermost server, ie. 198.168.33.100:8065.
I have created sample credentials to show that we can log onto the server.

Each one of the above mentioned parts are a collection of ansible tasks which maintain idempotency.
