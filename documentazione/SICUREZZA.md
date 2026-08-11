# Security

## Never publish secrets

Do not commit:
- GitHub Personal Access Tokens;
- API keys;
- OAuth client secrets;
- `.env` files;
- private campaign secrets;
- personal player data.

## Recommended GitHub token scope

For the reference setup, create a fine-grained token:
- restricted to the individual private campaign repository;
- repository permission `Contents: Read and write`;
- no unnecessary additional permissions.

Store the token only in the Custom GPT Action authentication field.

## Public framework vs private campaign

Keep this framework repository public and reusable.
Keep each actual campaign repository private unless the campaign owner intentionally chooses otherwise.
