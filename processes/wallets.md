# Wallet Process

This process contains all wallets operated by the RPCh team.

## Wallets

| Wallet Address | Alias | Description |
| - | - | - |
| 0xD720099cBC14e669695EaE0708E6Ca614B387921 | RPCh dev bank | RPCh's bank: used to transfer funds to other wallets |
| 0x01BFbCB6A2924b083969ce6237AdBbF3BFa7De13 | RPCh alpha deployer | Funding and registering HOPRd nodes for Alpha |
| 0xDCcC4a8ee2BF3CaF5a4AB1cDBa1ee7cc04E324Dd | RPCh deployer | Funding and registering HOPRd nodes |

## Policy

HOPR Association [multi-sig](https://etherscan.io/address/0x4f50ab4e931289344a57f2fe4bbd10546a6fdc17) is the main address where all HOPR related funds are stored and controlled.

All other wallets defined in [wallets](#Wallets) are or had been in control of Association contributors or HOPR Services AG employees. As they are controlled via private keys, mainnet funds are usually short-live and communicated internally.

All assets, current or future, that exist in [wallets](#Wallets), independently of the blockchain they live on, should be considered Association property and can only be used for development purposes. When their purpose is complete, they should be sent back to the Association.

Additional wallets that are not defined under the [wallets](#Wallets) have no connections to the Association whatsoever, and are the sole responsibility of their owners, independently of their relationship with the Association.

No HD-derived wallets (e.g. mnemonics) are used for HOPR Association as having the seed of this wallet would grant access to private keys that could be used further down the line w/o being aware of that being the case.
