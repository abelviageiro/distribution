# Amzi! Prolog Distribution
This repository contains the binaries needed to run Amzi! Prolog standalone or to integrate Amzi! Prolog Logic Server into your applications.
Download the latest version for your platform, for best compatibility.

The binary distribution files (ordered by platform) are:
- Win32:
  - amzi_apls_win32_\<Version>.zip
- Win64:
  - amzi_apls_win64_\<Version>.zip
- Mac:
  - amzi_apls_mac_\<Version>.zip
- .NET:
  - see below

## Eclipse IDE support
There is an Eclipse IDE plugin, that can run Prolog programs interpreted (consulted) or compiled, but also supports debugging.
The source code can be found in the separate IDE repository: https://github.com/AmziLS/ide

A direct binary download is available here as *amzi_eclipse_plugin_\<Version>.zip*, or follow the installation instructions below to get the latest plugin version, without having to explicitly download anything.

### Installation
To install the Eclipse plugin, make sure you have a recent version of Eclipse. In Eclipse select the menu ```Help|Install New Software...```. In the edit box labeled "Work with:" enter the following URL and press "Add...":

https://github.com/AmziLS/distribution/raw/master/eclipse_plugin_update_site/

Check "Amzi! Eclipse Feature" (and its sub elements), click "Next" several times, accept the license terms, then click "Finish".
Go in the menu "Window|Perspective|Open Perspective|Other..." and select "Prolog", then confirm.
From there on, you may want to watch these two videos:

- [Getting Started with Eclipse Amzi! Prolog](https://www.youtube.com/watch?v=EMxLnn2I9yo)
- [Amzi! Prolog Source Code Debugger in Eclipse](https://www.youtube.com/watch?v=fewTmnarfu8)

## .NET
There is a [NuGet package](https://www.nuget.org/packages/amzinet/0.1.0) that can easily be pulled into your project. The .NET binary package consists of two DLLs, one is the .NET wrapper called amzinet.dll and other is amzi.dll which is the Logic Server. amzi.dll should be deployed to your bin directory. The NuGet package is set up to make your project do just that. Besides NuGet, .NET binaries could also be found in one of the Windows archives found in this repository.

### ASP.NET Web Applications
There is an extra step required to make ASP.NET web application run smoothly with Amzi! Prolog and Logic Server. ASP.NET uses what is known as [Shadow Copy](https://en.wikipedia.org/wiki/Shadow_Copy), which copies all the binaries necessary for the project into a preliminary directory where they are run from (typically, it is `Temporary ASP.NET Files`). The Shadow Copy process copies only the CLR DLLs and their references, it will not copy the amzi.dll. For that to be picked up by the application, the only alternative is to deploy the amzi.dll into one of the directories included in the `PATH` environment variable. A better way if you do not have access to any of those directories -- such as when you are deploying your application to Microsoft Azure Cloud services -- is that you add your application pool's bin directory to the `PATH` environment variable at the `Application_Start` event.

```csharp
string path = Environment.GetEnvironmentVariable("PATH");
string binDir = Path.Combine(AppDomain.CurrentDomain.BaseDirectory, "Bin");
if (!path.EndsWith(";"))
{
    path = path + ";";
}
path = path + binDir;
Environment.SetEnvironmentVariable("PATH", path);
```
