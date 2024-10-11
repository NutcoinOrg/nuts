# Nuts NFTs Collections

Website: [nuts.family](https://nuts.family)

## Nuts.sol

ERC-721 Non Fungible Token (NFT) contract deployed with OpenZeppelin and Remix on Ethereum: [0x88266f9eb705F5282a2507A9c418821a2AC9f8BD](https://etherscan.io/token/0x88266f9eb705F5282a2507A9c418821a2AC9f8BD)

**EDIT: You can use our friendly GUI to burn your NUT for minting NUTS NFTs, now available here: [nuts.family/en/#mint](https://nuts.family/en/#mint) or here: [app-nuts-family.netlify.app/#/mint](https://app-nuts-family.netlify.app/#/mint)**

## Nuts404.sol

Contract deployed with OpenZeppelin and Remix on Ethereum: [0x25559f0abbaf2a928239d2f419181147cc2dad74](https://etherscan.io/address/0x25559f0abbaf2a928239d2f419181147cc2dad74)

This contract converts Nuts NFT ERC-721 standard to ERC-20 standard by locking Nuts NFT into the contract and minting 1:1 backed ERC-20 token, that can then be redeemed at any time:

**Nuts (NUTS) <> Nuts404 (NUTS404)**

Nuts404 is built on a generic simple abstract contract called **W404** based on OpenZeppelin libraries (ERC-20, ERC-721, DoubleEndedQueue) and inspired from Pandora "ERC"404 experimental format.

**WARNING**: Current implementation of wrapping & unwrapping does not guarantee to get back to the same ERC-721 token(s) initially deposited. As unwrapping is implemented to withdraw the Nuts ERC-721 token(s) corresponding to the tokenId(s) stored on the back of the queue.

### Usage

**EDIT: You can use our friendly GUI to (un)wrap your NUTS NFTs, now available here: [nuts.family/en/#wrap](https://nuts.family/en/#wrap) or here: [app-nuts-family.netlify.app/#/wrap](https://app-nuts-family.netlify.app/#/wrap)**

**WARNING: The following manual instructions are unsafe as they do not perform safety checks on the inputs you will provide to the Smart Contract and might cause a loss of assets. Recommended for advanced devs knowing what they are doing. (If you're a beginner, please use the GUI link provided above)**

There are several ways to (un)wrap your NUTS with this contract (using web3/ethers scripts, etc). The following instructions represent just an example using Etherscan as a Web3 provider to interact with Nuts404.sol smart contract:


1. **Approval:** On [NUTS Contract](https://etherscan.io/address/0x88266f9eb705f5282a2507a9c418821a2ac9f8bd#writeContract#F5), connect you wallet, call `setApprovalForAll` method allowing transfering NUTS for the Nuts404 Wrapper Contract (/!\ it will be for all your current and future NUTS as long as the value is set to `true`):

```code
setApprovalForAll(
operator: 0x25559f0abbaf2a928239d2f419181147cc2dad74     (Nuts404 Wrapper Contract)
approved: true
)
```

2. **Wrapping:** On [NUTS404 Contract](https://etherscan.io/token/0x25559f0abbaf2a928239d2f419181147cc2dad74#writeContract#F2), connect you wallet, call `deposit` method in order to wrap NUTS NFTs into ERC20 tokens and set the `tokenIds` you want to wrap:

```code
deposit(
tokenIds: [0, 31, 15]    (in this example: NUTS #0, #31 and #15 that you own will be wrapped into ERC20 tokens called Nuts404)
)
```

Click on `write` button to launch the call.

3. **Unwrapping:**: [NUTS404 Contract](https://etherscan.io/token/0x25559f0abbaf2a928239d2f419181147cc2dad74#writeContract#F6), connect you wallet, call `withdraw` method in order to unwrap NUTS404 tokens into NUTS NFTs and set the integer `value` you want to unwrap:

```code
withdraw(
value: 3000000000000000000    (it will give you 3 NUTS NFTs but as said previously, it does NOT guarantee that it will be the #0, #31, #15 deposited previously)
)
```

Click on `write` button to launch the call.

**WARNING: It is not recommended to (un)wrap more than 100 NUTS NFTS in order not to get 'running out of gas' errors.**
