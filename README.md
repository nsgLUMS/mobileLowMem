# Mobile Web Browsing Under Memory Pressure
## About Repository
In this work, we analyze how device memory usage affects Web browsing performance. We quantify the memory footprint of popular Web pages over differ-ent mobile devices, mobile browsers, and Android versions, analyze the induced memory distribution across different browser com-ponents (e.g., JavaScript engine and compositor), investigate how performance gets impacted under memory pressure and proposeoptimizations to reduce the memory footprint of Web browsing.

In this repository, we have provided all the tools, scripts, and data used in the paper along with installation guidelines. For majority of our experiments, we used a 2GB RAM Nexus 5 device, which has a quad-core processor. Use of such a mid-range device is commmon in developing countries.
  
To perform experiments involving tracking the memory footprint of Web browsing, we flashed userdebug build (built from Google's repository) to the device. Moreover, for inducing memory pressure using a custom application we built, we rooted the device. We tracked the memory footprint using the Telemetry; a performance benchmarking tool for Chrome. To obtain webpage size and more detailed statistics about Web pages, we used WebPageTest. For inducing memory pressure, we designed and developed a native Android application using SDK and NDK. For tracking PSS of applications, we also developed an Android application.

