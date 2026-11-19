# Olm

> [!NOTE]
> Olm is being phased out in favor of the [Praxis CLI](https://github.com/CausQ-Networks/praxis-cli) and is only meant for advanced use cases.

Olm is the cross-platform internal networking library built into every Praxis client. It does the heavy-lifting of connecting the client to Praxis sites.

Don't use Olm as a standalone machine client. Instead, use the [Praxis CLI](https://github.com/CausQ-Networks/praxis-cli).

### Installation and Documentation

Olm is used with Praxis and Newt as part of the larger system. See documentation below:

-   [Full Documentation](https://docs.praxis.causq.com/manage/clients/understanding-clients)

## Key Functions

### Registers with Praxis

Using the Olm ID and a secret, the olm will make HTTP requests to Praxis to receive a session token. Using that token, it will connect to a websocket and maintain that connection. Control messages will be sent over the websocket.

### Receives WireGuard Control Messages

When Olm receives WireGuard control messages, it will use the information encoded (endpoint, public key) to bring up a WireGuard tunnel on your computer to a remote Newt. It will ping over the tunnel to ensure the peer is brought up.

## Hole Punching

In the default mode, Olm uses both relaying through Gerbil and NAT hole punching to connect to Newt. Hole punching attempts to orchestrate a NAT traversal between the two sites so that traffic flows directly, which can save data costs and improve speed. If hole punching fails, traffic will fall back to relaying through Gerbil.

## Build

### Binary

Make sure to have Go 1.25 installed.

```bash
make
```

## Licensing

Olm is dual licensed under the AGPLv3 and the Fossorial Commercial license. For inquiries about commercial licensing, please contact us.

## Contributions

Please see [CONTRIBUTIONS](./CONTRIBUTING.md) in the repository for guidelines and best practices.
