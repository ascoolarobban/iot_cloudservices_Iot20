<p align="center">
  <a href="Co2">
    <a href="https://ibb.co/LZ360jt"><img src="https://i.ibb.co/Js92c67/Logo.png" alt="Logo" border="0"></a>
  </a>

  <h3 align="center">Co2 Stockholm</h3>

  <p align="center">
    Fun school-project in [Emil Nildersens](https://github.com/voxic) course "IoT and Cloud services".
    An end to end solution to meassure greenhouse emissions with an arduino. Visualizing all the data on thingSpeak, 
    and getting data from YR.no into mongoDb with a heroku function writtten in python. 
    <br>
    <a href="https://reponame/issues/new?template=bug.md">Report bug</a>
    ·
    <a href="https://reponame/issues/new?template=feature.md&labels=feature">Request feature</a>
  </p>


## Table of contents
- [Use case](#Use case)
- [Solution](#solution)
- [What's included](#whats-included)
- [Wiring](#wiring)
- [Bugs and feature requests](#bugs-and-feature-requests)
- [Creators](#creators)
- [Thanks](#thanks)
- [Copyright and license](#copyright-and-license)
---
## Use Case
To meassure any toxins in the air, converting the meassurements into PPM-units and posting it to a thingSpeak to be able
to se it differate over time, this is very important to be able to do an evaluation of where we are heading when it comes to green house gas emissions
and if we are going towards the paris agreement goals. To be able to meassure locally we can quickly do an overall evaluation and a more precis prediction of if such goals are realistic and reachable 
with our current emission rate.
_However_, this project will work with toxins such as any gases like ethanol, smoke etc. Please see [MQ-2 documentation](https://www.pololu.com/file/0J309/MQ2.pdf) for more information.
And since its fully mobile it can be placed anywhere in the world.

In current state we will:
- Get readings from MQ-2 sensor.
- Post to thingSpeak.
- Get YR.no weather reports every hour.
- Push weather to mongoDB with python script on heroku server.
- Collect all data locally.


---
## Solution
###Hardware:
- Arduino nano
- MQ-2 Sensor
- 2x 5v Led
- Sim800L
- Antenna
- 3g GSM card with a data plan.
- Battery/ 5v power. 


###Messaging:
At-commands are used to send a value over GSM with a GET command to thingsPeak.

### System flowchart:
<a href="https://ibb.co/t8mr2j7"><img src="https://i.ibb.co/vZwndy7/systemskiss.png" alt="systemskiss" border="0"></a>

### ThingsPeak:
ThingSpeak is an IoT analytics platform service that allows you to aggregate, visualize and analyze live data streams in the cloud.
ThingSpeak provides instant visualizations of data posted by your devices to ThingSpeak.

thingSpeak requires a mathlab user to be able to use its services, this is a good thing, since you later on can use Matlab to perform online analysis and processing of the data as it comes in. 

<img src="https://brands.home-assistant.io/_/thingspeak/logo.png" height="50" width="250">

### MongoDB:
MongoDB Atlas, the multi-cloud application data platform, allows users to easily deploy a serverless database with minimal configuration or integrate with existing FaaS.

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/93/MongoDB_Logo.svg/2560px-MongoDB_Logo.svg.png" height="50" width="200">


## Tableau:
Run this locally as an app, its free for students.
This will help you visualize all the data and do relations to see potential patterns.
It helps in simplifying raw data in a very easily understandable format. Tableau helps create the data that can be understood by professionals at any level.

<img src="https://upload.wikimedia.org/wikipedia/commons/4/4b/Tableau_Logo.png" height="50" width="200">


## Heroku: 
Heroku is a platform as a service (PaaS) that enables developers to build, run, and operate applications entirely in the cloud

<img src="https://iconape.com/wp-content/files/xn/371066/svg/371066.svg" height="50" width="50">


## Api:
This is for lon:lat: Stockholm, Sweden.

    Yr.no
    https://api.met.no/weatherapi/locationforecast/2.0/compact.json?lat=59.3293&lon=18.0686
---
## Wiring
###Arduino nano:
-Gnd.<br>
-Vin 5v.

-A0 Mq-2 sensor.<br>
-D2 Red led.<br>
-D3 Green Led.<br>
-D7 Rx on Sim800L.<br>
-D8 Tx on Sim800L.<br>
-D9 Rst on Sim800L.<br>

####Make sure the power is at 5v, the Sim800L wont work properly otherwise.


<a href="https://ibb.co/X78TDSD"><img src="https://i.ibb.co/6HB58g8/Screenshot-2021-12-20-at-19-38-36.png" alt="Screenshot-2021-12-20-at-19-38-36" border="0"></a>

---
## What's included

```text
Yr_weatherdata/
└── 
    ├── README.me
    ├── main.py
    ├── pipfile.lock
    ├── pipfile
    ├── requirements.txt
    ├── Procfile 
    └── arduino/
        └── co2_stockholm.ino
    └── records/
        ├── mongodb
        ├── Tableau_co2
        ├── Tableau_Co2_Scatter
        └── thingSpeak
```
---
## Bugs and feature requests

Have a bug or a feature request? Send me a message to discuss it.


## Creator

    Robin Ellingsen

- [Github]("https://github.com/ascoolarobban")
- [Email]("robin@fauxdelorean.com")




## Copyright and license
None an free to use as you wish, cred is always cool, be cool.
Thanks.
