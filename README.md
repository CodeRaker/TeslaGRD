# TeslaGRD Story
TeslaGRD (Tesla Guard) was long story short, motivated by buying a new car, parking it in a public parking space, and come back to 20 sentry events every day. Often times, videos actually showed people attempting to open the car or just hanging around it, leaning up on the car. 

At first I thought (hoped) Sentry Mode could send a notification upon trigger to the Tesla App. So at least I could know when, and confront the car bullies. I quickly realized, that this wasn't the case.

So I started mapping out, "what does it take" to get what I want?

- A computer in the car, with access to Sentry Clip videos.
	- The computer needs power, while pretending to be a USB mass storage device. That's a lot of action for a single USB port. More on that later.
- Code that can detect people in videos.
	- This was a new world to me, but so many AI projects, does this. So after reading and googling a lot, I ended up finding a small footprint trained neural network. Used in this project.
- An internet connection to send notifications to me.
	- A USB LTE adapter should do the trick.
	
At this point, I just jumped straight into it, and ended up with the following components:

- 1 x Nvidia Jetson Nano
- 1 x 32GB micro SD card
- 1 x USB Huawei LTE adapter
- 1 x Data SIM card from my provider
- 1 x USB WiFi Adapter
