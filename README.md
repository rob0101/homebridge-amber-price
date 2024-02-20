# Homebridge-Amber-Price

Homebridge-Amber-Price is a project forked from [anon1y4012/homebridge-energy-price](https://github.com/anon1y4012/homebridge-energy-price). This version has been modified to talk to the API of Amber Electric in Australia

## Installation

The easiest installation method is to use Homebridge-Config-UI-X and search for this plugin.

If you want to install manually, you can run the following commands:

```bash
sudo npm install -g homebridge
sudo npm install -g homebridge-amber-price
```

**Note:** If you install homebridge using the following command:

```bash
sudo npm install -g --unsafe-perm homebridge
```

All subsequent installations must follow the same format, like this:

```bash
sudo npm install -g --unsafe-perm homebridge-amber-price
```

## Configuration

You will need to add the following example accessory configuration to your homebridge `config.json`:

```json
"accessories": [
    {
         "name": "Amber Price",
            "manufacturer": "Amber",
            "model": "Amber Price Monitor",
            "apiKey": "=== your API Key here ====",
            "apiId": "=== Your API Site ID here ====",
            "refreshInterval": 5,
            "accessory": "Energy Price"
    }
]
```

### Configuration Explanation

Field | Description
----- | -----------
**accessory** | (required) Must always be "Energy Price".
**name** | (required) The name you want to use for the power level widget.
**manufacturer** | (optional) This shows up in the HomeKit accessory characteristics.
**model** | (optional) This shows up in the HomeKit accessory characteristics.
**refreshInterval** | (required) The refresh interval in minutes for polling Amber.
**apiID** | (required) Your Amber API ID (Site ID)
**apiKey** | (required) Your Amber API Key starts with psk_

### Obtaining your API Key

1. Visit https://app.amber.com.au/ and log in
2. Click on "Settings"
3. Enable "developer mode"
4. Follow the link to the "For Developers" to see the developer documentation
5. Generate a token - You can name this Homebridge or anything meaningful
6. Copy the token and enter as your apiKey in your configuration
   
### Obtaining your API ID (Site ID)

From where you obtain your API key, there are a series of documented API calls

1. Click on Authorize and in the Value, provide your apiKey / token you generated as the value and click Authorize
2. Click on the "GET /sites"
3. Hit "Try it out"

Note: The documentation shows a response which is an example of the response. This does not show your Site ID. You may need to view your network calls using your browsers developer mode in order to see the network request and response. You will need to obtain the "id" in the resulting array of site objects returned. 
