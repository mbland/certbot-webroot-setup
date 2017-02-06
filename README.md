# Certbot Webroot Setup

__NOTE: Right now this program is untested and incomplete, very much in the
[Exploration
phase](https://github.com/mbland/automated-testing-playbook/blob/master/pages/rapid-prototyping.md#exploration).__

Source: https://github.com/mbland/certbot-webroot-setup

[![License](https://img.shields.io/github/license/mbland/go-script-bash.svg)](https://github.com/mbland/go-script-bash/blob/master/LICENSE.md)

This program encapsulates the steps needed to set up
[Certbot](https://certbot.eff.org/) to use the [Webroot
plugin](https://certbot.eff.org/docs/using.html#webroot) to install and renew
[Let's Encrypt](https://letsencrypt.org/) SSL certificates.

It is written using the [go-script-bash
framework](https://github.com/mbland/go-script-bash).

### Table of contents

- [Introduction](#introduction)
- [Environment setup](#environment-setup)
- [Feedback and contributions](#feedback-and-contributions)
- [Open Source](#open-source)

### Introduction

To get a copy of the repo and view the online help:

```bash
$ git clone https://github.com/mbland/certbot-webroot-setup
$ cd certbot-webroot-setup
$ ./certbot-webroot-setup -h
```

It's recommended you alias the `certbot-webroot-setup` script using
`certbot-webroot-setup env` to create the `cws` alias per the following:

```bash
$ eval "$(./certbot-webroot-setup env cws)"
```

To try to install `certbot`, generate a private key and Certificate Signing
Request, and fetch a Let's Encrypt certificate all at once:

```bash
$ cws setup-all my-site.com me@mysite.com
```

If instead you want to take things step-by-step, you can run individual commands
such as the following:

```bash
$ cws certbot-setup
$ cws ssl-generate private-key my-site.com.key
$ cws site-setup my-site.com my-site.com.key me@my-site.com
$ cws get-cert my-site.com
```

In either case, use `cws webserver-config` to generate a configuration block for
your web server. __Note that right now, only [Nginx](http://nginx.org) is
supported.__

### Environment setup

To run `certbot-webroot-setup`, you must have
[Bash](https://en.wikipedia.org/wiki/Bash_%28Unix_shell%29) version 3.2 or
greater installed on your system. Run `bash --version` to make sure Bash is in
your `PATH` and is a compatible version. You should see output like this:

```
GNU bash, version 3.2.57(1)-release (x86_64-apple-darwin15)
Copyright (C) 2007 Free Software Foundation, Inc.
```

If you do not see this, follow the instructions in the [Installing
Bash section of the go-script-bash
README](https://github.com/mbland/go-script-bash#installing-bash).

### Open Source License

This software is made available as [Open Source
software](https://opensource.org/osd-annotated) under the [ISC
License](https://www.isc.org/downloads/software-support-policy/isc-license/).
For the text of the license, see the [LICENSE](LICENSE.md) file.
