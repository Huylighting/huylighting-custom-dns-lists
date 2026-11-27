# Huylighting — AdGuard Home Custom Allowlist

A community-readable collection of DNS allowlist rules for **AdGuard Home**. This project documents domains that may be incorrectly blocked by DNS filtering and are needed for legitimate websites and services.

The list is maintained by Huylighting and is intended to be transparent, easy to review, and simple to subscribe to.

## Subscribe

Add the following Raw URL to **AdGuard Home → Filters → DNS allowlists**:

```text
https://raw.githubusercontent.com/Huylighting/adguard-custom-allowlist/main/allowlists.txt
```

1. Open the AdGuard Home web interface.
2. Go to **Filters → DNS allowlists**.
3. Choose **Add allowlist**.
4. Give the list a name, such as `Huylighting Custom Allowlist`.
5. Paste the Raw URL above and save.
6. Update the filter lists if the rules are not fetched automatically.

Use the Raw URL from `raw.githubusercontent.com`, not the GitHub file-view page under `github.com/.../blob/...`.

## Current entries

| Domain | Service | Reason |
| --- | --- | --- |
| `malighting.com` | MA Lighting | Stage-lighting products and services |
| `azota.vn` | Azota | Education and learning platform |
| `console.tailscale.com` | Tailscale | Administration console |
| `login.tailscale.com` | Tailscale | Login and authentication |

The rules are maintained in [allowlists.txt](./allowlists.txt).

## Rule syntax

The list uses AdGuard-compatible filtering syntax:

- `@@||example.com^` allows the domain and its subdomains.
- Put each rule on a separate line.
- Lines beginning with `!` are comments and are ignored by the filter engine.

Example:

```text
@@||example.com^
```

## Reporting a blocked domain

If a legitimate website or service is still unavailable:

1. Open **Query Log** in AdGuard Home.
2. Reproduce the issue.
3. Identify the exact blocked domain related to the affected service.
4. Verify that the domain is required and was blocked unintentionally before proposing an exception.

Please include:
- The website or service affected.
- The blocked domain shown in Query Log.
- A short explanation of why the domain is required.

Avoid broad exceptions when a narrower domain rule is sufficient. Do not add advertising, analytics, or tracking domains merely to fix an unrelated page element.

## Maintenance and scope

This is a personally maintained allowlist. Entries may be added, revised, or removed as services change and reports are reviewed. Inclusion means that matching DNS requests are exempted from filtering; it does not guarantee that every feature of a website will work.

Use this list only if you trust its maintainer and have reviewed the rules. Administrators remain responsible for deciding whether each exception is appropriate for their network.

## Links

- **Raw allowlist:** https://raw.githubusercontent.com/Huylighting/adguard-custom-allowlist/main/allowlists.txt
- **Repository:** https://github.com/Huylighting/adguard-custom-allowlist
