Dockermail
==========

### Easy mail service Docker containers.

The setup is modular and has:
* `core` -  base SMTP and IMAP server
* `opendkim` - adds DKIM signing service for outgoing mail
* `amavis` - adds incoming SPAM filter

Please see the README in each folder for more information.

## Getting started
 Check out this post:
 [Easy private email hosting with dockermail](http://madespecial.co.uk/blog/2016/1/28/easy-private-email-hosting-with-dockermail)

---
# Config changes
New version has replaced the previous collection of flat files with a single `config.json` file, please see `core` README for details on syntax. You will need to update your configuration to upgrade to new dockermail version.

---

### SPAM
Although OpenDKIM is optional, it will really help your messages across spam filters. See `opendkim` folder for more info on setting it up.

You should also add PTR record to your IP (aka Reverse DNS) which is done by your server provider.

And finally, generate and add an SPF record to your domain, search for instructions on this - there are a few generator site around and the setup steps depend on your domain name provider.

You can test your configuration using the excellent [mail-tester.com](https://www.mail-tester.com/) service.

### Compose
Assuming you follow READMEs to set up all the containers, you should just be able to run:

```bash
docker-compose up
```
This will spin up all the containers and link them together, easy!

### Images on DockerHub
Automated builds of the images are available here:
* Core: https://hub.docker.com/r/adaline/dockermail-core/
* OpenDKIM: https://hub.docker.com/r/adaline/dockermail-opendkim/
* Amavis: https://hub.docker.com/r/adaline/dockermail-amavis/

### Coming soon
* Testing
* https://github.com/vstakhov/rspamd module
