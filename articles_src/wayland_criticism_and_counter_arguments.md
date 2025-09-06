# wayland criticism and counter arguments

## argument

counter argument
## why migrate to wayland:

https://www.cbtnuggets.com/blog/technology/devops/wayland-vs-xorg-wayland-replace-xorg

applications need to communicate with Xorg before the compositor can create the window for the application. This workflow is a tried-and-true method but can be slow, especially by today’s standards. During remote connections, latency issues can be noticeable to the end user.

## Are there other resources for learning about wayland

see the wayland website, mailing list , irc channel, and faq

## They should not have rewritten it from scratch, they should have improved x11

it is not a rewrite, a lot of things from X has moved to the kernel (memory management, command scheduling, mode setting) or libraries (cairo, pixman, freetype, fontconfig, pango, etc) and there is very little left that has to happen in a central server process.

Also keep in mind that even if there was a decision to work on X it would probably cause issues like others big transitions like from KDE 3 to KDE 4
Also you want to remove stuff you don’t need, breaking the 30 year old backward compatibility , or writing an implementation with a language that is arguably better/safer like rust.

## progress on wayland was slow

This is analogical to an Api rewrite, gtk 3 was released 6 years ago and still haven't finished porting (this is about the same time wayland 1.0 stable protocol was released), This is a classic example of "mediocre is the enemy of the good" and reaching a 100 percent market share is going to take a while (It probably has a decent market share now because it is the default on several distros).

## you have to implement everything from scratch

see wlroots and smithay, also multiple implementations is a good thing


## wayland does not a a screenshot protocol:

wlroots has a screenshot protocol, so that will give you support for wlroots based wayland compositors like sway/way-cooler (they are both suppose to migrate to wlroots soon).
Also it looks like xdg-desktop-portal has a screenshot API,  gimp is using it recently. that means you can create a flatpak package for your app and use it. Maybe in the future even non flatpak apps could use the Api (or maybe they can now if xdg-desktop-portal is installed, I am not sure).

There is pipwire, also a new protocol could be developed in the future

# wayland has been in development since 2008 and is still not ready:

It’s advantages are prominent in embedded scenarios where it is used a lot, desktop development is started latter, I think I good start for that is the start of the development of wlroots (april 2017) and now you hear at least some people say it works for them better then X11.

Also X11 wasn’t great for a very long time, iirc until about 2021 I was still getting screen tearing when watching videos.
See : https://www.linux-magazine.com/Online/Features/Is-Wayland-the-New-X
Although most people have settled into thinking of Wayland as a work in progress, the project has already shipped on a number of embedded products, phones, and tablets. “For these products, where you control the entire stack top-to-bottom, it’s very easy to use the Wayland core protocol, and build your own specific UI on top with custom extensions.”


## There is still fragmentation, for example if a protocol needs to be implemented it needs to be implemented for multiple implementation (KDE,GNOME,smithay,wlroots):

That’s a common approach, for example for HTML,C++ or posix you can have multiple implementations, not all of them implemented completely .

I think it is good because competition is extremely important, it’s not about how much resources you have but how efficiently you use them, take for example AMD that started taking business from intel despite having one tenth the revenue at the end of 2019. If protocols like HTML and POSIX did not exist we would not get Linux and firefox and other open source browsers.

## Wayland offloads all the complexity onto the compositor which has to do everything itself.

there is the [wayland  protocols](https://gitlab.freedesktop.org/wayland/wayland-protocols) repository , if you would look at it's [governance](https://gitlab.freedesktop.org/wayland/wayland-protocols/-/blob/main/GOVERNANCE.md?ref_type=heads) you will see it is basically where wayland implementations can work on common standards , and implementations can have their own protocols that other implementations can implement before they are standardized (e.g. [kde protocols](https://github.com/KDE/plasma-wayland-protocols) , [wlroots protocols](https://gitlab.freedesktop.org/wlroots/wlr-protocols) , [cosmic protocols](https://github.com/pop-os/cosmic-protocols)).

And then you can use a library like smithay or wlroots.
