eac-check.sh: Easy Anti-Cheat Linux v2 requirements checker for Ubuntu (and probably any debian based distro)

Will my Ubuntu PC run Easy Anti-Cheat Linux v2? This little bash script tells you before you waste an evening trying to launch Fortnite, which, according to Epic, will be the first game to use this anti-cheat system. xD

Epic Games announced EAC Linux v2 on 2026-10-14 (https://onlineservices.epicgames.com/news/introducing-easy-anti-cheat-linux-v2). It comes with a list of 8 system requirements
(Secure Boot, TPM 2.0, signed kernel and modules, and more). Checking all of that by hand is a pain, so I made a script that does it for you.

What it checks

It goes through the 8 requirements from Epic's announcement, including:

    Secure Boot enabled
    TPM 2.0 present
    Signed kernel
    Kernel module signing (and who's allowed to sign them)
    kexec restrictions
    ...and the rest of the list from the announcement

Each check comes back as OK, BAD or WARN, and you get a short summary at the end.

Is it safe?    0_0

It's read-only. It only reads your system state and doesn't change, install or delete anything. It's one bash file, so read it before running it (you should do that with ANY script that asks for sudo).

Usage:  
   
    sudo bash eac-checker-en.sh

it also runs without sudo, but then it can't read the kernel signature, so will show a warning.

Tested on my PC running Ubuntu Budgie 24.04 and my notebook running Kubuntu 26.04

It should probably work on other Ubuntu flavors and Debian-based distros (Linux Mint, Pop!_OS, Zorin...). If you try it somewhere else, tell me, I'd love to see them.


This is an approximate check. The real verification happens when EAC starts inside a protected game, and Epic says the requirements MAY change. If the script says OK and the easy anticheat says nahh!!, blame Epic, not me ;P


I don't know how, but hopefully xone, xpadneo (Xbox controllers) and the Nvidia drivers work somehow ^_^ (now require secure boot off or secure boot on +MOK)

Since the script is read-only, it cannot damage your operating system. The script checks the current state and provides suggestions; please be aware that these suggestions *can* affect your system, so do not follow them unless you are 100% sure of what you are doing.
Seriously—the suggestions provided by the script could potentially break your system, so please make sure you know what you are doing.

