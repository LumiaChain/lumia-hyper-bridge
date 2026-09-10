<h1>
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="./assets/lumia-mark-dark.svg">
    <img alt="" src="./assets/lumia-mark-light.svg" height="26">
  </picture>
  Lumia Bridge
</h1>

> [!NOTE]
> **This repository is generated and contains no source code.**
> It exists to publish the release history of Lumia Bridge. `CHANGELOG.md` is written by an
> automated job from the private repositories the product is built in — edits made here by
> hand are overwritten on the next run. Issues and discussions are read and answered; pull
> requests against this repository are closed unfixed.
> The code lives in the repositories linked under [Source code](#source-code).

Moving assets in and out of Lumia. Two independent paths, each with its own trust model:

| | |
|---|---|
| **Agglayer** | The native bridge of the Polygon CDK stack Lumia runs on. Used for the canonical route between Lumia and Ethereum. |
| **Hyperlane** | Permissionless interchain messaging, used for routes to the other chains listed below. Lumia runs its own validator and relayer for these routes. |

Live at **[bridge.lumia.org](https://bridge.lumia.org)**.

This repository is the public home of the Bridge's release history. The application is a
fork of Hyperlane's transfer interface; the changelog here covers **our** changes to it and
the deployment we operate, not the upstream project.

## Routes

Assets moving over Hyperlane warp routes, as registered in the public
[Hyperlane registry](https://github.com/hyperlane-xyz/hyperlane-registry/tree/main/deployments/warp_routes):

| Asset | Connected chains |
|---|---|
| [LUMIA](https://github.com/hyperlane-xyz/hyperlane-registry/tree/main/deployments/warp_routes/LUMIA) | Ethereum, Arbitrum, Avalanche, Base, BNB Smart Chain, Optimism, Polygon |
| [ETH](https://github.com/hyperlane-xyz/hyperlane-registry/tree/main/deployments/warp_routes/ETH) | Ethereum, Arbitrum, Base, Optimism, Polygon |
| [USDC](https://github.com/hyperlane-xyz/hyperlane-registry/tree/main/deployments/warp_routes/USDC) | Ethereum, Arbitrum, Base, Optimism |
| [USDT](https://github.com/hyperlane-xyz/hyperlane-registry/tree/main/deployments/warp_routes/USDT) | Ethereum |
| [PNDR](https://github.com/hyperlane-xyz/hyperlane-registry/tree/main/deployments/warp_routes/PNDR) | Ethereum, BNB Smart Chain |

## Contracts

Hyperlane core deployment on Lumia Prism (chain ID `994873017`). Addresses come from the
public [Hyperlane registry](https://github.com/hyperlane-xyz/hyperlane-registry/blob/main/chains/lumiaprism/addresses.yaml)
and are verifiable on the [explorer](https://explorer.lumia.org).

| Contract | Address |
|---|---|
| Mailbox | [`0x0dF25A2d59F03F039b56E90EdC5B89679Ace28Bc`](https://explorer.lumia.org/address/0x0dF25A2d59F03F039b56E90EdC5B89679Ace28Bc) |
| Interchain Gas Paymaster | [`0xb7C9307fE90B9AB093c6D3EdeE3259f5378D5f03`](https://explorer.lumia.org/address/0xb7C9307fE90B9AB093c6D3EdeE3259f5378D5f03) |
| Interchain Security Module | [`0x9Ed43A4C9FaE7Bd17FA62b8984C3Ae74739E85a0`](https://explorer.lumia.org/address/0x9Ed43A4C9FaE7Bd17FA62b8984C3Ae74739E85a0) |
| Merkle Tree Hook | [`0xC88636fFdFAc7cb87b7A76310B7a62AF0A000595`](https://explorer.lumia.org/address/0xC88636fFdFAc7cb87b7A76310B7a62AF0A000595) |
| Validator Announce | [`0x803d2A87429E20d4B52266bF97Ca1c7e4f4F5Dfa`](https://explorer.lumia.org/address/0x803d2A87429E20d4B52266bF97Ca1c7e4f4F5Dfa) |
| Interchain Account Router | [`0x3C330D4A2e2b8443AFaB8E326E64ab4251B7Eae0`](https://explorer.lumia.org/address/0x3C330D4A2e2b8443AFaB8E326E64ab4251B7Eae0) |

Inbound security modules on the connected chains are static and ownerless by design; their
addresses are in the registry alongside the routes above.

## How it is operated

Lumia runs its own Hyperlane validator and relayer for the routes above rather than relying
on a hosted deployment. Ownership of the route and core contracts is reviewed on a recurring
schedule against the expected configuration.

## Source code

The bridge is operated from these repositories. The application is a fork of Hyperlane's
transfer interface with our changes on top; the agent configuration and deployment
documentation are ours.

| | |
|---|---|
| [hyper-bridge](https://github.com/LumiaChain/hyper-bridge) | The transfer interface behind bridge.lumia.org |
| [contracts](https://github.com/LumiaChain/hyperlane-contracts) | Agent configuration, deployment and paymaster documentation |
| [hyperlane-monorepo](https://github.com/hyperlane-xyz/hyperlane-monorepo) | Our fork of the Hyperlane monorepo, from which the validator and relayer images are built |

## Areas

Release notes are labelled by the part of the bridge a change affects.

- **app** — the transfer interface at bridge.lumia.org
- **deployment** — configuration and documentation for the agents that carry messages

## Reporting an issue

Open an issue using one of the templates. For anything security-sensitive, do not open a
public issue — write to the Lumia team directly.

## License

The contents of this repository are published under the MIT License.
