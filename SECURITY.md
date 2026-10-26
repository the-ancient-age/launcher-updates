# Security

## Verify a download by hand

1. Install the official [minisign](https://jedisct1.github.io/minisign/) tool.
2. Download the channel manifest and its signature, for example `channels/stable.json` and
   `channels/stable.json.minisig`.
3. Verify the signature with the main public key from `keys/`:

   ```
   minisign -Vm stable.json -P <main public key>
   ```

4. Compute the SHA-256 of the file you downloaded (PowerShell: `Get-FileHash <file>`) and compare it with
   the `sha256` listed for it in the verified manifest. The size must match too.

The launcher does all of this automatically before installing anything.

## Keys

- **Main key:** signs every manifest.
- **Emergency (backup) key:** kept offline and only used to sign a key rotation, never a normal release.
- Private keys never leave the maintainer's offline storage. They are not in this repository, in the
  launcher or in any release file.

## Reporting a problem

If something looks wrong (a file that does not match its manifest, a signature that does not verify, a
release you did not expect), do not run it and report it to the maintainer on the project's Discord.
