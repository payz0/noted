# IP public tanpa install
If you're running Ubuntu on Windows Subsystem for Linux, there will not be a preinstalled public key or authorized keys list, so you'll need to generate your own.

If you don't already have openssh-server installed:

sudo apt-get upgrade

sudo apt-get update

sudo apt-get install openssh-server

sudo service ssh start


Then take the following steps to enable sshing to localhost:

cd ~/.ssh

ssh-keygen to generate a public/private rsa key pair; use the default options

cat id_rsa.pub >> authorized_keys to append the key to the authorized_keys file

chmod 640 authorized_keys to set restricted permissions

sudo service ssh restart to pickup recent changes

ssh localhost

ssh -R 80:localhost:[port_local] ssh.localhost.run
