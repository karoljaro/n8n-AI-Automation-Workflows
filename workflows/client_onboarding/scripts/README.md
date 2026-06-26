# Webhook tests

Minimal Bash scripts for testing the n8n workflow that creates a client folder in Google Drive.

## Scripts

- `test_webhook` — valid input, expected status: `201`.
- `test_webhook_invalid` — invalid input, expected status: `422`.
- `test_webhook_duplicate` — existing client folder, expected status: `409`.

## Usage

```bash
chmod +x test_webhook test_webhook_invalid test_webhook_duplicate

./test_webhook
./test_webhook_invalid
./test_webhook_duplicate
```

You can provide a different webhook URL as an argument:

```bash
./test_webhook http://localhost:5678/webhook/ID
```

Or through the `WEBHOOK_URL` environment variable:

```bash
WEBHOOK_URL=http://localhost:5678/webhook/ID ./test_webhook
```

When using a `webhook-test` URL, n8n may require you to select **Listen for test event** before each request. Run the duplicate test after the valid-input test so the client folder already exists.

`curl` is required. Python 3 is optional and is used only to format JSON output with unescaped Unicode characters.
