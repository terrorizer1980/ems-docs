# Configuring Dimension Integration Manager

## Known Issues

The Dimension Integration Manager ships with a number of integrations that do not work in an on-premise environment. The following integrations are known to work with proper internet connectivity:

- Jitsi Widget
- Hookshot Frontend

Please note that we recognise this situation is less than ideal. We will be working to improve the situation around integrations in the near future.

## On the hosting machine

- Copy sample file from `config-sample/dimension/dimension.yml` to
 `extra-config/dimension`
- Edit the file with the following values :
  - `ems_bridges_registry_username`: ems bridges registry token name
  - `ems_bridges_registry_password`: ems bridges registry token password
  - `dimension_fqdn`: The access address to dimension. It should match
    something like `dimension.<fqdn.tld>`
  - `admins`: List of mxids with admin access to dimension
  - `widget_blocklist`: CIDRs listed here will be blocked from becoming
    widgets.
  - `postgres_fqdn`: PostgreSQL server fqdn or ip
  - `postgres_user`: PostgreSQL username
  - `postgres_db`: PostgreSQL dimension database
  - `postgres_password`: PostgreSQL dimension password
  - `bot_data_size`: The size of the space allocated to bot data.
  - `bot_data_path`: The path on the hosting machine to the space allocated
    to bot data
- Restart the install script

## On element

- Copy sample file from `config-sample/element/dimension.json` to
 `extra-config/element`
- Edit the file to replace `< dimension_fqdn >` to your dimension instance
 fqdn.
- Restart the install script

## Enabling BigBlueButton

To enable BigBlueButton integration into Element through Dimension, you
should set the following variables.

- `bbb_api_base_url`: The full base URL of the API of your BigBlueButton
 instance
- `bbb_shared_secret`:  The "shared secret" of your BigBlueButton
 instance. This is used to authenticate to the API above.
- `bbb_widget_name`:  The title for BigBlueButton widgets that are generated
 by Dimension.
- `bbb_widget_title`: The subtitle for BigBlueButton widgets that are
 generated by Dimension.
- `bbb_widget_avatar_mxc`:  The avatar for BigBlueButton widgets that are
 generated by Dimension. Usually this doen't need to be changed, however if
 your homeserver is not able to reach t2bot.io then you should specify your
 own here.
