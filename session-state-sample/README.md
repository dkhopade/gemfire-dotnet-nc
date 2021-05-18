## Overview

This is a sample code that stores a session state for an ASP.NET app (basically .NET Web App). It's a command line simple program that connects to a region using cache factory object and does not involve any depenency on Java.

Before you continue, you need to follow these steps for SessionStateProvider sample works:

- In your Web.Config file, add below section under <system.web> section. The timeout value can be changed as needed:
    ```
    <!--GemFire SessionStateProvider-->
    <sessionState mode="Custom" cookieless="false" timeout="20" customProvider="GemFireSessionProvider">
      <providers>
        <add name="GemFireSessionProvider" type="Pivotal.GemFire.Session.SessionStateStore" region="sessionStateRegion"/>
      </providers>
    </sessionState>
    ```
- In Global.asax.cs code-behind file, you will need add a class called `BasicAuthInitialize` that implements `Apache.Geode.Client.IAuthInitialize` interface. It can also be declared outside of Global.asax.cs file in its own class file (for example: BasicAuthInitialize.cs).
    ```
    public class BasicAuthInitialize : IAuthInitialize
    {
        private string _username;
        private string _password;
        
        public BasicAuthInitialize(string username, string password)
        {
            _username = username;
            _password = password;
        }
        
        public void Close()
        {
        }
        
        public Properties<string, object> GetCredentials(Properties<string, string> props, string server)
        {
            var credentials = new Properties<string, object>();
            credentials.Insert("security-username", _username);
            credentials.Insert("security-password", _password);
            return credentials;
        }
    }
    ```
    Please refer the docs for more details: https://gemfire-native-dotnet.docs.pivotal.io/102/gemfire-native-client-ssp/ssp.html
- In Global.asax.cs file and under `Application_Start()` event, add the line that initializes the instance of `BasicAuthInitializeClass` class using its constructor that accepts the credentials.

- Make sure you have `geode.properties` and `cache.xml` files defined that contains the necessary information to connect to GemFire cluster and client side properties. Plesae refer to this doc and KB for more details.
    https://gemfire-native-dotnet.docs.pivotal.io/102/geode-native-client-dotnet/configuring/system-level-configuration.html
    https://community.pivotal.io/s/article/How-to-configure-geode-properties-file-for-GemFire-NET-Native-Client-10-2-with-an-ASP-NET-application?language=en_US

This sample was created, built and tested with Microsoft Visual Studio 2017 Community Edition.