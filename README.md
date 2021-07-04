# Tech-Conference

**Tech-Conference** allows attendees to register for an upcoming conference. Administrators can also view the list of attendees and notify all attendees via a personalized email message.

## User Stories

The following **required** user stories are complete:

- [x] The web application is not scalable to handle user load at peak
- [x] When the admin sends out notifications, it's currently taking a long time because it's looping through all attendees, resulting in some HTTP timeout exceptions
- [x] The current architecture is not cost-effective

The following **technical** specification are implemented:

- [x] Azure App Service
- [x] Azure Functions
- [x] Azure Web Apps
- [x] Azure PostgresDB 
- [x] Azure Queue

## Architecture
<p align="center">
<img src="/screenshots/techconf.jpg" width="500px">
</p>

## Discussion
- Intro: 
   - This is the barebone and minimal price tag for services as I am trying to use resources frugally with a limited cusomters base. 
- Risk: 
   - There is no advance logging mechanism so resiliency is the traded-off
- Architecure Explaination:
   - A single web server is good enough for a squential user-access fashion
   - Moving task consuming too much time to a background job mechanism and jobs-worker queue pattern
   - Moving the whole app to Azure will allow the adminnistrators to scale the app base on their need. In this project, I scale it back to the minimum as there is only one user. 

## Monthly Cost Analysis
- Scenario: TechConf has the siiiar stat to https://azuresummit.live/ 
- Up front: $0
- Link: 
   - Azure Pricing Calculator: https://azure.com/e/fb6cccd2dbb449e5a50b2aae50c5ce61 
   - Theorical website visiting stat: https://www.similarweb.com/website/reinvent.awsevents.com/#overview 

| Azure Resource | Service Tier | Monthly Cost |
| ------------ | ------------ | ------------ |
| *Azure Postgres Database* | Basic Tier | $32.82 |
| *Azure Service Bus* | Basic tier | $0.05 |
| *Storage Account* | Queue Storage | $0.05 |
| *App Service* | Consumption tier | $13.14 |
| *Azure Function* | Basic Tier | $0.00 |
| *SendGrid* | Free Tier | $0.00 |

<p align="center">
<img src="/screenshots/aws-visit.png" width="500px">
<img src="/screenshots/price.png" width="500px">
</p>

## Screenshots
<p align="center">
<img src="/screenshots/1-1-1.png" width="500px">
<img src="/screenshots/1-1-2.png" width="500px">
<img src="/screenshots/1-2-1.png" width="500px">
<img src="/screenshots/1-2-2.png" width="500px">
<img src="/screenshots/2-1.png" width="500px">
<img src="/screenshots/2-2.png" width="500px">
<img src="/screenshots/3-1-1.png" width="500px">
<img src="/screenshots/3-1-2.png" width="500px">
<img src="/screenshots/3-2-1.png" width="500px">
<img src="/screenshots/3-2-2.png" width="500px">
<img src="/screenshots/3-2-3.png" width="500px">
</p>

## Notes

All the URI/URL and keys in the app are safe for public as all the resources are deleted.

## License

Copyright [2021] [Huy Duc Vo]

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
