# nanoflux-plugin-killthenewsletter

A nanoflux external plugin for Kill the Newsletter. It creates newsletter
inboxes and manages their Atom feeds from nanoflux.

## Install

```bash
cd nanoflux/plugins/killthenewsletter
GOOS=linux GOARCH=amd64 CGO_ENABLED=0 go build -o ../nanoflux-plugin-killthenewsletter .
```

Restart nanoflux after putting the binary in its plugins directory
(`NF_PLUGINS_DIR`, `/plugins` in the container).

## Configuration

Set the instance base URL on the admin plugins page. Leave it empty to use the
public `https://kill-the-newsletter.com` instance.
