# htg-v3-supp
Keyed suppression data for HTG v3 outreach automations. **Contains no plaintext.**

- `htg_supp_v1.json` holds 48-bit HMAC-SHA256 tags and a keyed Bloom filter only. There are no names, emails, domains, IDs or credentials.
- The HMAC key is **not** in this repo. Without it the tags cannot be checked against guesses.
- Consumers verify the signature (`mac`), the counts and the expiry (`expires_at`, 10 days) and treat any failure as "hold everything".
- Updated weekly by an automated refresh. Do not edit by hand (the signature would break and consumers would fail closed).
