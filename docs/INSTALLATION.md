# Installation — Pre-alpha

## 1. Create a private campaign repository

Create a new private GitHub repository for the campaign.

Copy:
- `templates/campaign/` to `campaign/`
- `templates/dm/` to `dm/`

## 2. Configure the Custom GPT

Upload the nine files from `knowledge/` as Knowledge.

Copy `gpt/INSTRUCTIONS.md` into the Custom GPT Instructions and replace:
- `YOUR_GITHUB_USERNAME`
- `YOUR_CAMPAIGN_REPOSITORY`

Enable Code Interpreter / Data Analysis.

## 3. Create GitHub authentication

Create a fine-grained Personal Access Token restricted to the private campaign repository with `Contents: Read and write`.

Configure the Custom GPT Action authentication as an API key using Bearer authentication.

## 4. Configure the GitHub Action

Copy `gpt/github-action-openapi.yaml` into the Action schema.

Replace:
- `YOUR_GITHUB_USERNAME`
- `YOUR_CAMPAIGN_REPOSITORY`

Test `readCampaignFile` before testing writes.

## 5. Verify persistence

Read `campaign/PG.md` and `campaign/STATO_CAMPAGNA.md`.

Perform a controlled write test, verify the resulting Git commit, then restore any temporary test data.

## 6. Verify RNG

Ask the GPT to generate multiple independent dice results using Code Interpreter / Data Analysis and confirm that the tool actually executes.
