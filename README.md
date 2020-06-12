# HushChat - Signal-like Protocol on Hush

<img src="https://raw.githubusercontent.com/MyHush/hushchat/master/hushchat-screen.png">

## What is HushChat?

HushChat is a protocol which is a particular use case of HushList protocol and which sits on top of Zcash Protocol. It is
inspired by the design of Signal Protocol and uses many of the same cryptography and ideas, but does not actually use any
code from Signal.

## Is HushChat only compatible with HUSH mainnet?

No, it's designed to run on any compatible Zcash Protocol chain, including all Hush Smart Chains:

https://github.com/myhush/hush-smart-chains

That being said, HushChat is being developed soley on HUSH mainnet. Other cryptocoins are encouraged to read our open source code and port it to their codebases.

## Is HushChat a fork of Signal?

No. We do not use code directly from Signal, but the ideas from the protocol and ideas/concepts from the GUI interface.

## Why not just use Signal?

Signal requires phone numbers and is a centralized service. HushChat is completely anonymous and decentralized and requires absolutely no metadata be given to any centralized third parties.

Features of HushChat:

  * No phone numbers
  * No centralized web servers
  * No US-based organization
  * No Javascript in our desktop full or lite wallets
  * Multiple layers of encryption, in-flight and at-rest
  * Compatible with Tor (i2p support in progress)
 
  
## What kind of interfaces will there be to HushChat?

In order of development:

  * Lite mode desktop
  * Android Mobile
  * Full mode desktop
  * iOS Mobile

The Lite mode desktop version is nearing it's first release.
 

## What is HushList?

HushList is a protocol first published in 2017, which describes how to use Zcash Protocol for various communications use cases,
including censorship-resistance: https://github.com/leto/hushlist/blob/master/whitepaper/protocol.pdf

HushChat is basically one specialized way to use HushList Protocol, focused on near-real-time chat versus mailing list style
communicaitons. The world is increasingly chat-based versus email-based and HushChat is a response to that.

## Will HushChat store messages on the blockchain like HushList does?

Yes, data must be stored on-chain to have censorship resistance and HushChat can be thought of as a "flavor" of HushList.
Users may choose between storing data on the *public* Hush blockchain or their own Hush Smart Chain (which could be public or completely private) : https://github.com/myhush/hush-smart-chains

## Isn't it a bad idea to store private data in a blockchain?

It depends on the needs of the user. Currently, many users give all their information for free to various cloud companies
who constantly mine their personal data which can then be sold to advertising companies who want to influence thinking and purchases. These average users have a lot to benefit from controlling their data, wrapping it in multiple layers of encryption and enjoying censorship-resistance. For those with more strict needs (say a Healthcare company), a dedicated Hush Smart Chain
with access controls, such as needing to be on a certain VPN with a special user/pass to connect to the network, could be used.

Ultimately, to prove to others that something happened or to easily communicate with others, a public blockchain will be the primary use case. It also provides a meeting place for users to come together and then spin up their own Just-In-Time specific-use-case blockchains.

Additionally, if somebody is trying to say false things about you, selectively disclosing data that proves your innocence
can be very valuable. HushChat enables this use case, which Signal cannot possibly implement. Because Hush is backed up by Bitcoin hashrate security, the data cannot be censored or modified once it is notarized.

## Are you rolling your own crypto like stupid people?

No. We use the industry standard libsodium to provide cryptographic primitives:

https://download.libsodium.org/doc/

Specifically, we use these parts of libsodium:

  * Key Exchange
  * Secretstreams
  * Password Hashing API (Argon2id)
  
and potentially others. In terms of cryptographic hash functions, Blake2B and SHA256 are used directly and internally by various
libsodium functions. 

## How does HushChat protect my privacy?

Glad you asked!! HushChat adds various layers of privacy on top of our "base" Zcash Protocol, heavily using libsodium.

  * Every HushChat has per-conversation encryption
    * This means that every time Alice talks to a new Bob, they have unique encryption keys compared to every other chat.
  * Every HushChat conversation constantly "ratchets"
    * The shared keys to each conversation constantly change, providing "forward secrecy"
    * If you can steal the secret keys to one chat, it won't decrypt future chats nor can you impersonate future chats
  * HushChat Lite wallets have *FULL* wallet.dat encryption, leaving no plaintext accessible
    * A wallet.dat at rest therefore has two layers of encryption, wallet-level and chat-level
  * Every HushChat is additionally encrypted with a user passphrase, independent of wallet.dat private keys
    * This means if your device is seized/liberated/stolen and your wallet.dat inserted in ChainAnalysis or similar blockchain analysis platform, your chats are encrypted blobs of useless information
  * HushChats cannot be truncated, removed, reordered, duplicated or modified without being detected
    * There are very strong encryption/decryption guarantees provided by libsodium secretstreams: https://doc.libsodium.org/secret-key_cryptography/secretstream



  
## Where can I learn more?

Join our Discord: https://myhush.org/discord
