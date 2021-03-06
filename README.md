ansible-gocd
=============

Ansible Playbook to install Go.  

Model even the most complex build & deploy workflow with ease. Unlike CI servers, Go was built from the ground up with pipelines in mind. Go makes it simple to model failing fast, artifact promotion, self-service environments and single-click deployment.

Product details are available at http://www.go.cd .  Source will soon be at https://github.com/GoCD/GoCD

installation instructions
=========================

This repository is organized as a single Role. That means it can be included, symlinked, submoduled, or galaxied into your existing Ansible repository. 

The default is to install the server and agents onto a single node.  Use the tags of 'server' or 'agent' to selectively install one or the other.
### Server
* The server listens on port 8153 by default.  
  
### Agents
* By default one agent will be installed per CPU core available.  You can override this by setting gocd.agent.instances to a specific value.
* When multiple agents are installed each is controlled by it's own service (/etc/init.d/go-agentX). If you wish to uninstall the package, you'll need to manually remove those services as they're not recognized by the RPM/DEB.

## developing
Fork away!  Pull requests are always appreciated. :-)

You should be able to do a vagrant up and have a running instance of this role.  Take a look inside Vagrantfile and you'll notice we're forcing a role_path on Ansible.  

It's been tested on Vagrant 1.5.x with VirtualBox primarily, with a little attention paid to Docker on Linux via the docker-provider plugin.   
