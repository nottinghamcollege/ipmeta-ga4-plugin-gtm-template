# IPMeta Plugin for Google Analytics 4 (GA4)

Google Tag Manager template for the [IpMeta plugin](https://ipmeta.io/).

**Requires a valid IpMeta.io API key.**

## Prerequisites

1. IpMeta.io API key
2. Custom dimensions setup for `IpMetaServiceProvider`, `IpMetaNetworkDomain` and `IpMetaNetworkType`. [Installation guide](https://ipmeta.io/instructions/google-analytics-4)

Non-sandbox Custom HTML method:

```html
<script src="https://ipmeta.io/plugin.js"></script>

<script>
    IpMetaGa4({
        gtmEventKey: 'ipmeta_loaded',
        apiKey: 'YOUR-IPMETA-API-KEY',
    });
</script>
```

Google Tag Manager template method:

![image](https://github.com/nottinghamcollege/ipmeta-ga4-plugin-gtm-template/assets/8067792/515906eb-c242-4cc6-b5c8-f0d39f5a45a3)

The sandbox template takes care of loading the `https://ipmeta.io/plugin.js` script and calling the `IpMetaGa4` function with your API key to load the IpMeta plugin.

IpMeta when successfully loaded will raise an `ipmeta_loaded` event, you will need to link your Google Analytics GA4 configuration tag to this event as the trigger in order for the custom dimensions to be populated reliably (ensuring IpMeta was loaded before Google Analytics tags fire).



