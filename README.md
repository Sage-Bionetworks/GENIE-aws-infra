# Overview
Infrastructure for the [GENIE](https://github.com/Sage-Bionetworks/Genie)
application.


# Purpose
This repo contains infrastructure templates for the GENIE batch jobs


## Security
The instances running agora and the database for it runs in a private
subnet which means neither the instances nor the database are accessible
from the internet.  GENIE contains limited PHI


## Continuous Integration
We have configured Travis to deploy CF template updates.  Travis deploys using
[sceptre](https://sceptre.cloudreach.com/latest/about.html)

