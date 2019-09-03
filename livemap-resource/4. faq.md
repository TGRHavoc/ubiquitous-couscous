---
title: "Frequently asked questions"
weight: 4
---
# Frequently asked questions

Below you can find some frequently asked questions about the interface.

---

## How do I get blips?

Whilst in game, run the command `blips generate`.
That should be enough to generate the blips.json file.

Note: You must have the permission to run the command.
Something along the lines of

```
add_ace group.YOUR_GROUP command.blips allow ## Allow a specific group to use the blips command

add_ace identifier.YOUR_IDENTIFIER command.blips allow ## Allow a specific player to use the blips command
```

---

## I get a "dependency" error

This is known. Apparently the Node implmentation isn't up-to-par on the Linux servers for FiveM.
The best thing to do is to install the dependencies yourself and try again.

1. Make sure NodeJS and NPM are installed for your distro 
2. Navigate to the resource's location 
3. Run `npm install`
4. Remove `dependency "yarn"` from the resource file
5. Try starting again

---

## I get a YARN error

The solution to this was found by two community members, [Kevin_Gorman](https://forum.fivem.net/u/Kevin_Gorman) and [cnyncrvr](https://forum.fivem.net/u/cnyncrvr).

[Kevin_Gorman](https://forum.fivem.net/t/release-livemap/49901/811?u=havoc)

> We have just been doing some experimenting with it, to fix the issue, we had to download the new version of Yarn from the github and install it into an older version of FiveM to get it too work… If you use a new version of yarn in a new version of FiveM, it seems to just error…

[cnyncrvr](https://forum.fivem.net/t/release-livemap/49901/812?u=havoc)

> Absolutely right, reverting back to the June 1st server build seems to make everything work correctly again

