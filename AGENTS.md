# Kill the Newsletter plugin notes

Implementation invariants for maintainers. The user-facing documentation is
`killthenewsletter/readme.md`.

- The plugin implements the control plane without claiming `CapFetch`: its Atom
  feeds are read by the host's generic parser, so `feeds.plugin_name` stays
  empty and `ReconcileFeeds` is untouched.
- The `base_url` setting selects the public or a self-hosted instance. It
  changes both what `Match` recognizes and what `Provision`/`Action` call, so
  `Configure` must cache it before matching.
- A provisioned feed returns an inbox address and an Atom URL. The inbox address
  is display-only and rendered with a copy control; the Atom URL is the stored
  feed.
