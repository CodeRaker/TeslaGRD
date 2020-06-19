# TeslaGRD 

## Disclaimer
* This project is not commercial and support is only provided on a friendly community basis. The code is developed for the Nvidia Jetson Nano, but should be able to run on any system, that meet the requirements for running the python modules, involved.
* TeslaGRD (read Tesla Guard) is undergoing continuous development and various technical aspects are still being tested.
* The biggest limitation I found, was staying within the power limits of the cars USB port. We use a lot of features and gadgets, that all draw on a single USB socket 5v@1~2Amp (5-10Watts).

## Overview
* TeslaGRD was created to solve this problem: The car doesn't notify you, when a sentry event occurs. And when you see a sentry event has occured, you have to either ignore the event, or take out the USB stick and plug it into a computer and look through the vast amounts of videos. TeslaGRD automates the process of detecting people in videos.

* TeslaGRD will notify you by email and include a GIF preview of the people it detected. The email includes a location path to the original Sentry Clip.

* The code works by monitoring the Sentry Clip folder for changes. A triggered sentry event, will eventually trigger the code, when the car moves recorded videos to the Sentry Clip folder. Those videos are then scanned for people using a neural net.

* An added benefit, is you can use TeslaGRD, as a WiFi hotspot - to download updates, watch Netflix etc. IF you wish to be more advanced, you can configure TeslaGRD to open a reverse SSH shell on your own server. This adds the capability to log in to TeslaGRD remotely and download the original video clips, while being away from the car.

Here is an image of the device in my car
![Image showing the Nvidia Jetson Nano (TeslaGuard) in the car](teslaguard-in-car.jpeg?raw=true "TeslaGuard")

## Story
### The motivation
TeslaGRD (Tesla Guard) is a one-man project, and was long story short, motivated by buying a new Tesla Model 3, parking it in a public parking space, and come back to 20 sentry events every day. Often times, videos actually showed people attempting to open the car or just hanging around it, leaning up on the car. 

At first I thought (hoped) sentry mode could send a notification upon trigger to the Tesla App. So at least I could know when, and confront the car bullies. I quickly realized, that this wasn't the case.

I also quickly realized how much time I actually spent, looking through videos everyday, sitting there with the laptop in my car, plugging in the USB and seeping through the video files.

### Figuring it out
That quickly sickened me, so I started figuring out, if there was a way to solve my problem, without the good old "just ignore it" ... I can't.

So I started mapping out, what it would actually take, to achieve my goal. This is what I wanted:

- Immediate notifications when sentry mode was triggered.
- Video's on my device, showing what happened, so I wouldn't have to run to my car, to realize it was someone just passing by.

Then I thought about, how that could be achieved technically:

- A computer in the car, with access to sentry videos.
- The computer needs power, while pretending to be a USB mass storage device. That's a lot of action for a single USB port. More on that later.
- Code that can detect people in videos. This was a new world to me, but so many AI projects, does this. So after reading and googling a lot, I ended up finding a small footprint trained neural network. Used in this project.
- An internet connection to send notifications to me. A USB LTE adapter should do the trick.
	
At this point, I just jumped straight into it, and ended up with the following components:

- 1 x Nvidia Jetson Nano
- 1 x 32GB micro SD card
- 1 x USB Huawei LTE adapter
- 1 x Data SIM card from my provider
- 1 x USB WiFi Adapter

Now I "just" needed to assemble the parts and bring them together in code.

### Assembling the parts
That was the easy part.

- Nvidia distribute their own modified Ubuntu for the Jetson series. I downloaded their latest version of the `Jetpack` and flashed it onto the 32GB micro SD card.
- The USB Huawei LTE adapter, was plug'n'play, so I could immediately start pinging google (`> ping 8.8.8.8`), when connecting the device.
- The WiFi adapter was also immediately detected by the OS (`> iwconfig`)
- I also quickly discovered, the Jetson Nano must run in low-power mode. Otherwise, it will poweroff almost instantly (or after running for a couple of minutes). Keep in mind this is because, it is solely run off USB power, in this setup. The power mode is changed using the command `> sudo /usr/sbin/nvpmodel -m 1`. More info [from Nvidia here](https://docs.nvidia.com/jetson/l4t/index.html#page/Tegra%20Linux%20Driver%20Package%20Development%20Guide/power_management_nano.html).

### Coding the functionalities



## License
Everything you find here, is free for you to use.

Do as you please.

You can show support by ordering your next car using my referral link: https://ts.la/peter62069
