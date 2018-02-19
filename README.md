# certbot-dns-inwx
INWX DNS authenticator plugin for certbot

An authenticator plugin for [certbot](https://certbot.eff.org/) to support [Let's Encrypt](https://letsencrypt.org/) DNS challenges (dns-01) for domains managed by the nameservers of InterNetworX ([INWX](https://www.inwx.com)).

## Requirements
* certbot (>=0.15)

For older Ubuntu distributions check out this PPA: [ppa:certbot/certbot](https://launchpad.net/~certbot/+archive/ubuntu/certbot)

## Installation
First install the plugin:

    python setup.py install

Configure it with your INWX API Login Details:

    vim /etc/letsencrypt/inwx.cfg

Make sure the file is only readable by root! Otherwise all your domains might be in danger.

## Usage
Request new certificates via a certbot invocation like this:

    certbot certonly -a certbot-dns-inwx:dns-inwx -d sub.domain.tld -d otherdomain.tld

Renewals will automatically be performed using the same authenticator and credentials by certbot.

