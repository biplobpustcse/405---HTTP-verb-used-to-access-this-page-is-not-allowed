## 405---HTTP-verb-used-to-access-this-page-is-not-allowed

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
</system.webServer>
```


