# What is it

Script nonce is a feature used for security purposes in web applications. Nonce (number used once) is an abbreviation and represents a randomly generated value. Script nonce is specifically used to prevent Cross-Site Scripting (XSS) attacks.

Script nonce is employed to enable the execution of JavaScript code on web pages. It is a randomly generated value created by the server of the web page, and this value is added to the page through the "nonce" attribute of the JavaScript tag. The nonce value is required for loading and running JavaScript files.

Script nonce is a security mechanism implemented by web browsers. Browsers allow JavaScript code added to a page only from sources (e.g., the server) that have a specific nonce value. This prevents the execution of malicious code injected by XSS attackers.

# How It Works

A web application should generate a random nonce value for each request and add this value to the "nonce" attribute of the JavaScript tag. On the server side, this nonce value needs to be added to the HTTP responses as well. Consequently, browsers execute only JavaScript files that have the correct nonce value and block others.

Script nonce is an effective mechanism for preventing security vulnerabilities in web applications. When browsers support this method, it enables web developers to design their applications securely and protect against XSS attacks.

![image](https://github.com/salihozkara/MD/assets/58659931/9751cf17-870e-473b-8754-d729e598d5cc)

# Abp Approach

Abp adds the nonce value to the HTTP headers through the `AbpSecurityHeaderMiddleware`. Later, this value is added to the "nonce" attribute of the JavaScript tag via the `NonceScriptTagHelper`. In some pages or situations, it may be undesired to use this feature. In such cases, the `ScriptNonce` property can be disabled through the `AbpSecurityHeaderMiddleware`.

```csharp
Configure<AbpSecurityHeaderOptions>(options =>
{
     //ignore script nonce source for these paths
    options.IgnoredScriptNoncePaths.Add("/my-page");

    //ignore script nonce by Elsa Workflows and other selectors
    options.IgnoredScriptNonceSelectors.Add(context =>
    {
        var endpoint = context.GetEndpoint();
        return Task.FromResult(endpoint?.Metadata.GetMetadata<PageRouteMetadata>()?.RouteTemplate == "/{YOURHOSTPAGE}");
    });
});
```

# How to Activate

By default, this feature is not enabled in Abp. To activate it, `AbpSecurityHeaderOptions` needs to be configured.
And `AbpSecurityHeaderMiddleware` should be activated with `UseAbpSecurityHeaders`.

## ConfigureServices

```csharp
Configure<AbpSecurityHeaderOptions>(options =>
{
    options.UseContentSecurityPolicyScriptNonce = true;
});
```

## Configure

```csharp
app.UseAbpSecurityHeaders();
```
