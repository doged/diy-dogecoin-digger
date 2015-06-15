# Do-It-Yourself ƊogecoinDark Digger ([DƊD](https://bit.ly/diy-doge))

 
Start digging in your own back yard!

![DogecoinDark](http://dogecoindark.net/img/logo-dark@2x.png)

## CPU Mining for the Masses!

This project is intended to get users up and running on a CPU miner in
a **fast, secure, and friendly way**. First, that means providing
pre-configured installers that can be automatically run from the command
line with little fuss and no guesswork. It also means validating all the
provided binaries and scripts with md5sums and keeping everything on
SSL for download and install.

Mass individual mining is important to the future of DogecoinDark, if you can spare
the cycles and electrons. 

## TL;DR!

Oh, I get it, you're the sort who doesn't care about details. You just want
to be helpful. I respect that. After all, who has the time? Here's what you
need to do to start digging some DogecoinDark with a P2P pool and help protect
the DogecoinDark network, right now.

### Step One: Get a Wallet

If you have a wallet, great, just skip ahead to the [Linux/OSX method](https://github.com/doged/diy-dogecoin-digger#d%C3%90d-on-linux-and-osx)
or the [Windows procedure](https://github.com/doged/diy-dogecoin-digger#d%C3%90d-on-microsoft-windows).


If you don't have a Dogecoin wallet yet, then might I suggest going to the DogecoinDark main website,
(http://DogecoinDark.net) and downloading one for whatever platform you use!

There are many other choices in your quest for a DogecoinDark address. Feel free
to shop around.

### Step Two: Start digging already!

Now that you have a wallet, pick your operating system, and follow the
very simple instructions to get started. You can choose Linux/OSX,
Windows, Raspbian (soon), or Android (some day).

## DƊD on Linux and OSX

![Linux](http://i.imgur.com/iEMgx2U.png) ![OSX](http://i.imgur.com/Mitgpaf.png)

The Linux and OSX version of the bootstrap script, `ddd.sh`,
requires curl, a small application useful for command-line file transfers.
Most of these systems already have it. DƊD also assumes an Intel-based 64-bit
for OSX or Linux, or 32-bit Linux (for now). All MacBooks manufactured since
late 2006 have 64-bit CPUs, but if you're not sure about yours,
[here's how to tell](http://support.apple.com/kb/HT3696).

So, you should be set out of the box. Just open a Terminal window, and type:

````
curl -3sSL http://bit.ly/1Gov69j > ddd.sh && bash ddd.sh
````

#### Avoiding me ripping you off (Posix)

The above will get you started mining right away, but you'll be mining
to **my** Dogecoin address, not yours. While this seems like a perfectly
reasonable default to **me**, you might not agree. That's fair. You can
keep your earnings by editing the `p2p.conf` file first. Here's how:

````
\curl -3sSLO https://raw.githubusercontent.com/doged/diy-dogecoindark-digger/master/bin/ddd.sh
\curl -3sSLO https://raw.githubusercontent.com/doged/diy-dogecoindark-digger/master/conf/p2p.conf
sed -i s/DPNC2H2pYUCSebQ992GyeRTRuWw3hCTBwD/YOUR-DOGECOINDARK-WALLET-ADDRESS/ p2p.conf
bash ./ddd.sh
````

Just copy and paste that into your Terminal window. It should work out.

#### Non-Debian derived systems

This probably works on other Linuces. Let's keep a list of tested
operating systems on the
[wiki](https://github.com/doged/diy-dogecoindark-digger/wiki/_pages)! That'll
be fun.

## DƊD on Microsoft Windows

![Windows](http://i.imgur.com/CVDmPUk.jpg)

Sadly, Windows kind of fails at both having an easy command-line interface
for file transfers, and a scriptable way to unzip files. To take care of that,
you *may* need to manually download a couple things if you haven't done something
like this before.

  * [cURL](https://github.com/doged/diy-dogecoindark-digger/raw/master/bin/curl-7.35.0-win32-local-fix1.msi) - a crazy useful, multi-protocol data transfer utility. Free and open source.
  * [7zip](https://github.com/doged/diy-dogecoindark-digger/raw/master/bin/7z920.msi) - a stunningly handy archive manager. Free and open source.

These are nice to have around anyway so you'll be happy you have them. You may need adminstrative
permissions to install one or both, though, depending on your local security settings.
Ask an adult first!

Once you have those installed, you can pretend like you're on Linux or OSX, and run:

````
curl -3sSL http://bit.ly/1FXDBFZ -o ddd.bat && ddd.bat
````

Someday, we'll have a nice one-click experince for our Microshibe friends. Also,
since it's Windows, 32-bit applications still will work on 64-bit hardware. That said,
there's an [issue](https://github.com/doged/diy-dogecoindark-digger/issue)
open to address this and get you on the more correct platform with some auto-detection.

#### Avoiding me ripping you off (Windows)

The above will get you started mining right away, but you'll be mining
to **my** DogecoinDark address, not yours. While this seems like a perfectly
reasonable default to **me**, you might not agree. That's fair. You can
keep your earnings by editing the `p2p.conf` file first. Here's how.

First, get the p2p.conf and the `ddd.bat` batch file:

````
curl -3sSLO https://raw.githubusercontent.com/doged/diy-dogecoindark-digger/master/bin/ddd.bat
curl -3sSLO https://raw.githubusercontent.com/doged/diy-dogecoindark-digger/master/conf/p2p.conf
````

Edit `p2p.conf` with your favorite editor and replace my "user" (really my wallet address)
with yours. Be careful to save it as a `p2p.conf` and not `p2p.conf.txt` -- Windows is
tricky like that.

Now you're off to the races:

````
ddd.bat
````

# The Long and Kind of Boring Story

So if you've read this far, you may be wondering why I want loads and
loads of people to start mining on their low-end, non-optimized, barely
adequate gear. I mean, that's just going to kick up the difficulty rate
and cost everyone a bunch of electricity, right?

Well... not so fast. There are real, practical reasons to do this.
If you're used to the profit motives often talked about in cryptocurrency
circles, you may want to avert your eyes, since I'm going to talk about
the social good you can perform by sparing a little CPU power.

## Initial musings

For a while, I've been worrying myself over the whole fragility of the
peer-to-peer network that DogecoinDark (and all other cryptocurrencies)
rely on to operate. There was a mild freakout in March of 2014 about
how [Wafflepool had accumulated over 40% of the total hashing power of the network](http://www.reddit.com/r/dogecoin/comments/210fwh/wafflepool_is_almost_in_position_for_51_attack_on/).

The problem is twofold:

  * Multipools tend to mine DogecoinDark quickly, then turn around and trade the DOGED for BTC.

These folks don't hold the DOGED, they don't spend the DOGED, and they don't trade for
goods and services with DOGED. They mine, dump, and mine again. Of course, it's perfectly
reasonable to do this on an individual basis. You just ending up sucking the life out of the
coins you mine for your short-term gain. Shrug, right?

  * Pools (multi- or not) tend to concentrate hashing power into very few hands (and machines)

All of the security of a peer-to-peer, distributed currency is predicated on the fact
that it's actually **peer-to-peer**. This is not the case today. You can usually eyeball
how the hashrate is divided right now by taking a look at [RapidHash's chart](https://pools.rapidhash.net/).
In late March, 2014, 10 pools are identified as controlling over **60%** of the hashrate.

Are the controllers of these pools all going to suddenly start colluding, like so many
monocoled and cigar-smoking [robber barons](https://en.wikipedia.org/wiki/Robber_baron_(industrialist))?
Probably not. But how probably? 99%? 98%? Is it any better that it would only take the top six pools
to cover over 51% of the hashrate?

Let's assume the controllers of these pools -- every person who knows a password or holds a key to
a critical service on these pools -- are pure of heart. Even if they have the most excellent
of intentions, I would bet they're not immune to getting hacked. It happens, and it happens over
and over again on young sites caught up in racing to meet performance and bandwidth demands.

Many people are familiar with the chaos caused when cryptocurrency exchanges go bad, since they
control such a large percentage of the coins already extant, and of course, they do go bad from
time to time, at various levels of fault. Imagine what happens when the network itself goes bad.

So, let's try to mitigate against that.

This project defaults to setting up a CPU miner to contribute its
proof-of-work to an anonymous pool,
[GoldMin.es](http://goldmin.es). You're of course,
welcome to use whatever pool you like, but these days, GoldMin.es is nice for
no-registration-required mining.

Let's make it easy to drop CPU miners everywhere, have them all throwing in on a peer-to-peer sharechain,
and drive down the influence of the pooled miners. That's my take, anyway.

See, I told you this was a long and boring story. You should have gotten a snack.

# Next steps

Now, I try to make this all easy so you don't have to do a whole lot but
stab at some keys. You got your compiled binaries (non-nerds might call
them "programs" or "apps") in a reasonably secure way. However, if this
is all just too easy for you, you are invited to go and compile cpuminer
straight from the source:

https://github.com/pooler/cpuminer

However, that kind of thing is beyond this "Total Noobs Guide" getting
started thing. All I care about is that lots of people mine. I don't
super care about any one individual's hashrate, assuming he doesn't
hog all the rocket juice for himself.

# Contribute!

In the grand scheme of DogecoinDark, this is a pretty minor project.
But, open source things like this often end up being a one man
show, and that's a sure way to turn into abandonware in six months.

The fact is, there are way smarter people than me out there, with all
kinds of useful experience and knowledge. If you want contributor rights,
and I have some way of verifying that you are a trustworthy sort that's
not going to go backdoor all those noob shibes coming here, feel free to
e-mail me or hit me up on [Reddit](http://reddit.com/u/sunerok).

# Tipjar

![Tipjar](http://i.imgur.com/ehUkOjO.png)

Of course, it's not a proper cryptocurrency project unless you leave out a tip jar. Here's mine:

[DPNC2H2pYUCSebQ992GyeRTRuWw3hCTBwD](http://blockexperts.com/address/DPNC2H2pYUCSebQ992GyeRTRuWw3hCTBwD)

You'll note it's the same as the default address in these one-line installers. If people really are
falling for the default wallet address trick, you can keep tabs on my
apparent hashrate on [GoldMin.es](http://goldmin.es/workers)
-- just look for **DPNC2H2pYUCSebQ992GyeRTRuWw3hCTBwD*. I promise to fix that, by
the way. I just don't have a good way to do it yet.
