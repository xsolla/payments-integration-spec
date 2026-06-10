# Xsolla Payments Integration Spec

[![License](https://img.shields.io/github/license/xsolla/payments-integration-spec)](#license)

## Overview

This repository contains the API specification that payment providers must implement to integrate with the Xsolla Payments platform. It defines the REST endpoint contract, HTTP Message Signature scheme (RFC 9421 / RFC 9530), webhook event payloads, and payment flow sequences.

The specification is published in both OpenAPI (`openapi.yaml`) and Postman (`postman.json`) formats. All synchronous API calls are sent **from Xsolla to the provider**. Providers implement the REST endpoints, verify request signatures, and respond per the contract.

## Requirements

- A REST service capable of receiving HTTPS requests from Xsolla
- Ability to verify HTTP Message Signatures (RFC 9421) and Content-Digest (RFC 9530)
- A signing key and `keyid` issued by your Xsolla integration manager
- (Optional) [Prism CLI](https://stoplight.io/open-source/prism) for local mock server

## Install

```bash
git clone https://github.com/xsolla/payments-integration-spec.git
```

Key files:
- `openapi.yaml` — OpenAPI 3 specification of all required endpoints
- `postman.json` — Postman collection for interactive endpoint exploration

## Usage

**Run a local mock server with Prism:**

```bash
npx @stoplight/prism-cli mock openapi.yaml
```

**Import into Postman:**

Open Postman, select **Import**, and upload `postman.json` to explore all endpoints interactively.

## Documentation

Full integration guide is in this repository's `README.md`. For Xsolla Payments API context, visit [developers.xsolla.com](https://developers.xsolla.com/).

## Support

- [Open an issue](https://github.com/xsolla/payments-integration-spec/issues) on GitHub
- Contact your Xsolla integration manager for signing key provisioning

## License

MIT License. See [LICENSE](./LICENSE).
