# TeslaGRD 
## Story
TeslaGRD (Tesla Guard) is a one-man project, and was long story short, motivated by buying a new Tesla Model 3, parking it in a public parking space, and come back to 20 sentry events every day. Often times, videos actually showed people attempting to open the car or just hanging around it, leaning up on the car. 

At first I thought (hoped) sentry mode could send a notification upon trigger to the Tesla App. So at least I could know when, and confront the car bullies. I quickly realized, that this wasn't the case.

I also quickly realized how much time I actually spent, looking through videos everyday, sitting there with the laptop in my car, plugging in the USB and seeping through the video files.

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

Now I "just" needed to code it all.

## License
Everything you find here, is free for you to use.

Do as you please.

You can show support by ordering your next car using my referral link: https://ts.la/peter62069
