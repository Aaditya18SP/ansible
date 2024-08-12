# THINGS TO KEEP IN MIND WHILE INSTALLING OHMYZSH   
 
1. I have created a new user with sudo privileges with password as "password". This helps to emulate a real world scenario
2. Ansible, git, curl, setting the user password is done in the Dockerfile ie it is expected that you have all these packages installed
3. After getting all these packages, go to the Ansible directory and run the command as `ansible-playbook install-xyz.yml --ask-become-pass`. Then enter theuser password
4. In the ansible YAML file, while installing ohmyzsh from the internet, use the flag `--skip-chsh` in order to skip the installer asking whether you want to switch to zsh. The task below this one, does that for you. The reason for using this flag is that at the end the ohmyzsh script asks to switch your defautl shell to zsh and it requires human intervention to answer it and I couldn't find any way around it. 
5. Dont use BASH variables such `$ZSH_CUSTOM` while using the inbuilt ansible git module in the YAML file as it doesn't know what the variable is.Hence your plugins are not added.
6. Lastly, `sed` is not the best way to add your plugins but it does the jo but it does the job.


*** AND VOILA YOU SHOULD HAVE OHMYZSH INSTALLED *** 
