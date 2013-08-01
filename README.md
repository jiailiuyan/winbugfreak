Winbugfreak
===========

Bug tracking client for wpf/silverlight applications, see [server](https://github.com/agilefreaks/apibugfreak)

Overview
========

A bare bones bug tracking framework that you can use and deploy your self, it's main aim is to integrate seemesly 
with your application and centralize issues in a main repository, we are working on having a free server deployed
please contact us if you can help

Instalation
===========

You can grad the package from [nuget](http://www.nuget.org/)

For wpf
```
PM> Install-Package BugFreak.WPF
```

For Silverlight
```
PM> Install-Package BugFreak.Silverlight
```

Configuration
=============

For WPF update you config file
```
<pre>
	<configSections>
		<section name="BugFreak" type="System.Configuration.AppSettingsSection, System.Configuration, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" />
	</configSections>

	<BugFreak>
		<add key="ServiceEndpoint" value="http://endpoint.ro"/>
		<add key="ApiKey" value="apiKey"/>
		<add key="Token" value="token"/>
	</BugFreak>
<pre>

```

For Silverlight user add the configuration in `App.xaml.cs#Application_Startup`

```
BugFreak.GlobalConfig.Settings.ApiKey = "apiKey";
BugFreak.GlobalConfig.Settings.Token = "token";
BugFreak.GlobalConfig.Settings.ServiceEndpoint = "http://service.com";
```

Register
========

Hook tracking in WPF
```
BugFreak.Integration.WPF.AgileReporter.Hook();
```

Hook tracking in Silverlight
```
BugFreak.Integration.Silverlight.AgileReporter.Hook();
```

That's all folks, any uncatched exceptions will be reported back to the server

Contributing
============

1. Fork it.
2. Create a branch (git checkout -b my_cool_feature)
3. Commit your changes (git commit -am "Added CoolFeature")
4. Push to the branch (git push origin my_cool_feature)
5. Open a Pull Request
