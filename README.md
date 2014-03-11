cURL NuGet Targets Patch
=====================

Patch for nuget package of curl.7.30.0.2 and curl.redist.7.30.0.2 to support v120 (VS2013 default) and CTP_Nov2013 compilers.

The cURL NuGet packages for both [curl.7.30.0.2](https://www.nuget.org/packages/curl/) and [curl.redist.7.30.0.2](https://www.nuget.org/packages/curl.redist/) contain multiple of the following condition:

`$(PlatformToolset.ToLower().IndexOf('v110')) &gt; -1`

This prevents compilation and linking for the toolsets v120 (VS2013 default), v120_xp, and for CTP_Nov2013 (with additional c++11 support).

Until the packages are updated you must either compile for v100, v110 or adopt these changes to your targets files.

**To use simply replace the files of the same names in your nuget packages and rebuild.**

The files are located as follows:

* `curl.7.30.0.2\build\native\curl.targets`
* `curl.redist.7.30.0.2\build\native\curl.redist.targets`
