## How do I enable HTTP PUT and DELETE
#### 405---HTTP-verb-used-to-access-this-page-is-not-allowed

#### Just add following settings in your server's web.config

```xml
<system.webServer>
    <handlers>
      <remove name="WebDAV" />
      <remove name="ExtensionlessUrlHandler-Integrated-4.0" />
      <remove name="OPTIONSVerbHandler" />
      <remove name="TRACEVerbHandler" />
      <add name="ExtensionlessUrlHandler-Integrated-4.0" path="*." verb="*" type="System.Web.Handlers.TransferRequestHandler" preCondition="integratedMode,runtimeVersionv4.0" />
    </handlers>
    <modules>
        <remove name="WebDAVModule" />
    </modules>
    <security>
        <requestFiltering>
            <verbs allowUnlisted="false">
                <add verb="GET" allowed="true" />
                <add verb="POST" allowed="true" />
                <add verb="DELETE" allowed="true" />
                <add verb="PUT" allowed="true" />
            </verbs>
        </requestFiltering>
    </security>
</system.webServer>
```


