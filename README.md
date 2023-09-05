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
            "apiId": "=== Your API ID here ====",
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
**refreshInterval** | (optional) The refresh interval in minutes for polling ComEd. The default is 5 minutes.
**apiID** | (required) Your Amber API site ID
**apiKey** | (required) Your Amber API Key starts with psk_
