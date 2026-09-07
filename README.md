# Romance R6 Update Channel

This repository contains only the current release executable and its update
manifest. It does not contain application source code or credentials.

The installed client checks `update.json` on startup. When `version` is newer
than the version compiled into the client, it downloads `Romance-R6.exe`,
verifies the SHA-256 value, replaces the installed executable, and restarts.

## Publishing a future update

1. Increase `kCurrentVersion` in `src/release_services.h`.
2. Build and test the x64 Release executable.
3. Replace `Romance-R6.exe` in this repository.
4. Set `version` in `update.json` to the same version.
5. Replace `sha256` with the new executable's lowercase SHA-256 value.
6. Commit and push both files together.

Always upload the executable before or in the same commit as its matching
manifest. The client will reject a partial or mismatched download.
