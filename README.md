FakeNewsDetector Project

The aim of the fake news project is to help news readers to identify bias and misinformation in news articles in a quick and reliable fashion.
              We have collected news articles with veracity labels from fact-checking websites and used them to train text classification systems to detect fake from real news. You can paste a piece of text and examine its similarity to our collection of true vs. false news articles, or to news from four different types/genre. Enjoy testing!


© 2024 Fake News Detector

How to Set up Docker
Step 1 - First you have to install Docker at your Computer if you haven't already isntalled, following one by one these commands. More instructions and details of
how to download docker can be found here: https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04
   
  1. First, update your existing list of packages:

    sudo apt update
    
  2. Next, install a few prerequisite packages which let apt use packages over HTTPS:
  
    sudo apt install apt-transport-https ca-certificates curl software-properties-common
     
  3. Then add the GPG key for the official Docker repository to your system:

    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
      
  4. Add the Docker repository to APT sources:

    sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
      
  5. Make sure you are about to install from the Docker repo instead of the default Ubuntu repo: 

    apt-cache policy docker-ce

  6. Finally, install Docker:
  
    sudo apt install docker-ce

  Docker should now be installed, the daemon started, and the process enabled to start on boot. Check that it’s running:
  
    sudo systemctl status docker

  7. Install Docker Compose:

    sudo apt-get install docker-compose-plugin

  8. Verify that Docker Compose is installed correctly by checking the version:
   
    docker compose version

Step 2 — Executing the Docker Command Without Sudo

  1. Avoid typing sudo whenever you run the docker command, add your username to the docker group:
    
    sudo usermod -aG docker ${USER}

   2. To apply the new group membership, log out of the server and back in, or type the following:
    
    su - ${USER}

Step 3 - Install Images and run the project 

  l. step only need to change the access permissions for your WordPress Directory by using the following commands in the following path /Desktop/FakeNewsDetector/src :
    
    sudo chown -R www-data:www-data wp-content/plugins/
    sudo chmod 775 wp-content
    sudo chown -R www-data:www-data wp-content/

  2. Now you need to run the final command to install the images and dockerize the project.

    sudo docker compose up -d

  3. After finishing installation make sure that all the containers are running. And the wordpress index page is running on http://localhost:8000/

Thank for Installing and Enjoy Testing!
   
     
