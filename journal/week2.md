# Week 2 — Distributed Tracing

### For this week decided to research what exactly is observability, and how it differs from monitoring.

Did some research, landed upon IBM's website. According to them *monitoring* tells you WHEN something goes wrong.<br/>
Also watched [ashish video](https://www.youtube.com/watch?v=bOf4ITxAcXc&list=PLBfufR7vyJJ7k25byhRXJldB5AiwgNnWv&index=31&ab_channel=CloudSecurityPodcast)

while *observability* tells you what is happening, why it's happening and how to fix it.
<br/>

> Ability to understand complex system's internal state based on outputs<br>

###3 pillars of observability(according to ibm):
1. logs
2. metrics
3. traces<br>

[article](https://www.ibm.com/cloud/blog/observability-vs-monitoring)

### implementation/instrumentation
we went over 4 services on how to implement observability
1. honeycomb
2. xray
3. cloudwatch logs
4. rollbar

andrew walked us on how to install each api, how to set the gitpod.yml file to include env vars to make sure these service providers would catch any activity happening on our app.<br><br><br>

below are some of the screenshots showing log activities for all the services<br><br>
### xray
![alt text](https://github.com/mariliah/aws-bootcamp-cruddur-2023/blob/main/journal/imgs/xray.png "xray")
![alt text](https://github.com/mariliah/aws-bootcamp-cruddur-2023/blob/main/journal/imgs/xray.traces.png "cloudwatch console page, showing xray traces")
![alt text](https://github.com/mariliah/aws-bootcamp-cruddur-2023/blob/main/journal/imgs/xray-daemon.png "xray daemon installed, but not running")


### cloudwatch logs
![alt text](https://github.com/mariliah/aws-bootcamp-cruddur-2023/blob/main/journal/imgs/cloudwatch.logs.png "cloudwatch logs")

### honeycomb
![alt text](https://github.com/mariliah/aws-bootcamp-cruddur-2023/blob/main/journal/imgs/honeycomb.results.png "honeycomb")

### rollbar
--coming soon.
