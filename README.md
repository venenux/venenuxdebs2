# venenux repositories of packages for not so older releases

VenenuX repositories for second, thirth and fourth generation of modern computers, means 
its for 32bit systems and older Debian's/VenenuX's, mostly, Debian 7, Debian 8 and Debian 9.

**Do you want more modern ones? theck http://venenux.github.io/venenuxdebs3/ repository for Debian 10/11/12!**

## Supported Debians

* Debian 7.0 wheezy and with this support limited to winbuntu 11.04, **likely VenenuX 1.0**
* Debian 8.0 jessie and with this support limited to winbuntu 14.04, **likely VenenuX Debian 8**
* Debian 9.0 stretch and with this support limited to winbuntu 17.04, **likely VenenuX Debian 9**

## How to use this repository

Just add to sources list using your name distro:

| Release | Repo entry in source.list |
| ------- | ------------------------------------------------------------- |
| wheezy  | `deb https://venenux.github.io/venenuxdebs2/ wheezy main`    |
| jessie  | `deb https://venenux.github.io/venenuxdebs2/ jessie main`    |
| stretch | `deb https://venenux.github.io/venenuxdebs2/ stretch main`   |
| extra   | `deb https://venenux.github.io/venenuxdebs2/ any main`       |

Autoconfiguration can be made for more repos by using the package: [any/apt/apt-conf-vnx_0.5.0_all.deb](any/apt/apt-conf-vnx_0.5.0_all.deb)

## How to avoid or use the https

Since apt 0.7.0 exist the `apt-transport-https` package,
you must install  `apt-transport-https` package to use this repository directly.

#### About the TLS and incompatible SSL layer on https for apt

To being able to use this repository with `apt-transport-https` package for jessie or stretch, 
please do as root account logged in:

```
cat > /etc/apt/apt.conf.d/50venenuxgithubrepo << EOF
APT::Get::AllowUnauthenticated "true";
Acquire::AllowInsecureRepositories "true";
Acquire::AllowDowngradeToInsecureRepositories "true";
Acquire::Check-Valid-Until "false";
Aptitude::CmdLine::Ignore-Trust-Violations "true";
Acquire::https::venenux.github.io::Verify-Peer "false";
EOF
```

And then make the apt update procedure.

## Notable packages and architecture supported

Older machines are not 64bit capable, so only 32bit i386 packages are provided.

| Package            | wheezy      | jessie     | stretch   | notes    |
| ------------------ | --------- | --------- | --------- | -------- |
| docker-ci          | 17,18     | 17,18,19  | 19        | containerio package for jessie and stretch |
| nodejs+npm         | 9 & 11    | 12 to 16  | 14 to 20  | soon 16 for i386 https://github.com/nodejs/unofficial-builds/issues/122#issuecomment-1998798096 |

more to come

#### extra or and non free packages

We provide some minimal nonfree packages that unless gnu or open source crap 
always supporting older versions and historic packages


| Package            | wheezy    | jessie    | stretch   | notes    |
| ------------------ | --------- | --------- | --------- | -------- |
| anydesk            | 6.0.0     | 6.0.0     | 6.0.0     | amd64/i386 but cannot view remote desks due SSL, 6.0.1 for amd64 and i386 |
| nomachine          | 6.12.3    | 6.12.3    | 6.12.3    | 6.9.2 also for jessie and stretch on amd64 |
| brave-keyring      |   x       |     x     |     x     | need for manual brave install on our customized repos  |
| google chrome      |  48       | 48/96     |  96       | 48 was the last version for i386 |
| slimjet            |  26       | 26        |  26       | 26 was the last version for wheeze |
| codium             |  1.35     |  1.35     |  1.35     |  las version for i386     |
| yarn               | 1.29      | 1.29      | 1.29      | working    |
| nerolinux          | 4.0.0     | 4.0.0     | 4.0.0     | nerolinux key provided in telegram, or inside venenux debian |
| samsung drivers    | 2         | 2         | 2         | archived of the universal sansung dreivers for older printers |
| la-capitaine       | 2.1       | 2.1       | 2.1       | icon and cursor |
| yarn               | 1.29      | 1.29      | 1.29      | working    |
| nodejs+npm         | 9 & 11    | 12 to 16  | 14 to 20  | working, amd64, arm64/armf, and for i386 only v9 |

Those package are only in the `any` branch component, not in `main` one of the repository index debian packages.

##  Why this repository and why older distro

Some already working and good computers cannot handle a recent linux, 
linux becomes a windo like product since companies started to take into consideration, 
and developers only see their own benefice, GNU project need more support 
and still there are people using older things..

## CONTRIBUTE

PLease read [HACKING.md](HACKING.md) You can fill an issue on Codeberg, or use Telegram Venenux groups:

* https://codeberg.org/venenux/venenux/issues
* https://t.me/latam_debian (Debian only spanish)
* https://t.me/open_debian_devuan (Debian and/or Devuan english, also other langs)
* https://t.me/venenux (English and Spanish also other langs)

## LICENSE

* GPL v 3 100% with one exception: you must cited authors of this work!
* Each package has own license but the work of packaging itselft must cite authors.

Those packages in mayority are backports from Debian originals with security updates, 
also includes patches long awaiting or fixeds that never was acepted becouse deviated to next release of debians.
