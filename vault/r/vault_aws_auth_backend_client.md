# vault_aws_auth_backend_client

[back](../vault.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vault = ">= 2.17.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vault_aws_auth_backend_client" {
  source = "./modules/vault/r/vault_aws_auth_backend_client"

  # access_key - (optional) is a type of string
  access_key = null
  # backend - (optional) is a type of string
  backend = null
  # ec2_endpoint - (optional) is a type of string
  ec2_endpoint = null
  # iam_endpoint - (optional) is a type of string
  iam_endpoint = null
  # iam_server_id_header_value - (optional) is a type of string
  iam_server_id_header_value = null
  # secret_key - (optional) is a type of string
  secret_key = null
  # sts_endpoint - (optional) is a type of string
  sts_endpoint = null
  # sts_region - (optional) is a type of string
  sts_region = null
}
```

[top](#index)

### Variables

```terraform
variable "access_key" {
  description = "(optional) - AWS Access key with permissions to query AWS APIs."
  type        = string
  default     = null
}

variable "backend" {
  description = "(optional) - Unique name of the auth backend to configure."
  type        = string
  default     = null
}

variable "ec2_endpoint" {
  description = "(optional) - URL to override the default generated endpoint for making AWS EC2 API calls."
  type        = string
  default     = null
}

variable "iam_endpoint" {
  description = "(optional) - URL to override the default generated endpoint for making AWS IAM API calls."
  type        = string
  default     = null
}

variable "iam_server_id_header_value" {
  description = "(optional) - The value to require in the X-Vault-AWS-IAM-Server-ID header as part of GetCallerIdentity requests that are used in the iam auth method."
  type        = string
  default     = null
}

variable "secret_key" {
  description = "(optional) - AWS Secret key with permissions to query AWS APIs."
  type        = string
  default     = null
}

variable "sts_endpoint" {
  description = "(optional) - URL to override the default generated endpoint for making AWS STS API calls."
  type        = string
  default     = null
}

variable "sts_region" {
  description = "(optional) - Region to override the default region for making AWS STS API calls."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_aws_auth_backend_client" "this" {
  access_key                 = var.access_key
  backend                    = var.backend
  ec2_endpoint               = var.ec2_endpoint
  iam_endpoint               = var.iam_endpoint
  iam_server_id_header_value = var.iam_server_id_header_value
  secret_key                 = var.secret_key
  sts_endpoint               = var.sts_endpoint
  sts_region                 = var.sts_region
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_aws_auth_backend_client.this.id
}

output "this" {
  value = vault_aws_auth_backend_client.this
}
```

[top](#index)