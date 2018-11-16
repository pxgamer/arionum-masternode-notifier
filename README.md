# arionum-masternode-notifier

[![Software License][ico-license]](LICENSE)

Send email notifications when a masternode IP address receives a reward.

## Install

1. Clone the github repository to a directory.
1. Enter the required details in [the configuration file](config.php).

## Usage

>The node you are monitoring MUST have its API enabled, as the wallet balance uses the node's API.
>This can be found in the node configuration.

Run this script using tmux to keep it running after you logoff the VPS.

```bash
$ cd mn-notifier
$ tmux new -s sessionname
$ php mn-notifier
```
    
You can now logoff and the script will continue running to notify you when the masternode wins a block.

## License

The GNU General Public License v3.0 (GPL-3.0). Please see [License File](LICENSE) for more information.

[ico-license]: https://img.shields.io/badge/license-GPL3-brightgreen.svg?style=flat-square
[link-contributors]: ../../contributors
