
# Cardano Example Dapp

## **Multisig using Unimatrix and Roundtable**

Builds 3 multisig transactions and tries to sign them only with local private keys and with remote signers using Unimatrix Sync and Roundtable. Customize required keys to real ones or experience a Kobayashi Maru scenario


## Try it online: 

-  Visit [HTML5 Dapp](https://gamechangerfinance.github.io/gamechanger.wallet/examples/Multisig%20using%20Unimatrix%20and%20Roundtable.html)
-  Run [Standalone URL dapp connection](https://beta-wallet.gamechanger.finance/api/2/run/1-H4sIAAAAAAAAA5VTTU_cMBD9K1YutBJCSZxPbgsXpAoJdal6QAhN7MmuRWJvbafNdrX_vePsAqEIJG6ZeW_85s1MdpFXvsPoPLoeOq-cWrHBKb1iP7TqwVs1MtCSfTeDlh4aYp5GEp2wauOV0VR3MahOOsZZ__SAt6AdiIC7qZqeQce8YYRq5tfYM6O7Lfuj_Jp1RkDHNlb9Bo_sEbeHmgmz2BtKhjK07k1ny60W_7V3xi4H502v_iJV_xqURXl4lOQtkpLR1IuxDMcNUl9aIAP2zTSwBbdW7BrswJxADVYZMks0Y_3CkdMng5S16AdL7ndRb2SYXgfOR_vTyG83ITwMKBCHidWEISXh60iYErcjMfwY0k-9Lg9WQ2rRKRGoCceaQ1aJouBpKsu6FbLiMq-SNuVZ1eRFGfMaGi7rqmrbShZpVVAU7ffU0CSUfk75wjREzISMW0DgaQy8wkxkNfJUiiyWbdJA1lQIsomxzQRP8jQVXIi8aJOZLv-c7uUabIdh1BWHnOeJLKs6SbK8LOK2rQtMa8HLHDLO87yJq1zmMU94g2lRyKwuy6PncC8z5RDejo6UNfR4A95j2F207MF6tkQtp6P2oDqUN2h75Vy43ei8hc7h6cviz-920aMiPv0uoPRCSovO0d6f05eDtaj9T2Mf3QZofzPs1U_kyCs15-2AgaLk7MAeEloscY51zwf_uuwYBGfHGLQmCUGpK7plPOb392HkFNxFuxX6LycCxBrPDid55scrHE--7untN2j6Icpf0Psw9KHplZ-PfUocBj_pv3oiLCWUUmWrNHTddlbag7Dm5e_xk5_3DRD4kYP3YT6D7-l09v8AJfzlaQ8FAAA)

## Source code:

- dapp connection code: [GCScript](Multisig%20using%20Unimatrix%20and%20Roundtable.gcscript)
- frontend + dapp connection code : [HTML5 dapp](Multisig%20using%20Unimatrix%20and%20Roundtable.html)

Dapp code was autogenerated by [Playground IDE in GameChanger Wallet ](https://beta-wallet.gamechanger.finance/playground)

## GCScript code (dapp connection):
```json
{
  "title": "Multisig using Unimatrix and Roundtable",
  "description": "Builds 3 multisig transactions and tries to sign them only with local private keys and with remote signers using Unimatrix Sync and Roundtable. Customize required keys to real ones or experience a Kobayashi Maru scenario",
  "exportAs": "multisig",
  "return": {
    "mode": "last"
  },
  "type": "script",
  "run": {
    "build1": {
      "type": "buildTx",
      "tx": {
        "requiredSigners": {
          "Alice": "13e93a48c66322d79fcd83d581f2348b567039ab3d988ff8d6286b3d"
        }
      }
    },
    "build2": {
      "type": "buildTx",
      "tx": {
        "requiredSigners": {
          "Bob": "4cd0faea320a38e4c49e32dc40df1ba4b8eadb0ef4c31522c3cc56f1"
        }
      }
    },
    "build3": {
      "type": "buildTx",
      "tx": {
        "requiredSigners": {
          "Charles": "83a5351d7891145760ff96e29c375a43355b085d50313be266d4977d"
        }
      }
    },
    "sign": {
      "type": "signTxs",
      "namePattern": "Smart Send",
      "detailedPermissions": false,
      "multisig": [
        {
          "kind": "MainAddress"
        },
        {
          "kind": "CurrentWorkspace"
        },
        {
          "kind": "Roundtable",
          "share": true
        },
        {
          "id": "multisig_1234",
          "kind": "Unimatrix",
          "share": true,
          "shareTxs": true,
          "announceTxHashes": true
        }
      ],
      "txs": [
        "{get('cache.build1.txHex')}",
        "{get('cache.build2.txHex')}",
        "{get('cache.build3.txHex')}"
      ]
    },
    "submit": {
      "type": "submitTxs",
      "txs": "{get('cache.sign')}"
    },
    "finally": {
      "type": "macro",
      "run": {
        "txHash": [
          "{get('cache.build1.txHash')}",
          "{get('cache.build2.txHash')}",
          "{get('cache.build3.txHash')}"
        ]
      }
    }
  }
}
```

## Run standalone QR dapp connection: 

You can use [Playground IDE in GameChanger Wallet ](https://beta-wallet.gamechanger.finance/playground) in `QR URL Transport` mode to capture results

[![This GCScript/URL is too large! make it shorter uploading parts to GCFS. Unable to generate QR code](Multisig%20using%20Unimatrix%20and%20Roundtable.png)](https://gamechangerfinance.github.io/gamechanger.wallet/examples/Multisig%20using%20Unimatrix%20and%20Roundtable.png)

## Resources
- [Github Docs and examples](https://github.com/GameChangerFinance/gamechanger.wallet/)
- [GCScript documentation](https://beta-wallet.gamechanger.finance/doc/api/v2/api.html)
- [Playground IDE in GameChanger Wallet ](https://beta-wallet.gamechanger.finance/playground)
- [Youtube Tutorials](https://www.youtube.com/@gamechanger.finance)
- [Discord Support](https://discord.gg/vpbfyRaDKG)
- [Twitter News](https://twitter.com/GameChangerOk)
- [Website](https://gamechanger.finance)

## License
MIT 
    