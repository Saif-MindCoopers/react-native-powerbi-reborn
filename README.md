# PowerBI Embed for React Native

This component opens embeded PowerBI reports. It uses the WebView on Android and iOS the display them. This package is compatiable with new architecture of react-native (v0.70).

## Installation

```
$ npm install --save https://github.com/mindcoopers-prod/react-native-powerbi-reborn.git
```

## Usage

`import PowerBIEmbed from 'react-native-powerbi-reborn';`

For a report to display you need at least three parts: AccessToken, Embed URL and the ID of the report. (these can be obtained thru the rest api)

```javascript
<PowerBIEmbed
  accessToken="H4sIAAAAAAAEACVW...NH8v_8HNiWyTi4LAAA="
  embedUrl="https://app.powerbi.com/reportEmbed?reportId=bac25fa7-d58d-40b6-8b01-606d165c3b43&groupId=be8908da-da25-452e-b220-163f52476cdd"
  id="bac25fa7-d58d-40b6-8b01-606d165c3b43"
/>
```

#### Language

You can also pass the language the report must use

```javascript
<PowerBIEmbed
  accessToken="H4sIAAAAAAAEACVW...NH8v_8HNiWyTi4LAAA="
  embedUrl="https://app.powerbi.com/reportEmbed?reportId=bac25fa7-d58d-40b6-8b01-606d165c3b43&groupId=be8908da-da25-452e-b220-163f52476cdd"
  id="bac25fa7-d58d-40b6-8b01-606d165c3b43"
  language="en"
/>
```

#### Embed configuration

You can pass your own configuration object from the [PowerBI JS library](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details)

```javascript
const config = {
      type: 'report',
      tokenType: 1,
      accessToken: "H4sIAAAAAAAEACVW...NH8v_8HNiWyTi4LAAA=",
      embedUrl: "https://app.powerbi.com/reportEmbed?reportId=bac25fa7-d58d-40b6-8b01-606d165c3b43&groupId=be8908da-da25-452e-b220-163f52476cdd",
      id: "bac25fa7-d58d-40b6-8b01-606d165c3b43",
      settings: {
        filterPaneEnabled: false,
        navContentPaneEnabled: true,
      },
    }

    <PowerBIEmbed
      embedConfiguration={config}
    />
```

supports webview onShouldStartLoadWithRequest
