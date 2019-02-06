# Mailclient

[![CircleCI status](https://img.shields.io/circleci/project/github/uubk/mailclient/master.svg?style=shield)](https://circleci.com/gh/uubk/mailclient/tree/master)
![License](https://img.shields.io/github/license/uubk/mailclient.svg?style=popout)
This role configures postfix in basic relay mode.

## How to use
To use this, you'll need an existing mailserver and some way to authenticate to it. Defaults are for GSSAPI with host keytab, but user+password fallback should also be possible. Postfix will then listen on localhost, accept any mail, rewrite the sender address and hand it of to the relay.

## Configuration
| Name | Default value | Description |
| ---- | ------------- | ----------- |
| `mailclient_sender` | `False` | Mail source is rewritten to sender@domain |
| `mailclient_domain` | `False` | The base domain this system belongs to |
| `mailclient_system_owner` | `False` | All system mail (see below) will be redirected owner@domain |
| `mailclient_to_redirect` | (see defaults/main.yml) | Which accounts to redirect mail for? |
| `mailclient_relay` | `False` | Relay mail over this system (postfix relayhost syntax) |
| `mailclient_rewrite_from_header` | `False` | Rewrite the `From:` header on outgoing mails |
| `mailclient_auth_enable` | `yes` | Whether to authenticate at the relay host |
| `mailclient_auth_mechanism` | `gssapi` | How to authenticate with the relay host |
| `mailclient_auth_credentials` | (see defaults/main.yml) | Login for the relay host |

## License
GPLv3
