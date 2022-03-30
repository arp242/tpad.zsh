tpad.zsh is a little script to control some various things on my ThinkPad
laptop. Some of it will also work on other laptops, I guess? I don't know, I
didn't try it. Tested on ThinkPad E585 (AMD Ryzen) and x270 (Intel Kaby Lake).

What you get:

    % tpad.zsh
    Charge:   BAT0: start=40 stop=75 current=93 capacity=91 status=Not charging
              BAT1: start=40 stop=75 current=51 capacity=87 status=Discharging remaining=02:22
    CPU:      governor=powersave min_freq=400 max_freq=3900
    Fan:      speed=0 level=auto
    Thermal:  coretemp.package-id-0 = 44
              coretemp.core-1       = 44
              coretemp.core-0       = 44
              thinkpad.cpu          = 42
              acpitz                = 42
              pch_skylake           = 40
              iwlwifi_1             = 39
              nvme.2                = 34
              nvme.1                = 31
              nvme                  = 31
    Knobs:    led-keyboard = 0     led-lid      = 0
              led-micmute  = 0     led-mute     = 0
              led-power    = 0     nmi-watchdog = 0
              vm-writeback = 1500

    % tpad.zsh help
    tpad.zsh controls some ThinkPad attributes.

    Commands overview:
        help          Show help.
        status        Print status.
        save          Save current settings as a shell script.
        charge-limit  Set battery charge limits.
        cpu           Set CPU governor and frequency.
        monitor-fan   Dynamically adjust fan based on temperature.
        knob          Control various "knobs".

    Use "help <cmd>" for more help for a command, or "help all" to list the
    full help for all commands.

It's a thin layer over setting various things in `/sys`; a lot of other
scripts/programs are super-complicated and abstract far too much IMO. I used
[TLP] before, which really isn't all that *bad*, but I had some problems with it
and it was quicker to figure out how Linux works and writing my own script than
figuring out how TLP and what exactly the problem was 🤷

Requires zsh, awk, and Linux.

[TLP]: https://linrunner.de/tlp/
