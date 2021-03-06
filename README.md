just-dice-bot
=============

Hi, i just made a quick prototype to martingale on just-dice.com. Feel free to use it under GPL. If you want to donate some Satoshis: 1CDjWb7zupTfQihc6sMeDvPmUHkfeMhC83 Thanks.

HOW IT WORKS
-------------

Just-dice has no api. What is used here is remoting the website with selenium. We run selenium in an 

WHY USE YOURS?
-------------

* betting style: martingale, your own theme, whatever. 
  Let the bot do what your calculations say is right.
* RISK MANAGEMENT: most bots fail on that: you say, what your want to risk.
  e.g. bot could martingale (= win first bet no matter how many losses) for 3 rounds on 50/50
       on 4th to 30th round it could avoid big losses by losing a bit round by round. Losing sounds bad, but it allows winning more with less balance. 
* Profit: I cannot guarantee that you win, but if you do good settings your probabilities to win much are good :)
  There are examples in the config.py, and I will help you on settings if documentation doesn't help you.
* Continuity: Share some of your profits with me, and I keep updating the bot as needed and wanted.
* Support: I'm around, usually within hours, maybe a day max. Just file a ticket.

auto-tip
-------------

Here's the deal: I made the bot, which gathers you BTC. 
I'll support your as long as enough donations come in.
So if you win, the bot sends X percent (default: 1%) to me. 
Let the bot builder life :D We will have nice winnings together :)

Your part of the deal: leave the 'auto-tip' setting to 1 % (or more, what you think the bot is worth).
My part of the deal: I code, support, update, help you with the bot.
Fair? I say yes, decide yourself.


INSTALL
-------------

It's tested on python 2.7 on linux. 
I installed these:

```
aptitude install firefox xvfb xterm xserver-xephyr fvwm
xhost +
pip install selenium
pip install PyVirtualDisplay
pip install EasyProcess
```

On windows, install Python 2.7, Selenium and Firefox. Here in Detail:
```
* Python 2.7:
  Download and install http://www.python.org/ftp/python/2.7.5/python-2.7.5.msi
* Requirements to run Selenium in python:
  We need some modules in python. first: setuptools and pip:
    Install http://www.lfd.uci.edu/~gohlke/pythonlibs/2ydk2k2o/setuptools-0.9.7.win32-py2.7.exe
	Install http://www.lfd.uci.edu/~gohlke/pythonlibs/2ydk2k2o/pip-1.4.win32-py2.7.exe
Selenium: 	http://docs.seleniumhq.org/download/
  #open a cmd box:
  Start menu - search for 'cmd' - open cmd.exe
  #in cmd type (and press Return after each line):
    #change to the dir where pip.exe is in, usually:
	cd \python27\scripts
	#install selenium module for python
    pip install -U selenium
  Firefox: 	
    Install firefox from https://www.mozilla.org/en-US/firefox/fx/#desktop
* Config:
  copy config-DEFAULT.py to config.py
  edit your config.py with an text editor (your user/password, ...)
* Start:
  doubleclick on 'start.bat'
```

Please tell me if something is missing.

CONFIG
-------------

Copy config-DEFAULT.py to config.py. Then just edit some vars in config.py, they are good commented.

RUNNING
-------------

```python just-dice-bot.py```

It will show every bet with one line:
This is taken from my currently running bot:

    7:16:37: -0.00000002 LOSE (49.5%) = 0.00947565 total. session: +0.00012332 (+0.00040672(+4.3%)/d)
	7:16:41: +0.00000002 WIN  (90.0%) = 0.00947567 total. session: +0.00012334 (+0.00040672(+4.3%)/d)
    from left to right:
    * it is running for 				7 hours 16'
    * on the last bet it won 			+0.00000002 WIN
    * thi chance for this bet was		90.0%
    * the new balance is 				= 0.00947567 total
    * the total win in that session is	session: +0.00012334
    * the estimate for next 24 hours	we will win +0.00040672 which is +4.3% per day

A huge beginners error is watching at the percentage, and panic on -500% on third bet or so.
Why is that? Well, just after starting there is less data to calculate up to 24 hours.
So after starting with new settings, watch at the 'the total win in that session' (just before WIN|LOSE).
You *may* lose some raffles, but should recover based on probabilities. So do your math (or try my defaults)

CONTROL THE APP IN CONSOLE:
* Please dont close the Firefox-Window or click there. This will make the bot fail with errors.
* Instead use this commands in console:
* To stop, press 'q' and ENTER.
* Get help: press 'h' and ENTER. well, for now, these are the only two commands. more will follow.

ON ERRORS
-------------

* make sure, you have the latest version
* open your config, set visible=1
* explain, what you expect the bot to do (the error)
* explain, what you see and what the bot does
* describe your system (linux/windows, python version, ...)
* copy the stack trace from command line if any
* report on github: https://github.com/KgBC/just-dice-bot/issues

LICENSE
-------------

GPLv2 applies. Please refer to this project:
https://github.com/KgBC/just-dice-bot

DONATE (Beer)
-------------

Send your satoshi's to: 1CDjWb7zupTfQihc6sMeDvPmUHkfeMhC83
Or even better: use auto-tip feature :)
Thanks.
