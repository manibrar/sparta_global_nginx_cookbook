# nginx

## NGINX cookbook description
This cookbook was compiled using Chef 14.2 with kitchen 1.22.
This cookbook can be linked to Ubuntu/Xenial64 16.04 virtual boxes running chef to provide http and reverse proxy services.
This cookbook has been compiled to use with chef

## How to install on an individual virtual machine using vagrant
### 1) Create a Vagrantfile or clone the file from https://github.com/manibrar/sparta_global_development_environment/blob/envConf/Vagrantfile.
### 2) In the Vagrant box config add the line:  
development.vm.provision "chef_solo" do |chef|
  chef.add_recipe "nginx::default"
end.
### 3a) If you would like to pull your cookbooks from a github repository, in the Berksfile add the line:
cookbook 'nginx', git: 'INSERT YOUR CLONED REPOSITORY SSH LINK HERE'
### 3b)  If you would like to pull your cookbooks from a repository stored within the project type the command 'berks vendor cookbooks'
### 4) Open up terminal and navigate to the folder which contains your Vagrantfile, once there type the command 'berks update' to ensure your newest cookbook will be used.  
### 5) To initialise your virtual machine type the command 'vagrant up'.
### 6) Once initialised the machinee is configured to forward requests on port 80 to port 7000, this can be changed in the template > proxy.conf.erb file.
