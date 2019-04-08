# Overview
Infrastructure for the [GENIE](https://github.com/Sage-Bionetworks/Genie)
application.


# Purpose
This repo contains infrastructure templates for the GENIE batch jobs. 

* validation
* input to database
* database to staging
* release


## Security
The instances running agora and the database for it runs in a private
subnet which means neither the instances nor the database are accessible
from the internet.  GENIE contains limited PHI


## Continuous Integration
We have configured Travis to deploy CF template updates.  Travis deploys using
[sceptre](https://sceptre.cloudreach.com/latest/about.html)



## Instructions to setup batch
Build an AMI that can run batch jobs! Start from this page and follow instructions and specify your docker image. It is important at this stage that you time the building of your AMI, or your AMI will not be able to start batch jobs. After doing so, you will have to start an instance with the AMI and run these 2 commands:

```
sudo start ecs
sudo stop ecs
sudo rm -rf /var/lib/ecs/data/ecs_agent_data.json
```

Rebuild the AMI above, specify the size of the image and put whatever you want in the instance that you would want to bind