Mail-in-a-Box (Ubuntu 16.04 aware)
==================================

**This is a fork**

For original sources, see [Mail-in-a-Box](https://github.com/mail-in-a-box/mailinabox)!

Why is this fork special?
-------------------------

Using this fork, one may easily install mail-in-a-box on **Ubuntu 16.04.03**!

Features
--------

* [spreed](https://nextcloud.com/webrtc/) in Nextcloud by default
    * private and secure voice & videoconference calls
* [nextant](https://github.com/nextcloud/nextant#nextant) in Nextcloud by default
    * fulltext search built on top of Apache Solr
	* you can search text within all of your JPGs, PNGs, PDFs, Office documents, etc. (it's using [OCR](https://en.wikipedia.org/wiki/Optical_character_recognition))
* all services run in an systemd init system (much better UX)
* no php5 anywhere! - all running on php7, so there is no need to maintain two versions of php
* lesser hardware requirements (I run it on 512 MB RAM & 1 CPU without any hassle - from [DigitalOcean](https://www.digitalocean.com/?refcode=210c1aeb22bb&utm_campaign=Referral_Invite&utm_medium=Referral_Program&utm_source=CopyPaste) )

Disadvantages
-------------

* lack of dovecot-lucene in Ubuntu 16.04 brought me to a decision to don't include fulltext search into the roundcube
    * but that seems not to be an issue because all modern email clients have this already installed

Quick Install
-------------

```bash
# Clone this fork
git clone https://github.com/jirislav/mailinabox.git
cd mailinabox

git checkout v0.25-ubuntu16

# Run installation
setup/start.sh
```

## Toubleshooting

In case of some trouble, please issue `setup/start.sh` command once again. If that doesn't help, please also try this command:
```bash
INSTALL_NEXTANT=no setup/start.sh
```

Otherwise, you are welcome to [file a new issue](https://github.com/jirislav/mailinabox/issues/new).

For further info, see [the original documentation for obtaining mail-in-a-box](https://mailinabox.email/guide.html).

Installation
------------

See the [setup guide](https://mailinabox.email/guide.html) for detailed, user-friendly instructions.

For experts, start with a completely fresh (really, I mean it) Ubuntu 14.04 LTS 64-bit machine. On the machine...

Clone this repository:

	$ git clone https://github.com/mail-in-a-box/mailinabox
	$ cd mailinabox

_Optional:_ Download my PGP key and then verify that the sources were signed
by me:

	$ curl -s https://keybase.io/joshdata/key.asc | gpg --import
	gpg: key C10BDD81: public key "Joshua Tauberer <jt@occams.info>" imported

	$ git verify-tag v0.26
	gpg: Signature made ..... using RSA key ID C10BDD81
	gpg: Good signature from "Joshua Tauberer <jt@occams.info>"
	gpg: WARNING: This key is not certified with a trusted signature!
	gpg:          There is no indication that the signature belongs to the owner.
	Primary key fingerprint: 5F4C 0E73 13CC D744 693B  2AEA B920 41F4 C10B DD81

You'll get a lot of warnings, but that's OK. Check that the primary key fingerprint matches the
fingerprint in the key details at [https://keybase.io/joshdata](https://keybase.io/joshdata)
and on my [personal homepage](https://razor.occams.info/). (Of course, if this repository has been compromised you can't trust these instructions.)

Checkout the tag corresponding to the most recent release:

	$ git checkout v0.26

Begin the installation.

	$ sudo setup/start.sh

For help, DO NOT contact me directly --- I don't do tech support by email or tweet (no exceptions).

Post your question on the [discussion forum](https://discourse.mailinabox.email/) instead, where me and other Mail-in-a-Box users may be able to help you.

The Acknowledgements
--------------------

This project was inspired in part by the ["NSA-proof your email in 2 hours"](http://sealedabstract.com/code/nsa-proof-your-e-mail-in-2-hours/) blog post by Drew Crawford, [Sovereign](https://github.com/sovereign/sovereign) by Alex Payne, and conversations with <a href="https://twitter.com/shevski" target="_blank">@shevski</a>, <a href="https://github.com/konklone" target="_blank">@konklone</a>, and <a href="https://github.com/gregelin" target="_blank">@GregElin</a>.

Mail-in-a-Box is similar to [iRedMail](http://www.iredmail.org/) and [Modoboa](https://github.com/tonioo/modoboa).

The History
-----------

* In 2007 I wrote a relatively popular Mozilla Thunderbird extension that added client-side SPF and DKIM checks to mail to warn users about possible phishing: [add-on page](https://addons.mozilla.org/en-us/thunderbird/addon/sender-verification-anti-phish/), [source](https://github.com/JoshData/thunderbird-spf).
* In August 2013 I began Mail-in-a-Box by combining my own mail server configuration with the setup in ["NSA-proof your email in 2 hours"](http://sealedabstract.com/code/nsa-proof-your-e-mail-in-2-hours/) and making the setup steps reproducible with bash scripts.
* Mail-in-a-Box was a semifinalist in the 2014 [Knight News Challenge](https://www.newschallenge.org/challenge/2014/submissions/mail-in-a-box), but it was not selected as a winner.
* Mail-in-a-Box hit the front page of Hacker News in [April](https://news.ycombinator.com/item?id=7634514) 2014, [September](https://news.ycombinator.com/item?id=8276171) 2014, [May](https://news.ycombinator.com/item?id=9624267) 2015, and [November](https://news.ycombinator.com/item?id=13050500) 2016.
* FastCompany mentioned Mail-in-a-Box a [roundup of privacy projects](http://www.fastcompany.com/3047645/your-own-private-cloud) on June 26, 2015.
