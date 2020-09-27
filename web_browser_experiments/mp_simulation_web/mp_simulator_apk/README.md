## what is this repository for?
To run gmail under high memory pressure regime, you have to create pressure by using mp_simulator application.

This Repository contains mp_simulator apk and instruction to use it.

## How to run MP_Simulator
### Install mp_simulator
you can install this apk by running:
```
$ adb shell settings put secure install_non_market_apps 1
$ adb install -r -t mp_simulator.apk
```
Before running mp_simulator you have to root it by following instruction provided [here](https://github.com/ehsanlatif/Understanding-Mobile-QoE-Under-Low-Memory/web_browser_experiments/mp_simulation_web/root_images).
then run this application and grant root permissions

Here you can set memory pressure as MB or percentage.
We have used Nexus 5 device(2GB RAM) for our experiments and values for mp_simulator are as follows:

1. For normal pressure you have to set 25% or 250MB
2. For moderate pressure you have to set 60% or 800MB
3. for high pressure you have to set 95% or 1200MB

Then you have to set no repeate pressure by clicking radio button for repitition.

after that you have to set package name of gmail appliation in the field of app_name(in our case it was **com.google.gm**)

then open Gmail which contains an image and a text mail. and record its pss for atleast 300 sec.
 
 after sometime you have to stop mp_simulator and then get its out file at path /sdcard/result/gmail_pss.csv
