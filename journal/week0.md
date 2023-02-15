# Week 0 — Billing and Architecture

# Set billing alarm/budgets

- three ways to set up billing alarms

1. billing dashboard, go to billing preferences, get notifications. old way: setting up alarms, get 10 max for the free tier
2. budgets, budget is more helpful because it has more advanced features, it notifies you 3x when you pass certain thresholds and are about to max out budget. can get 2 budgets on free tier(50%, 75%, 100%)
3. cost allocation tags. create a tag for a project (?), activate them which is another way of getting notifications if you're overspending

# Generating AWS Credentials

- log in as a root user
  -search for IAM in management console
  -create users, then group
  -assign certain policies to groups, and the users added to this group will be able to perform tasks they were given permission to
  -make sure you have the user reset password when they first sign in

# Using CloudShell/ aws cli

[Detailed instructions](https://github.com/omenking/aws-bootcamp-cruddur-2023/blob/week-0/journal/week0.md)<br>
[youtube video](https://www.youtube.com/watch?v=OdUnNuKylHg&list=PLBfufR7vyJJ7k25byhRXJldB5AiwgNnWv&index=12&ab_channel=ExamPro)

- can use CloudShell CLI rather than aws management console UI to do all your tasks using preferred shell (bash, powershell, or Z shell)
- free of charge
- cloudshell comes with pre-installed and utilities such as: git, make, pip, sudo, tar, tmux, vim, wget, zip
  -create access keys, download csv file and then import. give it to user
  -need to set it up on gitpod as well!
    -use aws CLI to create alarms, sns, budgets just as you would on aws UI
    -set all env variables on command line
    -make it a gp variable that is saved into your account so you don't have to revalidate everytime
    -change gitpod.yml to include the commands so aws cli will be installed/validated everytime you start up project again

# Conceptual architectural diagram

[Conceptual diagram](https://lucid.app/lucidchart/4529a44b-e846-4821-821b-7bdfd85248db/edit?viewport_loc=-540%2C-101%2C2328%2C1887%2C0_0&invitationId=inv_f07919c8-cf34-4eb4-b2a4-f7fcf1b6b17f)
[Logical diagram](https://lucid.app/lucidchart/4529a44b-e846-4821-821b-7bdfd85248db/edit?viewport_loc=-156%2C-11%2C2620%2C1887%2CB1qwpx8lbw~M&invitationId=inv_f07919c8-cf34-4eb4-b2a4-f7fcf1b6b17f)

# EventBridge Health Dashboard hook up
- what is aws health?<br/>
```AWS Health provides ongoing visibility into your resource performance and the availability of your AWS services and accounts. You can use AWS Health events to learn how service and resource changes might affect your applications running on AWS. AWS Health provides relevant and timely information to help you manage events in progress. AWS Health also helps you be aware of and to prepare for planned activities. The service delivers alerts and notifications triggered by changes in the health of AWS resources, so that you get near-instant event visibility and guidance to help accelerate troubleshooting.```<br/>
-health event are notifications aws health sends on behalf of other aws services. for example, aws health can send an event if aws IAM plans to depcrecate managed policy or aws config plans to deprecate managed rule.
-on aws console, searched aws health dashboard, clicked on pop up notification to configure amazon eventbridge
-create aws event for ec2 auto scaling instance refresh cancelled
-create event pattern called 'randomrule'
