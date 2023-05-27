# Thoughts on Nostr

## TL;DR:

1. Choice of crypto: Nostr picked the “Bitcoin crypto starter pack”. But what is good for blockchain may be bad for the network: it is ultra-slow, bad on key reuse (which is unavoidable for social networking) and non-standard in the digital identity world (incompatible with PGP/SSH).
2. Choice of javascript-style (no data typing): vectors for DoS attacks, slow speed, low extensibility.
3. No end-to-end encryption.

Overall: very vulnerable to DoS, secret key leaking, incompatible with other decentralized identity schemata, and will have scalability problems.

## Details

Nostr is a WebSockets-based text protocol for logs of authenticated (but unauthorized) tagged (and otherwise unstructured) messages stored at public relay servers. The rest is a specific Nostr application (like social networking or payments) on top of it.

Nostr takes several decisions on possible tradeoffs, which I try to analyze here:

1. Websockets. Good: pub/sub data access, web-integratable. Bad: high load on relay servers limiting scalability. Verdict: ⚠️
2. Elliptic curve (secp256k1) for identities. Good: bitcoin-based. Bad: very low performance, not GPG/SSH compatible, side-channel attacks are possible. Overall: ❌.
3. Signature scheme: BIP-340 Schnorr. Good: batch verification, standard. Bad: optimized for on-chain, discarding y-coord, making verification \~50% more expensive than non-BIP Schnorr, [vulnerable to leaking secret keys when the same public key is reused (tens, hundred) thousand of times](https://t.co/JOycV21Qub). Verdict: ❌
4. Hashing function: SHA256. Good: standard, bitcoin. Bad: slower than BLAKE3. Verdict: ⚠️
5. Text JSON encoding. Good: easy to implement. Bad: hard to pass & slow to encode/decode non-text/binary data; no limits on data sizing opening a door for DoSing relays and clients. Verdict: ❌
6. No authorization scheme. Good: easy to implement. Bad: limits use cases, limits scalability. Verdict: ⚠️
7. No encryption on the transport level, relying on TLS. Good: easy to implement. Bad: centralized, not end-to-end. Verdict: ⚠️

So I see most of the selected tradeoffs by Nostr as a bad or poor decision. This us arguable of course.

Can Nostr survive and succeed? For sure, if even much worse systems had done that in the past (Ethereum, JavaScript, PHP).

What is the greatest Nostr weakness? Limited scalability and possible DoS (not even DDoS) attacks.

If I were the one who did Nostr, what I would have made differently? I would have used Ed25519 signatures on Ristretto25519 (speed), binary encoding with strict limits on data sizes, use Noise\_XK encryption - and provide bridges to WebSockets only when they are needed for the web. But we have what we have.

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>
