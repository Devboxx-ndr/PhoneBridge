# Maintainer release process

Keep source and signing materials in a separate private workspace. Never attach that Git history to this distribution repository. No signing secrets or application-build workflow belongs here.

## First publication, after approval

1. Install GitHub CLI and run `gh auth login --web --git-protocol https`; check `gh auth status`. Do not send tokens through chat/Issues.
2. Replace every OWNER placeholder with the approved GitHub account. Check name availability; do not reuse an existing repository without review.
3. Create a separate empty PhoneBridge repository, enable Issues and use a fresh Git history containing only the approved documentation. Use a GitHub noreply commit address.
4. Obtain final owner approval before making the new repository public or pushing public content. Never change the source repository's visibility.
5. Create tag/release v2.7.1 using RELEASE_NOTES.md. Attach PhoneBridge-2.7.1-release.apk, an identical-byte stable alias PhoneBridge.apk, and SHA256SUMS.txt. APKs belong only in release assets, never Git commits. Mark the release latest.
6. Download the actual public assets and verify their hashes, both README links, Issues and all internal links. GitHub's automatic Source code archives contain only this documentation repository.

## Future updates

Build/test privately with the same package and release key. Increase versionCode above 15 and every previously distributed version; extract versionName/code from that build. Verify its signer, alignment, debugging disabled and bundled content. Keep the signing key backed up privately. Update documentation/privacy as needed, changelog, release notes and checksums. Review/approve the exact new file list, then create a new tag/release with versioned APK and identical-byte PhoneBridge.apk alias. Retain older releases; do not silently replace old binaries under old tags.

## Download statistics

GitHub returns per-asset `download_count`; these are download events, not unique people or installations. Include both APK aliases when counting total APK events and exclude checksum/images. Paginate all release pages.

PowerShell, after replacing OWNER:

```powershell
$releases = Invoke-RestMethod -Headers @{Accept='application/vnd.github+json'} 'https://api.github.com/repos/Devboxx-ndr/PhoneBridge/releases?per_page=100&page=1'
$releases | ForEach-Object {
  $tag=$_.tag_name
  $_.assets | Where-Object name -Like '*.apk' |
    Select-Object @{n='Version';e={$tag}},name,download_count
}
```

Increment page until empty. Unauthenticated public API access is rate-limited; keep any authentication tokens outside public files.

[Asset API](https://docs.github.com/en/rest/releases/assets) · [Stable latest links](https://docs.github.com/en/repositories/releasing-projects-on-github/linking-to-releases) · [CLI login](https://cli.github.com/manual/gh_auth_login)
