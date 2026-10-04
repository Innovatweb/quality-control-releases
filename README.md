# Quality Control - Android releases

APKs of the InnovatWeb quality-control **proof of concept**, and nothing else:
this repository holds no source code.

Each release is built and signed by the `android-signed-release` workflow of
the (private) application repository, from a verified commit, and carries:

- the APK;
- `SHA256SUMS` - check the APK against it before installing;
- `BUILD_INFO.txt` - the commit, version code and the servers it talks to;
- `BADGING.txt` - what the APK itself declares.

The app talks only to `https://quality-control.dst.api.innovatweb.pt` and
`https://auth.api.innovatweb.pt`, and every request needs a login. Installing
it on a phone requires allowing installs from this source.

Releases are never replaced: a new build is a new release.
