# Danu Listener — Auto-sign CI

Push this repo to GitHub (main branch). The workflow `.github/workflows/build-and-sign.yml` will:
- install Android SDK command-line tools
- generate a keystore named `debug-keystore.jks` with alias `danu_debug` and password `danu123`
- build the app (attempt release, fallback to debug)
- sign the APK with apksigner
- upload two artifacts:
  - `app-signed-apk` (signed APK ready to install)
  - `debug-keystore` (the generated keystore file)

Keystore credentials (demo):
  alias: danu_debug
  keystore file: debug-keystore.jks
  keystore password: danu123
  key password: danu123

After pushing, go to GitHub Actions → run → download artifacts when job completes.
