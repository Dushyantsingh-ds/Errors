# Errors

## 'ObjectContent`1' type failed | .NET Web API  
<details>
  <summary>Click to expand!</summary>
  
```
<Message>An error has occurred.</Message>
<ExceptionMessage>The 'ObjectContent`1' type failed to serialize the response body for content type 'application/xml; charset=utf-8'.</ExceptionMessage>
<ExceptionType>System.InvalidOperationException</ExceptionType>
<StackTrace/>
```
Solution: <br>
Add this to the WebApiConfig class under the Register Method.
```
var json = config.Formatters.JsonFormatter;
json.SerializerSettings.PreserveReferencesHandling=Newtonsoft.Json.PreserveReferencesHandling.Objects;
config.Formatters.Remove(config.Formatters.XmlFormatter);
```
<br/><br/>
</details
