# Contact-Tracing-Over-WIFI-Infrastrcture
What solution are your organization using for Contact Tracing during Covid-19? QR code scan, paper with pen or others?
Here I'd like to share some experience on leveraging WIFI Infrasturce for contact tracing.

The following snapshot is a bird view of client count **trend** in an University that really does show the impact of COVID in **2020**!
<img src="https://raw.githubusercontent.com/Ivanjin-king/Contact-Tracing-By-WIFI-Infrastrcture/master/pic/Screen%20Shot%202020-09-04%20at%208.39.13%20PM.png">
#### Timeline:
**Early of Feb:** students come back from Chrismas and new year holiday gradually<br />
**Early of March:** everything seems to be normal<br />
**End of March:** Lockdown start, students and staff have to stay at home <br />
**Early of May:** security level decrease to 2 from 3<br />
**Early of June:** Winter break/school holiday (here you could see I live in southern hemisphere)<br />

### Background Story:
We were frustrated with Cisco Prime Infrasturce which reports accummlated client count around 80k. Was it true? I often asked for this question, it's certainly impossible in user's environment. Eventually, it ends up with a finding --- TIG Solution (telegraf + Influxd _ Grafana). I was then happily playing with this solution, spending much time on it. this solution is easy to start, make you excited when having a first graph. However, it is difficult to expand and customize if you have specific needs. Harry, who challenged me why didn't we replace telegraf with Python script which is more flexible and completely owned and controlled by ourself, we can do anything we think. We were exited again and start the coding journey, we then visulized the wireless AP count,uptime,client count, wifi traffic ...... 

Until one day, we recevied an anouncement about a positive Covid person who presented at "location" between 11am - 12am. We realized we had all of the data which can help outline the users appeared there during the window.

Now, this solution has became one of most important application as the Contact tracing...

### Solution:
Python + TimescaleDB + Grafana

### Architecture:
<img src="https://raw.githubusercontent.com/Ivanjin-king/Contact-Tracing-By-WIFI-Infrastrcture/master/pic/Screen%20Shot%202020-09-04%20at%209.37.19%20PM.png">

### Best Practice:
