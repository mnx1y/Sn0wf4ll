# Sn0wF4ll

README FILE FROM JAKEASHACKS 

If you are having trouble with Electra1131 but still want to run tweaks:
consider using Sn0wF4ll Toolkit

Sn0wF4ll2.0: Electra Toolkit but for ios 11.3.1

manually install tweaks to: /var/containers/Bundle/tweaksupport/Library
Just like in the electra betas!

Patch deb files like with jakeajames rootlessjb 

Link to tweak files for those that don't know how to patch them using the Patcher:
https://mega.nz/#!1yIBBYaL!PqWngJOIWva2zQxPjem8ZciNXM_1HXmean7uSeiLO68

Should have increased success rate like with original Sn0wF4ll jailbreak 
ENJOY :)

iOS 11.0-11.3.1 jailbreak. Gets root, escapes sandbox, patches codesign (userland only), bind shell, nvram unlock (from Electra), host_get_special_port 4 (from Electra), code injection (from Electra; injects its amfid patch after using QiLin's since it's way better), ~~SSH (dropbear)~~

I think at this point this can be called a jailbreak, a developer-only one but with a small little feature: everything is done inside the app's bundle (except /var/dropbear & /var/profile) and nothing outside is touched. This makes it safe to use, without the requirement of full root read and write (although it is enabled on 11.0-11.2.6) and at the same time makes it not conflict with other jailbreaks in any way.


Includes ~~TWO~~ a root shell~~s~~ :)

~~First is via dropbear (SSH) and the other via netcat if dropbear for some reason  doesn't work or you prefer it?.~~ **Dropbear not supported yet because empty_list seems to also have file descriptor leaks. Unless those are fixed dropbear will NOT work**

You can drop any binaries in the iosbinpack64 directory. All binaries must have at least these two entitlements:

    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
    <dict>
        <key>platform-application</key>
        <true/>
        <key>com.apple.private.security.container-required</key>
        <false/>
    </dict>
    </plist>

LaunchDaemons are also supported, you can drop their plists in the iosbinpack64/LaunchDaemons directory and they'll get loaded on each run of the app. Type REPLACE_ME when you want to put the absolute path of iosbinpack64, like in the example provided.

Future plans include: getting rid of QiLin and implementing everything i need open-source, (already made progress!), fix remounting for 11.3.x (I guess I have no other choice rather than wait for QiLin/LiberiOS/Electra)

Credits: Uses jakeashacks empty_list fork and makes use of files from LycaJB and other jailbreaks not publicly released Thanks to Ian Beer for empty_list and mach_portal, Jonathan Levin for amfid patch, Jonathan Seals for find_kernel_base, Electra Team (especially stek29) and PsychoTea (@iBSparkes), 1GamerDev for reliability improvements
