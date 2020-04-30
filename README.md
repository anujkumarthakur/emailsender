         
        Use Case: We have multiple international clients and each client has multiple users. 
        We need to send Good Morning Email to all users at 8 AM of their location.
        
        
        ######################      EmailSender(Solution)     ######################################
        
        STEP-1: Task: Create an application using Golang (using any database or in-memory storage)
                which sends out the Good Morning emails to all the users at 8 AM according to the different 
                time zones of the users
        
        SETP-2:
                git clone  git@github.com:anujkumarthakur/emailsender.git

        SETP-3: Database configuration
                mysql -u username -p
                create database emailsender;
                use emailsender;
                source /home/user/Desktop/emailsender/mysql/filename.sql
        
        STEP-4:
               open terminal remove binary file(app)
               1-> rm -rf app
               2-> go build -o app

        SETP-5: Systemd file configurations
                1. change emailsender.service file configuration
                    [Unit]
                    Description=emailsender
                    [Service]
                    Type=simple
                    Restart=always
                    RestartSec=5s
                    Environment=FROM="YOUR MAIL ID"
                    Environment=PASS="YOUR MAIL PASSWORD"
                    Environment=DBHOST="localhost"
                    Environment=DBUSER="mysql-user-name"
                    Environment=DBPASS="mysql-password"
                    Environment=DBPORT="3306"
                    Environment=DB="emailsender"
                    ExecStart=/home/{your system name}/Desktop/Assignment/app

                    [Install]
                    WantedBy=multi-user.target

        SETP-6: open terminal run below command
                sudo cp emailsender.service ../../../../lib/systemd/system/
        
        STEP-7: run below command on terminal
                systemctl start emailsender
                systemctl status emailsender(enable)
        
        Note-: software running in background if you want to check status run below command
               systemctl status emailsender(enable)

        ##################  Happy coding ####################################
