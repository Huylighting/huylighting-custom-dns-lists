# Huylighting — Custom Allowlist for DNS & Ad Blocking

A transparent, community-readable allowlist for legitimate websites and services that may be incorrectly blocked by filters. The project provides compatible rule files for multiple filtering platforms instead of assuming one syntax works everywhere.

The list is maintained by Huylighting. Every exception should have a clear purpose and be reviewed before it is added.

## Supported formats

| File | Format | Intended platforms |
| --- | --- | --- |
| [allowlists.txt](./allowlists.txt) | AdGuard / Adblock Plus (ABP) filter syntax | AdGuard Home, AdGuard DNS filtering, uBlock Origin and other blockers that accept compatible ABP network filters |
| [pihole-allowlist.txt](./pihole-allowlist.txt) | Pi-hole subscribed allowlist using supported ABP-style allow rules | Pi-hole v6 and later |

**Compatibility note:** Not every ad blocker uses the same rule format or supports remote allowlist subscriptions. Use the file documented for your platform. For other DNS filters (for example, products that accept only plain domain entries), convert/import the domains using that product's own documented format. Do not paste ABP rules into a plain-domain-only field.

## Subscribe with AdGuard Home

Add this Raw URL under **Filters → DNS allowlists**:

```text
https://raw.githubusercontent.com/Huylighting/adguard-custom-allowlist/main/allowlists.txt
```

1. Open the AdGuard Home web interface.
2. Go to **Filters → DNS allowlists**.
3. Choose **Add allowlist**.
4. Name it `Huylighting Custom Allowlist`.
5. Paste the Raw URL and save.
6. Refresh/update the filter lists if needed.

## Subscribe with Pi-hole

Pi-hole v6 added support for subscribing to external allowlists. Add this Raw URL as a **subscribed allowlist** in Pi-hole:

```text
https://raw.githubusercontent.com/Huylighting/adguard-custom-allowlist/main/pihole-allowlist.txt
```

Then update/reload the subscribed lists (Gravity). Make sure the source is configured as an **allowlist**, not a blocklist. Pi-hole's parser supports the ABP-style `@@||example.com^` syntax in subscribed allowlists. Pi-hole v5 does not support external allowlist subscriptions; on older versions, add the required domains manually using Pi-hole's domain allowlist.

See the official [Pi-hole Domain Database documentation](https://docs.pi-hole.net/database/domain-database/) for subscription and syntax details.

## Current entries

| Domain | Service | Purpose |
| --- | --- | --- |
| `malighting.com` | MA Lighting | Stage-lighting products and services |
| `azota.vn` | Azota | Education and learning platform |
| `console.tailscale.com` | Tailscale | Administration console |
| `login.tailscale.com` | Tailscale | Login and authentication |

The AdGuard/ABP rules and Pi-hole subscription rules are maintained separately so each platform has a clearly named source file.

## Rule syntax

The compatible ABP-style allow rule is:

```text
@@||example.com^
```

It allows the domain and its subdomains on platforms that support this syntax. In this repository, lines beginning with `!` are comments.

## Reporting a false positive

Before requesting an exception:

1. Open the filtering platform's query log.
2. Reproduce the website or service issue.
3. Identify the exact domain that was blocked.
4. Confirm that the domain is genuinely required for the service.
5. Explain why the block appears to be a false positive.

Please include the affected service, exact blocked domain, filtering product/list (if known), and a short reason the domain is needed.

Do not add broad exceptions when a narrower rule is sufficient. Do not allow advertising, analytics, or tracking domains just to restore an unrelated page element. An allowlist exception reduces filtering for the matching domain and may affect privacy or ad blocking.

## Maintenance and scope

This is a personally maintained project, not an official list endorsed by AdGuard, Pi-hole, or other filtering vendors. Entries may be added, changed, or removed as services evolve and reports are reviewed.

The project focuses on **false-positive fixes for legitimate services**. It is not intended to disable ad blocking globally or to guarantee that every website feature will work.

Use the list only if you trust the maintainer and have reviewed its contents. Administrators are responsible for deciding whether each exception is appropriate for their network.

## Links

- **AdGuard / ABP Raw list:** https://raw.githubusercontent.com/Huylighting/adguard-custom-allowlist/main/allowlists.txt
- **Pi-hole v6 Raw list:** https://raw.githubusercontent.com/Huylighting/adguard-custom-allowlist/main/pihole-allowlist.txt
- **Repository:** https://github.com/Huylighting/adguard-custom-allowlist
