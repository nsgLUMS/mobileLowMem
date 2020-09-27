## What is this Repository for?
This repository contains path to download UDB images for the devices under our experimental setup.
### METHOD 1
We have compiled UDB images by following instructions as decribed below. We have provided path to drive containing images here:
1. UDB for [Nexus 5 OS Ver 6.0.1](https://pern-my.sharepoint.com/:f:/g/personal/20100262_lums_edu_pk/EiAuyjMNPhBCr67vz_pVV2wB4x8dMlTvTqn0NszQgL4wqw?e=LhnE0Q)
2. UDB for [Nexus 5x OS Ver 8.0.0](https://pern-my.sharepoint.com/:f:/g/personal/20100262_lums_edu_pk/EiAuyjMNPhBCr67vz_pVV2wB4x8dMlTvTqn0NszQgL4wqw?e=LhnE0Q)
3. UDB for [Nexus 6p OS Ver 8.0.0](https://pern-my.sharepoint.com/:f:/g/personal/20100262_lums_edu_pk/EiAuyjMNPhBCr67vz_pVV2wB4x8dMlTvTqn0NszQgL4wqw?e=LhnE0Q)
4. UDB for [Nexus 6p OS Ver 8.1.0](https://pern-my.sharepoint.com/:f:/g/personal/20100262_lums_edu_pk/EiAuyjMNPhBCr67vz_pVV2wB4x8dMlTvTqn0NszQgL4wqw?e=LhnE0Q)
 
### METHOD 2
#### Instruction to build UDB
Follow steps one by one:

1. To start off, read the hardware and software requirements mentioned at this [link](https://source.android.com/setup/build/requirements) (till OS and JDK). 
2. Next, go to [Establishing a Build Environment](https://source.android.com/setup/build/initializing.html).
3. Open the link **[Build Numbers](https://source.android.com/setup/start/build-numbers.html)** under Choosing a branch.
	1. Here, you need to find the right build for your device. 
	2. It is advised to use the same build version that your phone currently has or the latest build available.
	3. In the list for your device. To find out your phone's current build, go to Settings>About Phone>Build Number.
		* For example, I used M4B30Z android-6.0.1_r77 for Nexus 5. It is the latest build available for Nexus 5 and the phone previously had the same build.

4. Now you need to install JDK on your computer. 
	1. Install openjdk 7 for ubuntu 16.04 (on that laptop). The instructions mention jdk 8 which did not work for me.
5. Move onto the next step i.e., [Downloading the Source](https://source.android.com/setup/build/downloading).
	1. Simply follow the instructions given at this link, replacing the android version with yours when doing repo init, only follow till repo sync

6. Next, go to [Preparing to Build](https://source.android.com/setup/build/building).
7. Start following the commands from the heading Clean up
```
$ make clobber
$ . build/envsetup.sh
$ lunch aosp_hammerhead-userdebug
```
	(hammerhead is the code for nexus 5, you can find the codes for other devices here: 

	https://source.android.com/setup/start/build-numbers.html#source-code-tags-and-builds
```
$ make -j4
```
(do not use more threads as it results in failure)

8. If you face a clang error at this point, make the following change to build/Android.common_build.mk file:
	* Set the ART_HOST_CLANG flag to false by default

**Next, to flash the device go to the following [link](https://source.android.com/setup/build/running.html#flashing-a-device)**

### Follow the instructions here to put the phone in fastboot mode:
Use sudo with the command fastboot flashall -w if you are not already root

Here, you may encounter an error that the output directory is not set

To resolve it, set the variable **ANDROID_PRODUCT_OUT** to the absolute path till out/target/product/your build code directory (e.g. hammerhead)

Start up the device and you will have a user-debug build!
