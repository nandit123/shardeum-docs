---
title: Lighthouse Storage and Encryption
sidebar_position: 4
---

## Decentralized Perpetual storage with Lighthouse

Lighthouse is a perpetual file storage protocol that allows the ability to pay once and store your files forever. Lighthouse store your data on IPFS and ensures minimum number of replications across various Filecoin miners, abstracting all complexities and long-term storage functionality. Developers can also store encrypted data on Lighthouse and build token gated applications.

## How to use Lighthouse

Website -  https://lighthouse.storage

Sign into [Files Dapp](https://files.lighthouse.storage/) with your wallet or your github account to start uploading files to Lighthouse

Optionally:
- Get [Lighthouse CLI](https://lighthouse-1.gitbook.io/lighthouse-1/cli-tool/overview)
- Get [Lighthouse Javascript SDK](https://lighthouse-1.gitbook.io/lighthouse-1/lighthouse-sdk/overview)
- Get [Python SDK](https://pypi.org/project/lighthouseweb3/)

## How to Save Encrypted Files
1. Upload Encrypted files via [Files Dapp](https://files.lighthouse.storage/)
2. Using [CLI](https://lighthouse-1.gitbook.io/lighthouse-1/cli-tool/cli-commands/deploy-encrypted)
3. Use our [Javascript SDK](https://lighthouse-1.gitbook.io/lighthouse-1/lighthouse-sdk/code-examples) into react.js / node.js


## Setup personalised Gateway for fast content retrieval

Dapps can use our dedicated IPFS gateway to retrieve files quickly and even stream 4k videos which are very data intensive 

Lighthouse supports dedicated gateways from [Files Dashboard](https://files.lighthouse.storage) giving you the low latency and fast file retrieval you need. 

You can get a custom domain like <b>custom_name</b>.lighthouse.storage/ for your project.

## Use Case: Mint an NFT on a Shardeum using Lighthouse

Shardeum logo hosted on IPFS and Filecoin using Lighthouse:

<img src="https://gateway.lighthouse.storage/ipfs/QmQkckbv9vCGTwQWLD1Kjnu7YCYwMzzjtiqM33vfb433Sk" alt="shardeumLogo" />

Mint NFT with Shardeum logo using ERC-721 imported OpenZeppelin library.

Note: put the IPFS CID: 

	QmQkckbv9vCGTwQWLD1Kjnu7YCYwMzzjtiqM33vfb433Sk
	
instead of the IPFS gateway URL:

    https://gateway.lighthouse.storage/ipfs/<CID>

since gateways can go down.

<Tabs>
  <TabItem value="solidity" label="Solidity" default>

    // SPDX-License-Identifier: MIT
    pragma solidity 0.8.17;

    import "@openzeppelin/contracts/token/ERC721/extensions/ERC721URIStorage.sol";

    contract ShardeumNFT is ERC721URIStorage {

      constructor() ERC721 ("shardeumNFT", "SL"){
        _safeMint(msg.sender, 1); // Mint NFT with tokenId = 1.
        _setTokenURI(1, QmQkckbv9vCGTwQWLD1Kjnu7YCYwMzzjtiqM33vfb433Sk); //For tokenId = 1, set IPFS CID for image data.
      }
    }
  </TabItem>
</Tabs>


## Further Resources
- Refer complete [Documentation](https://www.lighthouse.storage/documentation)
- Follow us on [Twitter](https://twitter.com/LighthouseWeb3)
- Join our [Discord](https://discord.com/invite/c4a4CGCdJG) for dedicated support
- Fill up this [Form](https://airtable.com/shrPFC2TgojuOAYO4) to apply for free storage and dedicated gateway
