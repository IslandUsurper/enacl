## Fork maintenance

Plan is:
- keep `master` up to date with the upstream; no commits from us
  + We're not expecting too many more commits from the upstream,
    but should any emerge, they could be included trivially.
- use `dev` as our effective trunk branch:
  + topic branches are merged into dev
  + upstream commits, if any, move from `master` to `dev`
    (can use `merge`, `cherry-pick`, or whatever works best at the time)
  + tag notable commits in dev; keep changelog updated with those
  + use `ref` in dependencies to point to dev commit hashes
    (eventually shift to the tags for readability, but wait until we have some
     [tag-protection-rules](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/configuring-tag-protection-rules
) setup to ensure the same tag always points to the same commit

The overall goal is to allow for further development on this repo without worrying
too much about the upstream from which it was forked.
