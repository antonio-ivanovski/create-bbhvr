# Versioning

This fork uses a composite versioning scheme to track both the upstream `create-bhvr` version and fork-specific changes.

## Format

`UPSTREAM-bbhvr.INTERNAL`

- **UPSTREAM**: The version of the original `create-bhvr` package (e.g., `0.6.4`)
- **INTERNAL**: The fork-specific revision number (starts at 0)

## Examples

- `0.6.4-bbhvr.0` - Initial fork release based on upstream 0.6.4
- `0.6.4-bbhvr.1` - First fork-specific patch on top of 0.6.4
- `0.7.0-bbhvr.0` - After syncing with upstream 0.7.0

## Version Bump Rules

### Upstream Sync

When syncing changes from upstream `create-bhvr`:

1. Update `version` to match the new upstream version with `-bbhvr.0` suffix
2. Update `createBbhvr.upstreamVersion` to the new upstream version
3. Reset `createBbhvr.forkRevision` to `0`

### Fork-Only Changes

When making fork-specific changes without upstream updates:

1. Increment the internal revision number in `version` (e.g., `-bbhvr.0` → `-bbhvr.1`)
2. Increment `createBbhvr.forkRevision`

## Package Metadata

The `package.json` includes a `createBbhvr` object with:

```json
{
  "createBbhvr": {
    "upstreamVersion": "0.6.4",
    "forkRevision": 0
  }
}
```

## Release Steps

1. Update the version in `package.json` following the rules above
2. Commit the version bump: `git commit -am "chore: bump version to X.Y.Z-bbhvr.N"`
3. Create and push a tag: `git tag -a vX.Y.Z-bbhvr.N -m "Release vX.Y.Z-bbhvr.N" && git push origin vX.Y.Z-bbhvr.N`
4. The GitHub Actions workflow will automatically publish to npm
