Inkwell 7.42 for the Fire tablet (Android)
==========================================

WHAT IS HERE
------------
- builds/: the ready-made 7.42 APK, signed with Inkwell's own key, so it installs over the Inkwell already on the tablet and keeps your documents. Download it and follow
  "READ ME FIRST - FIRE TABLET.txt".
- The build kit: the same files GitHub Actions builds from
  (.github/workflows/build-apk.yml). A push to main builds again
  and publishes the result as a release of this repository.
- WORKFLOW build-apk.yml (copy).txt: the workflow as a plain text file.
- INKWELL_HANDOFF_v7p*.txt: the notes from each version, newest last.
- LICENCE.txt: all rights reserved; no licence is granted.

Look for "v7.42" beside the date at the top of Inkwell to know this
version is running.

THE SIGNING KEY
---------------
This repository is PUBLIC, so the signing key is not in it (signing/ is
left out and ignored). The build on GitHub takes the key from two
repository secrets instead (Settings, Secrets and variables, Actions,
New repository secret):
- INKWELL_KEYSTORE_B64: the keystore file as one line of base64. On a
  Mac, in the folder holding signing/:  base64 -i signing/inkwell.jks | tr -d '\n' | pbcopy
- INKWELL_SIGNING_PROPERTIES: the three lines of signing/signing.properties
  (storePassword=..., keyPassword=..., keyAlias=...).
With the secrets set, every APK GitHub builds installs over the one on
the tablet and keeps the documents. Without them, the APK is signed with
the Android test key and named -TESTKEY: it installs on a tablet with no
Inkwell, but not over an Inkwell signed with the real key. The APK in
builds/ is signed with the real key.
