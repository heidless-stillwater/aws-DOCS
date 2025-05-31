

# [Deploy Rails 7.1 To AWS With Docker And Nginx!](https://www.youtube.com/watch?v=UmAx1A6ic2M)

## [aws account](https://eu-west-2.console.aws.amazon.com/console/home?nc2=h_ct&region=eu-west-2&src=header-signin#)
```
heidless-0

```

#################
## RESOURCES USED
#
```
EC2 Instances:
RailsDeployEC2

EC2 Volumes:
vol-05ab09eda55c3b7b0

```

# Create Instance
```
# EC2->LaunchInstance->Name
RailsDeployEC2

# Application & OS Image
Search: 'docker'
Choose: Docker on Ubuntu 22.04
'Select'

# instance type
t2.micro

# keyair
Create New Keypair
'aws_rails_0'
RSA
.pem

# create security group

# Allow HTTPS traffic from internet
# Allow HTTP traffic from internet

# Configure Storage
12 
Magretic(Standard)

'Launch Instance'

```

##################
# create rails app
#
```
rails _7.2.2.1_ new rails_app_0 --main

cd rails_app_0
rails g scaffold post title

rails g action_text:install

vi config/routes.rb
--
  root "posts#index"

--

vi models/post.rb
--
  has_rich_text :body

--

vi posts_controller.rb
--
# Only allow a list of trusted parameters through - ADD BODY.
    def post_params
      params.expect(post: [ :title, :body ])
    end

--

vi views/posts/_form.html.erb
--


--



```

