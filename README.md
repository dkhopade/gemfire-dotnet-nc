[<img src="https://geode.apache.org/img/Apache_Geode_logo.png" align="center"/>](http://geode.apache.org)

# Overview
This repository contains GemFire .NET Native Client Samples with Visual Studio 2017 Community Edition (as of this writing).
Simply clone this repository and start building and testing these samples with Microsoft Visual Studio. 

Pull requests are welcome.

**List of samples:**
- [Simple Put/Get/Remove](https://github.com/dkhopade/gemfire-dotnet-nc/tree/master/simple-put-get-remove)
- [SSL Client](https://github.com/dkhopade/gemfire-dotnet-nc/tree/master/ssl-client)
- [Using Client Cache XML and properties file](https://github.com/dkhopade/gemfire-dotnet-nc/tree/master/using-client-cache-xml-and-properties-file)
- [SessionStateProvider with ASP.NET WebAPI/MVC](https://github.com/dkhopade/gemfire-dotnet-nc/tree/master/session-state-sample)


**For developers testing in Visual Studio**
Since all of the samples here are based on .NET NC 10.x, plesae follow this: under Tools->Options->Projects And Solutions->Web Projects, enable the property “Use 64-bit version of IIS Express”. You must use a 64-bit target.
