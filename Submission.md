# Project 2 - Submission

## Region

As I am currently french citizen, I set my default configuration for 
zone **eu-west-3** (Paris). So in the server file, you'll be having ami
configuration's name regardly what is available in this region.

The ami choosen is the one available with Free Tier and Ubuntu 18.04 this allowed
me to test the CloudFormation configuration using t2.micro in order to stay
in the Free Tier, then I updated the config file regarding the specifications
given in the project description.

## Schematics

Before writing all the details composing the CloudFormation Stack files,
I had to schematize all the network & server structure.
I used for it **LucidChart**, tool that was presented to us during 
Phase 1.

You'll find a sharing link of the schema (hope it is still available if you try it)

[Schematic for CloudFormation for Project 2](https://www.lucidchart.com/invitations/accept/444fea53-62b4-40a0-8ecb-d71abc78647e)

If it is not available, you'll be able to have a look upon the exported file

[Image Export from LucidChart](Schema%20-%20LucidChart%20-%20Project%202.png)

## CloudFormation Stacks

I choose to separate network and server configuration in 2 different files.

It would work like if 2 teams were dealing with each one concept and at the end, 
would be gluing back all the pieces to build the **Project 2**.

In [network file](private-network.yml) you'll be able to find : 
* VPC
* EIP
* Subnets
* Gateway
* NAT
* RouteTable
(Parameters are available in [specific file](private-network-parameters.json))

Because some information created in network step will be used in server step, 
I had to "export" some datas to be used in the server file.

In [server file](servers.yml) you'll be able to find : 
* Load Balancer (with )
* Launch Configuration
* AutoScaling group configuration
* Health Check Configuration
* Security Group
* Listener
* Target Group
(Parameters are available in [specific file](servers-parameters.json))

The only output I'll be using in the server step, is the URI which whom you'll 
be able to hit and test by yourself that the website is fully functional.

Normally, you should have something like this [Welcome Page](welcome_page.png).