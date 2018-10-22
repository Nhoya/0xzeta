---
title: "Why Windows Over Linux Desktop"
date: 2018-10-19T13:37:43+02:00
subtitle: "My experience with Linux on desktop and why I'm moving to Windows"
tags: [ "rant", "linux", "windows" ]
---

_Yes. This is yet another rant._

**Disclaimer**: I've been a Linux user for almost 10 years, both for Desktop and Server. This blog post derives from __my__ experience with __my__ use case. If you don't agree with me and want to share your opinion feel free to send me a DM or a tweet, but please, be polite.

I'll explain all the reasons that led me to stop using Linux on Desktop in favour of Windows 10, but first you need a bit of background to better understand what's my use case.

As you can read in my _super curated and well written™_ bio I'm a [Software Developer](https://github.com/Nhoya), a Security Enthusiast (sometimes calling me Security Researcher to boost my ego) and a [CTF Player](https://jbzteam.github.io) but I'm also a young guy who loves watching movies and occasionally playing games with my friends (who doesn't?).

**Note**: With "Linux" (GNU/Linux if you are nitpicking) here I'm not referring to the Linux kernel but the entire ecosystem.

## "Linux distributions are malware-proof"

_I know that the majority of my readers are in the security field and this may sound obvious but I would like to be as comprehensive as possible, giving nothing for granted._

Linux **is not** malware-proof. This is a myth that should be busted once and for all, specially if we are talking about Linux Desktop.
The real reason why you see less malware campaigns targeting Linux is because the Linux Desktop users are fewer and usually less valuable than Windows ones. Although this seems a good thing I have to kill your hopes: this is just an illusion. Thinking to be safe just because less people may attack your system is like leaving your safe unlocked just because you trust people in your neighborhood (spoiler: it's a bad choice).

## The new CoC is sh*t

Recently a [new Code of Conduct](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=8a104f8b5867c682d994ffa7a74093c54469c11f) was introduced in the Kernel mainline replacing the old [Code of Conflict](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/tree/Documentation/CodeOfConflict?id=ddbd2b7ad99a418c60397901a0f3c997d030c65e) raising a lot of controversy. If you live under a rock here is the TL;DR of the drama:

- The new Code of Conduct is based on the [Contributor Covenant](https://www.contributor-covenant.org/) written by Coraline Ada Ehmke.
- Although the Contributor Covenant defines the rules for a good community, it was abused multiple times by its own creator to remove people with a different view from his/her own from other projects. You can find more references [here](https://itsfoss.com/linux-code-of-conduct/), [here](https://lulz.com/linux-devs-threaten-killswitch-coc-controversy-1252/) [and here](https://linustechtips.com/main/topic/974038-why-the-linux-coc-is-bad/).
- Starting from the day 0 after the release of the CoC one of the top Kernel contributors Ted Tso was [accused to be a "rape apologist"](https://twitter.com/_sagesharp_/status/1042769399596437504)
- [The Contributor Covenant author is strongly against meritocracy](https://postmeritocracy.org/)

I'm not directly part of the Linux development community but this will affect all the users indirectly, losing a good contributor is always a bad thing. Also this CoC means introducing a political view inside the development process of a software that _IMHO_ should never be influenced by that. You, as a contributor, should be judged by you code quality not your personal life (I think that [ReiserFS](https://en.wikipedia.org/wiki/Hans_Reiser) is one of the best examples).

## "Microsoft is spying on us!"

Proofs? And please don't come answer to that with the old [PRISM](https://www.theguardian.com/world/2013/jun/06/us-tech-giants-nsa-data) case.

I always see people talking about telemetry with the misconception that if telemetry is active then someone will spy on us. That's totally wrong. Telemetry is just a tool used by developers to monitor their software use cases and crash reports. Those are (_usually_) anonymized and then sent to a server. Telemetry is super important to give the final user the best experience (more info you have on how your product is used and the errors it throws and better the improvements will be), also after the GDPR Windows allows EU citizens to select what kind of data you want to send to Microsoft.

With the April 2018 update thanks to the [Diagnostic Data Viewer](https://www.microsoft.com/en-us/p/diagnostic-data-viewer/9n8wtrrsq8f7?activetab=pivot%3aoverviewtab) you can have a complete summary of what data is sent and if you are still not happy there is the possibility to totally shout down the telemetry by working a bit with registry keys, or by using [this](https://github.com/10se1ucgo/DisableWinTracking) tool. Also, Microsoft published a [detailed list of endpoints](https://docs.microsoft.com/en-us/windows/privacy/manage-windows-endpoints), so if you have time to spend you can block them with your firewall.

_"But this doesn't prove that there aren't backdoors!22!"!£"_
Sure, it doesn't, but can you prove it does? Lately I see many people saying that vulnerabilities in Windows are actually backdoors put there intentionally but without any proof. If you consider every Windows bug an intentional vulnerability then you should do the same with Shellshock for example or the [recently discovered libssh flaw](https://www.zdnet.com/article/security-flaw-in-libssh-leaves-thousands-of-servers-at-risk-of-hijacking/) or, maybe... you are assuming that since they are open source, [is impossible that someone will put a backdoor on them](https://lwn.net/Articles/57135/)?

## Xorg and Wayland

Xorg is the 2004 implementation of X11 and is currently the most popular graphic server used by Linux distributions. It comes with *tons* of issues that undermine usability and security. [Here](https://blog.martin-graesslin.com/blog/2015/01/why-screen-lockers-on-x11-cannot-be-secure/) and [here](https://blog.martin-graesslin.com/blog/2015/11/looking-at-the-security-of-plasmawayland/), for example, you can find some blogposts from Martin Graesslin, a KDE developer, talking about screenlock security issues caused by X11 that, for obvious reasons, need a rewrite of the core components to be fixed (spoiler: this will not happen) or tricky workarounds from DE developers. The real solution is to migrate to an alternative. The one available is [Wayland](https://wayland.freedesktop.org/), but it's not ready for production use yet.

So, assuming that you don't want to spend time sandboxing everything on your system, out of the box you can choose between a broken protocol or one not yet ready.

## The issue with distributions system

I like the fact that everyone is able to run its own distribution. It's a way to play and understand how the internals work.

The issue comes when there are N *widely used* distributions that are, after all, just the same thing with major issues derived from inexperience or lacks by the development team. You don't trust me?

- [Deepin had unpatched vulnerabilities that lead to privilege escalation.](https://www.reddit.com/r/linux/comments/58zyqi/deepin_os_gorgeous_de_but_0_security/)

- [Mint webside was hacked and the ISO was changed with a malicious one.](https://www.zdnet.com/article/hacker-hundreds-were-tricked-into-installing-linux-mint-backdoor/)

- [Antergos website was hacked, they had to pay for an external review to understand what happen, still no official statement released. Really professional.](https://forum.antergos.com/topic/10653/phishing-popup-in-cnchi-followed-by-crash)

- [Kali Linux had multiple old and vulnerable packages in the repository](https://twitter.com/hashtag/monthofkalicrashes?src=hash)

- [Gentoo GitHub repo was backdoored due to Password Reuse](https://www.gentoo.org/news/2018/06/28/Github-gentoo-org-hacked.html)

- [Project0 accuses sluggish kernel patching of Debian and Ubuntu for threatening users security](https://www.zdnet.com/article/google-project-zero-to-linux-distros-your-sluggish-kernel-patching-puts-users-at-risk/)

Of course, those are things that can happen to everyone, except that for the case of Antergos and Deepin having a security team would be great.

For Kali the problem is different since it's run by a security company for security people, and a lack of security here is probably relative to a lack of attention in packages selection.


## "Everyone can read the source code of Linux so it's more secure"

Really? Explain me this then:

- [Shellshock](https://en.wikipedia.org/wiki/Shellshock_(software_bug))
- [Mutagen Astronomy](https://www.theregister.co.uk/2018/09/27/mutagen_astronomy_linux/)
- [CVE-2018-8781](https://securityboulevard.com/2018/05/cve-2018-8781-8-year-old-linux-kernel-bug-discovered/)

All of them are [1-9]+-years-old vulnerabilities discovered in the Linux Kernel or in well-known and commonly used components. This just proves that `"more people" != "more secure"` for two simple reasons:

- Closed source projects, let's say the NT kernel to stay in topic, are also inspected by multiple teams composed by highly qualified people. The fact that you are not one of them doesn't mean that their review process is not good or that you are more qualified than them.

- The fact that the source is easily available doesn't necessarily imply that all the users will read it or have the time and the knowledge to do it. This is easily demonstrable comparing the size of kernel community with all the users of Linux. And I'm pretty sure that all the people reading this post are Kernel top contributors.. right?

## Interesting Security Features in Windows 10

With Windows 10 Microsoft did bigger improvements around OS security. One of the more interesting for me are:

### [VBS](https://docs.microsoft.com/en-us/windows-hardware/design/device-experiences/oem-vbs)

![VBS](https://cloudblogs.microsoft.com/uploads/prod/2018/06/VBS-secure-memory-enclave.png)

The TL;DR is that Hyper-V will create a secure enclave that protect critical processes from code injection and unauthorized read access.

If you need more info you can read [here](https://techcommunity.microsoft.com/t5/Windows-Insider-Program/Virtualization-Based-Security-VBS-and-Hypervisor-Enforced-Code/td-p/240571), [here](https://blogs.technet.microsoft.com/ash/2016/03/02/windows-10-device-guard-and-credential-guard-demystified/) and [here](https://cloudblogs.microsoft.com/microsoftsecure/2018/06/05/virtualization-based-security-vbs-memory-enclaves-data-protection-through-isolation/)

### [Controlled Folder access](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-exploit-guard/enable-controlled-folders-exploit-guard) 

With this feature you can specify which application can access a specific directory preventing malicious software (a ransomware for example) to edit/delete/encrypt/read the files inside it.

### [Secure Boot](https://docs.microsoft.com/en-us/windows-hardware/design/device-experiences/oem-secure-boot)

Secure Boot prevents attacks on the bootloader verifying its signature. If it's verified then it will be loaded, otherwise it will throw an error. This is surely a great security feature that prevents malware from getting persistence on /boot. Unfortunately this had the side effect of blocking the execution of GRUB, preventing the installation of an alternative operating system. The maintainers of the distributions are working on it and currently Secure boot is supported (out of the box) by:

- [Red Hat](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/system_administrators_guide/sec-uefi_secure_boot)
- [Fedora](https://fedoraproject.org/wiki/Secureboot)
- [Open Suse](https://en.opensuse.org/openSUSE:UEFI) (experimental)
- [Ubuntu](https://wiki.ubuntu.com/UEFI/SecureBoot)
- [CentOS](https://blog.centos.org/2018/08/secureboot-rolling-out-new-shim-pkgs-for-centos-7-5-1804-in-cr-repository-asking-for-testers-feedback/)
- [Debian maybe in 2019 :)](https://www.phoronix.com/scan.php?page=news_item&px=Debian-UEFI-SecureBoot-2018)

Those are things that, without any doubt, can be archived under Linux too, but you need more time and skills: DIY is not always the solution, specially if you don't have time or skills.

[Qubes](https://www.qubes-os.org/), for example, has a sandbox-based design by default but lacks in usability and its [system requirements](https://www.qubes-os.org/news/2016/09/02/4-0-minimum-requirements-3-2-extended-support/) are higher compared to other solutions

What I love about Windows 10 is that all those features are just plug n' play or to be enabled with a dead-simple to use checkbox.

## Conclusion

Please, don't misunderstand me, everyone is free to install whatever they like. In my experience Linux was a nice training field: I learned a lot about OS internals, networking, how to manage a system and all the best practices about system maintenance but with knowledge comes criticism. I initially defended blindly the Linux Ecosystem, but then I started to find issues regarding security and usability.

I will keep developing my software for Linux and to use Linux on my servers (unless I will decide to migrate to BSD, but I'm not yet into masochism), I will just stop using it as my Desktop daily driver. If you are curious on how I will build my ecosystem I'll publish a blog post soon™ explaining the details.

_Remember: all that glitters is not free software :P_
