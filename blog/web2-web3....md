# Web2, Web3...

Let’s start with defining Web itself. My take:&#x20;

[#Web](https://snort.social/t/Web) is a computing platform - like POSIX, Windows, Java, embedded etc. Web differs from the Internet the same way Windows differs from BIOS.&#x20;

As a computing platform Web brings a number of protocols, toolchains, SDKs and technologies:&#x20;

1. Networking is restricted to the TCP/IP subset: HTTP(s), WebSocket and WebRTC.
2. Supported instruction set architectures: WASM, JavaScript virtual machine(s), both browser- and server (NodeJS)-based.
3. UI uses HTML, CSS, DOM, WebGL, and Canvas. On top of that UI frameworks proliferate - like in the POSIX world, we have Qt, GTK etc in the Web world we have React, Angular, Vue, Svelte etc.

Why Web is so popular? It was the first computing platform created in the age of networking - and for network-based apps first. It allows you to run apps without installing them - and do that on any consumer UI-based device: desktop, laptop or mobile. It allows the simple creation of cross-platform apps. It avoids censorship of app stores.&#x20;

The drawbacks of the Web are mostly direct consequences of its advantages:&#x20;

* low security: a remote code is executed locally;
* privacy leaks as a result of the client-server model;
* agility allowing cross-platform UI and schema-less network messaging results in “spaghetti code” and wired JavaScript VM non-determinism;
* poor decentralization and censorship resistance: an inherited client-server model doesn’t allow proper decentralization.&#x20;

The Web passed through generations: Web, Web2 - and now "Web3" is kinda there.&#x20;

The main difference between Web and Web2 was:&#x20;

* interactivity (brought through JavaScript AJAX, and later WebSockets);
* dynamic UI (with JavaScript DOM manipulations);
* abandoning Java applets;
* local storage for app data provided by web browsers;
* move from CGI to custom web servers with embedded server-side business logic (NodeJS, Python and web frameworks in almost every language);
* better markup languages (HTML5, CSS3), including graphic markup (SVG, Canvas, WebGL).

What people were looking for in the post-Web2-era etc?&#x20;

* better decentralization and censorship resistance;
* integration of native internet money and payment methods;
* smart contracts (complex automation based on cryptographic and economic incentives);
* better privacy.

Does Web3 on that? No: it promises to deliver, but fails: there can’t be privacy nor scalability with blockchain-based things; there can’t be censorship-resistance with PoS; there can’t be decentralization with the old client-server hosting of content.

What should the proper “next Web” look like?&#x20;

* be based on P2P (where is possible) or relay-based systems (where P2P is impossible); with relays being self-hosted;
* end-to-end encrypted communications
* over Mix networks (Tor, Nym, I2P etc);
* authentication based on public key cryptography (and not passwords) and decentralized identities (SSH, GPG and future systems);
* based on a zero-knowledge state; i.e. not leaking privacy data to the web servers or nodes;
* using deterministic functional computing;
* using PoW and bitcoin single-use-seals - but not for storing a state like in Web2 (!); only for cryptographic commitments (OTS etc);
* using client-side-valdiated smart contracts like RGB;&#x20;
* integrated with Lightning payments and [#BiFi](https://snort.social/t/BiFi) (bitcoin finance);
* using decentralized data protocols like [#Storm](https://snort.social/t/Storm), [#Slashtags](https://snort.social/t/Slashtags), [#Nostr-based](https://snort.social/t/Nostr-based) and like solutions.&#x20;

I call this future **Web4**, and we are working on it at [LNP/BP Standards Association](http://localhost:5000/o/-MO35HartFKtUgrkgzLy/s/-McfDPD66AVSPTr3V62W/), [Pandora Prime](http://localhost:5000/o/-MO35HartFKtUgrkgzLy/s/Blh0PdjVf3XiYzSfpSyZ/),  together with partner projects, doing things like mixnets, end-to-end encryption, [#reNostr](https://snort.social/t/reNostr), [#Storm](https://snort.social/t/Storm), [#RGB](https://snort.social/t/RGB) smart contracts and other exciting projects. Everyone is welcome to check one of the releases we did this year: [cyphernet](https://github.com/Cyphernet-DAO/rust-cyphernet/), a Rust library providing support for mixnets and pure rust implementation of Noise E2E encryption.
