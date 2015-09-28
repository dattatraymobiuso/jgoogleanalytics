## We have moved... ##
Please refer to [Github's](https://github.com/siddii/jgoogleanalytics) project page for the latest code & documentation. We will continue to keep Google code project repository for sometime with the legacy code & documentation.

Please create [issues](https://github.com/siddii/jgoogleanalytics/issues) in Github for any future bugs or feature requests.


### Introduction ###
**JGoogleAnalytics** is a lightweight, unobtrusive Java utility for tracking usage information on Java applications through [Google analytics](http://www.google.com/analytics). It can be used for gathering usage statistics on utilities, plugins(Eclipse, IntelliJ, Netbeans etc.), client-side, server-side, middleware, desktop or any Java based applications. Hence, allowing us to perform usage & trend analysis on the application of interest.

### Maven Dependency ###
JGoogleAnalytics is available on maven repo. Following is the maven pom dependency snippet.
```
<dependency>
  <groupId>com.boxysystems</groupId>
  <artifactId>jgoogleanalytics</artifactId>
  <version>0.5</version>
  <classifier>sources</classifier>
</dependency>
```

### Usage ###
If you have a registered [Google analytics](http://www.google.com/analytics) account, you can write a code snippet like below to capture the usage data. **FocusPoint** is a logical point of focus in the application. It can be events like application/module load, user actions, error events etc.

```
  //Google analytics tracking code for Library Finder
  JGoogleAnalyticsTracker tracker = new JGoogleAnalyticsTracker("Library Finder","1.3.2","UA-2184000-1");

  FocusPoint focusPoint = new FocusPoint("PluginLoad");

  tracker.trackAsynchronously(focusPoint);
```

### Proof Of Concept ###
For the proof of concept, I have used this tool in [Library Finder-IntelliJ](http://plugins.intellij.net/plugin/?id=51) plugin. I was tracking events like plugin load, user actions like Find Library action, Configuration changes action etc. I could see the usage statistics when I login to the google analytics account.
If you want to know more, please read this [posting](http://blogs.boxysystems.com/2008/4/2/jgoogleanalytics).

### Caveat ###
  * Google analytics does not update their reports in real time because of their high volume of subscribers. It usually gets updated every 24 hrs. If you are really curious to know if the tracking went fine, you can attach a **LoggingAdapter** to **JGoogleAnalyticsTracker** and see if you are seeing the success message.
  * JGoogleAnalytics would gracefully ignore errors and not collect statistics for the application running offline (without network connectivity)

[![](http://libraryfinder.googlecode.com/svn/IntellijBanner.png)](http://www.jetbrains.com/idea/)