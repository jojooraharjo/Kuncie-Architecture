# Kuncie-Architecture

Here i will explain about the architecture.
The provider that i use to this project is GCP (Google Cloud Platform).
So as we can see in the architecture, that i build this architecture as simple as i can, so we can provide the application for the better experience and the application developer can develop the application easier.

First, i will explain about the GCP section.
So, as we can see, there are many GCP services that we use on this architecture. For the application server, i recommend to build 1 project in 1 Region with details as :
1. 2 Compute Engines that developers use to develop the apps. The compute Engine have detail specification like :
  - 4 Core Standar processor, here i use AMD, with 16 GB Memory
  - 500 GB persistence disk for OS, to store the apps and etc  
2. Cloud Storage, here we can save the video from the application
3. CDN Interconnect, Because the application is like "live streaming apps", so i recommend this services for this architecture because the live streaming apps consume high volume bandwith, so for the better experience, i add this to the architecture.

Besides that, we can see that i create another project in another region for the replication. Why we need this ? because this is s solution that we need for the DRC (Disaster Recovery Plan), so if something happen on our project, we still have the replication. I adding the load balancer between this project to HA our application and network.

Second, We can see on the bottom there is On-Premise DC. This is same as GCP DRC but we replicate our apps and data to On-Premise Data Center. Again and again, to secure our apps and data if something happen on the cloud, so the bussiness flow still running.

Now, the section that deliver our apps to user. I reccommend to use third apps CDN ? Why ? because, we can combine the GCP CDN and third party CDN to deliver the live stream for the best experience, prevent lagging from happening.
And the last, for the developer section, i recommend to use IAM services for security for securing and veryfying user request to the GCP environment.
But, there is another services for the environment security, which is GOOGLE CLOUD ARMOR. But, i am not including this service into the architecture because i think the service so overprice.

For the cost, there is attachment file in the "images" folder for the detail, so we can see that we spent around IDR 36,040,024.52 per month, so the first 12 month cost for this GCP environment is IDR 432.480.294.24, current GCP environment price adjusted to USD to IDR currency exchange.
