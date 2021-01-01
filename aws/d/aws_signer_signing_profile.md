# aws_signer_signing_profile

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "aws_signer_signing_profile" {
  source = "./modules/aws/d/aws_signer_signing_profile"

  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```hcl
variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```hcl
data "aws_signer_signing_profile" "this" {
  name = var.name
  tags = var.tags
}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = data.aws_signer_signing_profile.this.arn
}

output "id" {
  description = "returns a string"
  value       = data.aws_signer_signing_profile.this.id
}

output "platform_display_name" {
  description = "returns a string"
  value       = data.aws_signer_signing_profile.this.platform_display_name
}

output "platform_id" {
  description = "returns a string"
  value       = data.aws_signer_signing_profile.this.platform_id
}

output "revocation_record" {
  description = "returns a list of object"
  value       = data.aws_signer_signing_profile.this.revocation_record
}

output "signature_validity_period" {
  description = "returns a list of object"
  value       = data.aws_signer_signing_profile.this.signature_validity_period
}

output "status" {
  description = "returns a string"
  value       = data.aws_signer_signing_profile.this.status
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_signer_signing_profile.this.tags
}

output "version" {
  description = "returns a string"
  value       = data.aws_signer_signing_profile.this.version
}

output "version_arn" {
  description = "returns a string"
  value       = data.aws_signer_signing_profile.this.version_arn
}

output "this" {
  value = aws_signer_signing_profile.this
}
```

[top](#index)