# Home Assistant Home Connect

This is work in progress of an implementation of a Home Connect component for Home Assistant.

## Recent breaking changes

Note that the current version **requires Home Assistant 0.102 or newer**.

Also, you need to **change the redirect URI** compared to before: replace `.../api/homeconnect` by `.../auth/external/callback`

## Usage

- Register an account with the [Home Connect Developer Program](https://developer.home-connect.com)
- Register a new application with the Redirect URI `https://YOUR_HOMEASSISTANT_BASE_URL:PORT/auth/external/callback` (it will not work without https, but your Home Assistant instance does *not* have to be accessible from the internet and a self-signed certificate will do)
- Make sure the `http` component in your `configuration.yaml` has the base url set to `YOUR_HOMEASSISTANT_BASE_URL:PORT` (it will not work otherwise)
- Copy the contents of `custom_components` to the  `custom_components` directory of your Home Assistant configuration directory
- Add the following to your `configuration.yaml`:
```yaml
homeconnect:
  client_id: YOUR_CLIENT_ID
  client_secret: YOUR_CLIENT_SECRET
```
- Navigate to the Integrations page and select "Home Connect"

## Feedback

This is a development preview (**use at your own risk!**). Please report problems by [opening an issue](https://github.com/DavidMStraub/homeassistant-homeconnect/issues). Feel free to report success in the [Home Assistant forum](https://community.home-assistant.io/t/home-connect-alpha-testers-wanted/82603).

Pull requests are welcome!
