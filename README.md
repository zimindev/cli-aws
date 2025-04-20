# ☁️ AWS CLI — Command Line Interface for Amazon Web Services

**AWS CLI** is a unified command-line tool to manage and automate your AWS services. You can control EC2, S3, IAM, Lambda, and more directly from your terminal.

---

## ✅ Features

- Full access to AWS services via CLI
- Automate AWS resource management
- Powerful scripting and automation support
- Works on Linux, macOS, and Windows
- Supports named profiles and credential management

---

## 🔧 Installation

### On Linux
```bash
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
```

### On macOS (Homebrew)
```bash
brew install awscli
```

### On Windows
- Download from: [https://aws.amazon.com/cli/](https://aws.amazon.com/cli/)

### Verify installation
```bash
aws --version
```

---

## 🚀 Basic Configuration

### Configure credentials
```bash
aws configure
```

You’ll be prompted for:
- AWS Access Key ID
- AWS Secret Access Key
- Default region (e.g. `us-east-1`)
- Output format (`json`, `table`, or `text`)

---

## 🛠️ Common Commands

| Command                                          | Description                               |
|--------------------------------------------------|-------------------------------------------|
| `aws s3 ls`                                      | List all S3 buckets                       |
| `aws s3 cp file.txt s3://my-bucket/`            | Upload file to S3                         |
| `aws ec2 describe-instances`                    | View EC2 instances                        |
| `aws ec2 start-instances --instance-ids i-123`  | Start an EC2 instance                     |
| `aws ec2 stop-instances --instance-ids i-123`   | Stop an EC2 instance                      |
| `aws iam list-users`                            | List IAM users                            |
| `aws lambda list-functions`                     | List all Lambda functions                 |

---

## 🌍 Profiles & Regions

Use named profiles to manage multiple accounts:
```bash
aws configure --profile my-second-account
aws s3 ls --profile my-second-account
```

Set region temporarily:
```bash
aws ec2 describe-instances --region eu-west-1
```

---

## 🧩 Tips

- Use `--output table` for prettier CLI output.
- Combine with `jq` for JSON filtering:
  ```bash
  aws ec2 describe-instances | jq '.Reservations[].Instances[].InstanceId'
  ```
- Create aliases in your shell config for common tasks.

---

## 📚 More Info

- Docs: [https://docs.aws.amazon.com/cli/](https://docs.aws.amazon.com/cli/)  
- GitHub: [https://github.com/aws/aws-cli](https://github.com/aws/aws-cli)  
- Run `aws help` or `man aws` for more details
