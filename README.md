# BundleScan
Recovers the open-source packages, versions and licences inside packaged Python and Electron desktop apps, and writes them out as a standard software bill of materials (SBOM).

> **Status: planned.** No working code yet.

## project summary:
BundleScan will be an open-source item that produces a SBOM  for packaged desktop apps. After a python app is bundled with pyinstaller, most of the record of which packages it contains (and which versions),
is irretrievable. When we tested existing scanners on our own product (ORYS) less than 20% of its python packages were detected, even after unpacking. BundleScan will unpack said bundles without running them, 
map bundled modules to PyPi packages, and recover versions from remaining metadata, version strings and comparison with published releases. For electron apps it will unpack app.asar and separate packages the app 
runs from development tools shipped but not used. It will output CycloneDX and SPDX files with package URLs, licences and a confidence level per package, returning "unknown" instead of guessing. A tested release 
under Apache 2.0, alongside a public test set of apps (with known versions); as well as a matching contributed upstream to ScanCode are the expected results.
