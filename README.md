# Nuts Collections

Website: [nuts.family](nuts.family)

## Nuts.sol

ERC-721 Non Fungible Token (NFT) contract deployed with OpenZeppelin and Remix on Ethereum: [0x88266f9eb705F5282a2507A9c418821a2AC9f8BD](https://etherscan.io/token/0x88266f9eb705F5282a2507A9c418821a2AC9f8BD)

## Nuts404.sol

Contract deployed with OpenZeppelin and Remix on Ethereum: [0x25559f0abbaf2a928239d2f419181147cc2dad74](https://etherscan.io/address/0x25559f0abbaf2a928239d2f419181147cc2dad74)

This contract converts Nuts NFT ERC-721 standard to ERC-20 standard by locking Nuts NFT into the contract and minting 1:1 backed ERC-20 token, that can then be redeemed at any time:

**Nuts (NUTS) <> Nuts404 (NUTS404)**

Nuts404 is built on a generic abstract contract called **W404** based on OpenZeppelin libraries (ERC-20, ERC-721, DoubleEndedQueue) and inspired from Pandora "ERC"404 experimental format.

**WARNING**: Current implementation of wrapping & unwrapping does not guarantee to get back to the same ERC-721 token(s) initially deposited. As unwrapping is implemented to withdraw the Nuts ERC-721 token(s) corresponding to the tokenId(s) stored on the back of the queue.
