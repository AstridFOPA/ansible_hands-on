#ansible_tutorial


this is my awesome Ansible repository
 trying to see if it's work

okay i arrange the identation on the file site.yml 

okay I had some issue with my ansible playbook when I tried to create a new user inside the centos I won't able to access the servers with that method Although I did every step showd in the video. by the way It work with ubuntu servers  

although I masde the transfered on git , I will remove for the next video to make sure I get connectedd to all my server 
    - ON MY FILE ansible.cfg : I will cp the sudeoers_simone file change it to let him state in my repository, but it wont be use in my playbook
    - remove the remote_user on my ansible.cfg 
    - remove the ssh_key also 
    - leave the bootstrap.yml file also : which going to be use to create that new user remotly 
    - continue using the command : ansible-playbook --ask-become-pass < name of the playbook>