we should be able to type vagrant up and our app will be running and reachable on http port 80 at http://10.10.10.20
    **** using gunicorn which is listening in the daemon mode on port 80 . IP 10.10.10.20 is configured in the vagrant file.
Guidelines:
		The provisioner should clone this github repo into the VM under /webapps/devops
		**** Ansible playbook has a task to perform this task
		You should be able to find what system packages are needed by looking through the app
		**** Used the requirements.txt file provided to install the required modules 
		You should not need to change the app code in any way
		**** Did not change the app code used it as is 
		The app should be running as a non-privileged user
		**** Used the ubuntu user avaialable by default to run the service 
		The app should be automatically restarted if crashes or if killed
		**** gunicorn running in daemon mode restarts worker processes if killed  , Monit is monitoring the gunicorn wrapper service called webapp
		The app should maximize all of the available CPUs (have Vagrant virtualize multiple CPUs)
		**** gunicorn is configured to run worker proceses equal to VCPU's avaialable on the system 
		The related logs should be rotated
		**** Used logrotate.d to rotate access and std out logs created by gunicorn daemon which is running app.py
		Timezone should be in UTC
		**** Ansible playbook has a task to perform this task