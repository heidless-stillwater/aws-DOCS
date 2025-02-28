
# [AWS + Rails - Playlist](https://www.youtube.com/playlist?list=PL6lusswsNPHG5csQPFjMExe5XQqr1cJvq)

# [How to Create Your First Rails App](https://www.youtube.com/watch?v=ssPPyizWJuc&list=PL6lusswsNPHG5csQPFjMExe5XQqr1cJvq&index=5)
# install postgres (kali)
## [98. PostgreSQL DBA: How to install and configure PostgreSQL 16 on Kali Linux 2022 / 2023](https://www.youtube.com/watch?app=desktop&v=tC5XIhSWT9I)
```
# install postgres (kali)
sudo apt-get install postgresql postgresql-contrib

sudo systemctl status postgresql
sudo systemctl start postgresql
sudo systemctl enable postgresql

sudo su - postgres
psql
select version();
\du
alter user postgres with password 'postgres';
\du

--

```

## app
```
npm install --global yarn
bundle exec rails webpacker:install

rails new aws-rails -d postgresql



```

# [How to Create an Amazon EC2 Instance for a Rails App Deployment (Ubuntu 20.04 Focal Fossa)](https://www.youtube.com/watch?v=M0avxObh8J8)
```



```


# [How to Deploy Your First Rails App to Amazon EC2 (Ubuntu 20.04 Focal Fossa Capistrano Deployment)](https://www.youtube.com/watch?v=YJzYmhxB8rE)

```
cd ~/projects/heidless-aws/aws-tuts/aws-rails-cap-deploy

sudo apt install ruby-bundler
bundle install

rvm install 2.7.1

/bin/zsh --login
rvm use --default 2.7.1
export PATH="/home/heidless/.rvm/gems/ruby-2.7.1/bin:$PATH"

# install capistrano

# setup github ssh keys
https://docs.github.com/en/authentication/connecting-to-github-with-ssh/checking-for-existing-ssh-keys
--
########################
# check for existing key
ls -al ~/.ssh
# Lists the files in your .ssh directory, if they exist

################
# create new key
https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent
#
ssh-keygen -t ed25519 -C "rob.lockhart@yahoo.co.uk"
<no passphrase>

######################################
# Adding your SSH key to the ssh-agent
#
# start ssh-agent
eval "$(ssh-agent -s)"
> Agent pid 17656

# Add your SSH private key to the ssh-agent
ssh-add ~/.ssh/id_ed25519

#############################################
# Adding a new SSH key to your GitHub account
https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account
#
# Copy the SSH public key to your clipboard.
cat ~/.ssh/id_ed25519.pub
# Then select and copy the contents of the id_ed25519.pub file
# displayed in the terminal to your clipboard

# on github.com
profile-photo->Settings
--
SSH & GPG Keys
New SSH Key
--
git-clone-ssh-authentication
Authentication
<Paste Public Key>

--

# configure config/deploy.rb
--
set :application, 'aws-rails'
set :repo_url, 'git@github.com:heidless-stillwater/aws-rails-cap-deploy.git'



--

```