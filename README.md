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

## Signing certificate

Every APK here is signed with the same key, so each one installs over the
previous one. Its certificate:

- Subject: `CN=InnovatWeb Quality Control PoC, O=InnovatWeb, C=PT`
- SHA-256: `f7:4d:25:b2:a2:92:9d:50:f8:15:1a:ee:a7:fb:c5:b9:d5:09:5e:ba:64:0a:ca:8d:9d:59:e1:0d:70:b1:6c:fa`

Check with `apksigner verify --print-certs <apk>`. A different certificate
means the APK did not come from this project.
