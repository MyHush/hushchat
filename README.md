# HushChat - Signal On A Blockchain


## What is HushChat?

HushChat is a protocol which is a particular use case of HushList protocol and which sits on top of Zcash Protocol. It is
inspired by the design of Signal Protocol and uses many of the same cryptography and ideas, but does not actually use any
code from Signal.

## Is HushChat a fork of Signal?

No. We do not use code directly from Signal, but the ideas from the protocol and the GUI interface.

## Why not just use Signal?

Signal requires phone numbers and is a centralized service. HushChat is completely anonymous and decentralized.

## What is HushList?

HushList is a protocol first published in 2017, which describes how to use Zcash Protocol for various communications use cases,
including censorship-resistance: https://github.com/leto/hushlist/blob/master/whitepaper/protocol.pdf

## Will HushChat store messages on the blockchain like HushList does?

Yes, data must be stored on-chain to have censorship resistance and HushChat can be thought of as a "flavor" of HushList.
Users may choose between storing data on the *public* Hush blockchain or their own Hush Smart Chain (which could be public or completely private) : https://github.com/myhush/hush-smart-chains

## Isn't it a bad idea to store private data in a blockchain?

It depends on the needs of the user. Currently, many users give all their information for free to various cloud companies
who constantly mine their personal data which can then be sold to advertising companies who want to influence thinking and purchases. These average users have a lot to benefit from controlling their data, wrapping it in multiple layers of encryption and enjoying censorship-resistance. For those with more strict needs (say a Healthcare company), a dedicated Hush Smart Chain
with access controls, such as needing to be on a certain VPN with a special user/pass to connect to the network, could be used.

Ultimately, to prove to others that something happened or to easily communicate with others, a public blockchain will be the primary use case. It also provides a meeting place for users to come together and then spin up their own Just-In-Time specific-use-case blockchains.

## Are you rolling your own crypto like stupid people?

No. We use the industry standard libsodium to provide cryptographic primitives:

https://download.libsodium.org/doc/

## Where can I learn more?

Join our Discord: https://myhush.org/discord
