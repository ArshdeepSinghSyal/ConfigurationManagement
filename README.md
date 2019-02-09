# HW2-DevOps

#### Name: Arshdeep Singh Syal
#### Unity Id: asyal
#### Link to screencast video: https://drive.google.com/file/d/1yV4d3RxhLtRfRnb_hat9ykNXFATjHRHQ/view?usp=sharing

I have written an ansible playbook which runs on a configuration server and allows us to automatically configure a web server to remotely run mattermost on it.

I have divided this whole process in 4 major parts:

1) Installing Ubuntu Server 16.04 LTS

2) Installing MySQL Database Server (5.7.x is recommended)

3) Installing Mattermost Server

4) Configuring Mattermost Server

Each one of the above mentions parts are a collection of ansible tasks which maintain idempotency.
