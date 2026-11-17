# Contributing

Thank you for helping with Merget's plugin for coding agents. This file says
how a change gets in. The code and skills here are licensed under the
Apache License, Version 2.0 ([LICENSE](LICENSE)); security reports go to
security@merget.ai, never to a public issue ([SECURITY.md](SECURITY.md)).

## What to contribute

- Fixes and improvements to the four skills under `skills/<name>/`: wording
  that an agent misreads, a tool argument the skill describes wrongly, a
  missing case in a reference.
- Packaging fixes: a manifest a client fails to read, a schema refresh, an
  install route that stopped working.
- Install notes for a client the README does not cover yet.

The skills teach the tools Merget's server exposes today; they never invent a
tool, argument or field, and a contribution that adds one needs to point at
the server release that ships it. What the server answers is not changed
here: a plugin release changes only what the skills teach and how the plugin
is packaged.

## Before you open a pull request

1. Edit `packaging/source.json` for anything that lives in a manifest (name,
   version, description, addresses, listing fields) and run
   `node packaging/build.mjs`; never edit a generated manifest by hand.
2. Run what CI runs (see [RELEASING.md](RELEASING.md), "Cut a version"):

   ```sh
   node packaging/build.mjs --check --base origin/main
   node packaging/build.mjs --validate
   for s in skills/*/; do npx -y skills-ref@0.1.5 validate "$s"; done
   claude plugin validate --strict .
   claude plugin validate --profile directory .
   ```

3. A change to anything a client reads (a skill, a manifest, `assets/`)
   needs a version bump in `packaging/source.json` and a CHANGELOG entry;
   `--check --base` refuses it otherwise. Changes to `README.md`,
   `RELEASING.md`, `CHANGELOG.md`, `packaging/` and `.github/` alone need no
   bump.
4. User-facing copy says Merget, and names tools the way the server does
   (`merget_status`, ...). The checker refuses a client-specific tool prefix
   outside `skills/merget-setup/references/clients.md`.

## Developer Certificate of Origin

Every commit must be signed off. By signing off you certify the
[Developer Certificate of Origin, version 1.1](https://developercertificate.org/):
that you wrote the change or have the right to submit it under the
repository's license, and that you understand the contribution is public and
kept with your sign-off. There is no contributor license agreement.

Sign off by adding this line to the end of the commit message, with your
real name and an email address you can be reached at:

```
Signed-off-by: Your Name <you@example.com>
```

`git commit -s` adds it from your git identity. A pull request whose commits
lack the line is not merged until they carry it (`git commit --amend -s`, or
`git rebase --signoff origin/main` for several commits, then push again).

The text of the certificate, for reference:

```
Developer Certificate of Origin
Version 1.1

Copyright (C) 2004, 2006 The Linux Foundation and its contributors.

Everyone is permitted to copy and distribute verbatim copies of this
license document, but changing it is not allowed.


Developer's Certificate of Origin 1.1

By making a contribution to this project, I certify that:

(a) The contribution was created in whole or in part by me and I
    have the right to submit it under the open source license
    indicated in the file; or

(b) The contribution is based upon previous work that, to the best
    of my knowledge, is covered under an appropriate open source
    license and I have the right under that license to submit that
    work with modifications, whether created in whole or in part
    by me, under the same open source license (unless I am
    permitted to submit under a different license), as indicated
    in the file; or

(c) The contribution was provided directly to me by some other
    person who certified (a), (b) or (c) and I have not modified
    it.

(d) I understand and agree that this project and the contribution
    are public and that a record of the contribution (including all
    personal information I submit with it, including my sign-off) is
    maintained indefinitely and may be redistributed consistent with
    this project or the open source license(s) involved.
```

## License of contributions

Unless you say otherwise, a contribution you submit on purpose for inclusion
in this repository is licensed under the Apache License, Version 2.0,
without additional terms or conditions (section 5 of the license).

## Conduct and contact

Be direct and courteous in issues and pull requests. Questions about the
plugin go to support@merget.ai; questions about the Merget service, its
Terms of Service and its Privacy Statement are answered at
https://merget.ai/legal.
