# ROMD DAT data

Complete, uncompressed catalogs live at stable platform paths, such as
`redump/psx/discs.dat`. The signed latest index and RSS are served by this
repository's GitHub Pages site. RSS is a notification hint; ROMD verifies the
signed metadata and exact document bytes before reviewing an update.

The publishing implementation and platform definitions live in
[romd-dat-catalogs](https://github.com/MoonlarkStudios/romd-dat-catalogs).
The small caller workflow pins both that implementation and its tooling checkout
to the same commit. Update both pins together. Configure Pages for Actions and
follow the tooling repository's deployment runbook before enabling the schedule.
The existing root/online keys must be preserved when migrating an existing site.

Only extracted DAT changes produce data commits. Metadata renewal uses Pages
artifacts, without data-branch commits. Git retains history: never force-push,
rewrite commits, enable Git LFS for DATs, or trim history while signed indexes
may reference it. ROMD retains its installed document locally.

Public upstream mirroring is disabled until redistribution is qualified. The
initial publication can use synthetic fixtures. No credentials or private keys
belong in this repository.


The proposed No-Intro SNES slice uses `no-intro/snes/standard.dat` and shared
system `snes` (Datomatic `49`). Keep `NOINTRO_SNES_PUBLISH_ENABLED` unset or false
until the reviewed rollout. [Redistribution approval and public-catalog reconciliation](https://github.com/MoonlarkStudios/romd-dat-catalogs/blob/fbb04903d5bf4120c4eaa9f185d6a49418279f0e/docs/nointro-snes-qualification.md)
are recorded for this slice. The overview counter remains 14 above the public
database total, but every public DAT-enabled archive ID is present in the export.
This pin update does not enable mirroring or add a DAT. Roll out
compatible publisher readers before deploying its extended signed registry;
older strict readers reject the new provider. Existing PSX, root keys, metadata
versions, schedule, and artifact-before-reference publication remain in place.
