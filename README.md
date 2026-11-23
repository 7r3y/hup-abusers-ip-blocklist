# HUP Abusers IP Blocklist

Public IP blocklist maintained by trey @ HUP (https://hup.hu).

The list is based exclusively on security observations from HUP infrastructure.

The Cloudflare abusers list is the operational source of truth. This repository is its manually maintained public copy.

External IP submissions are not accepted. GitHub Issues are reserved for reporting potential false positives.

## Inclusion criteria

New entries are added only for observed vulnerability scanning or hostile security probing targeting HUP infrastructure. Legitimate web crawling, search engine indexing, and high traffic volume alone are not grounds for inclusion.

Legacy entries migrated from pre-existing HUP infrastructure blocking rules may also be included. These are explicitly identified in their comments.

## Data format

The blocklist is published as `blocklist.json` with three fields:

- `ip`: Blocked IPv4/IPv6 address or CIDR range.
- `comment`: Reason recorded in the Cloudflare abusers list.
- `created_on`: Timestamp when the entry was created in Cloudflare (UTC), not necessarily when the activity was observed.

Entries are sorted lexicographically by IP address. Updates are published manually after review.

## Plain-text blocklist

`blocklist.txt` contains one IPv4 address, IPv6 address or CIDR range per line, without comments or headers. It is generated from the same Cloudflare data as `blocklist.json` and is intended for direct use by automated filtering tools.

## TODO

- Add CSV export (`blocklist.csv`) generated from the same Cloudflare `abusers` data.
