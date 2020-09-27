## What is this repository for?
This repository contains synthetic webpages along with the images which we have used to extrapolate contibution of images on the wb page load time and memory footprint and for suggestions to optimize web pagesby using specific format
### Synthetic Pages
./synthetic_pages/ directory contains web pages for differnt image formates, 16 images for each page.
We have run these webpages on telemtry same as mentioned in the parent directory.
### How to run
Download these pages to your local directory and then a python server in the same directory as:
```
$ python –m SimpleHTTPServer
```
Then you just have to set its url to the telemetry file. and then run its benchmark as:
```terminal
$ ./record_wpr --browser=android-chromium  memory_top_10_mobile
```
then you have to reply these files to get real picture of memory footprint as:
```terminal
$ ./run_benchmark --browser=android-chromium --pageset-repeat=15 memory.top10.mobile --output-format=csv
```
