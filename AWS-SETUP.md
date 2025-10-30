# AWS Credentials Setup

## How to persist AWS credentials in this environment

### Step 1: Edit the credentials file

```bash
nano .aws-credentials.sh
```

### Step 2: Replace the placeholder values

```bash
export AWS_ACCESS_KEY_ID="your-actual-access-key-id"
export AWS_SECRET_ACCESS_KEY="your-actual-secret-access-key"
export AWS_DEFAULT_REGION="us-east-1"  # or your preferred region
```

### Step 3: Save and source the file

```bash
source .aws-credentials.sh
```

### Step 4: Verify

```bash
aws sts get-caller-identity
```

## How it works

- The `.aws-credentials.sh` file is automatically loaded when you open a new terminal
- The file is in `.gitignore` so your credentials are never committed
- The `postCreateCommand` in `devcontainer.json` adds the source command to your `.bashrc`
- Your credentials persist across workspace restarts

## Security Notes

⚠️ **Important:**
- Never commit `.aws-credentials.sh` to git
- Use IAM users with minimal required permissions
- Rotate credentials regularly
- Don't share your workspace with untrusted users
