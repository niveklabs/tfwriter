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
  source = "./modules/aws/r/aws_signer_signing_profile"

  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # platform_id - (required) is a type of string
  platform_id = null
  # tags - (optional) is a type of map of string
  tags = {}

  signature_validity_period = [{
    type  = null
    value = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "platform_id" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "signature_validity_period" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      type  = string
      value = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "aws_signer_signing_profile" "this" {
  name        = var.name
  name_prefix = var.name_prefix
  platform_id = var.platform_id
  tags        = var.tags

  dynamic "signature_validity_period" {
    for_each = var.signature_validity_period
    content {
      type  = signature_validity_period.value["type"]
      value = signature_validity_period.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_signer_signing_profile.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_signer_signing_profile.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_signer_signing_profile.this.name
}

output "platform_display_name" {
  description = "returns a string"
  value       = aws_signer_signing_profile.this.platform_display_name
}

output "revocation_record" {
  description = "returns a list of object"
  value       = aws_signer_signing_profile.this.revocation_record
}

output "status" {
  description = "returns a string"
  value       = aws_signer_signing_profile.this.status
}

output "version" {
  description = "returns a string"
  value       = aws_signer_signing_profile.this.version
}

output "version_arn" {
  description = "returns a string"
  value       = aws_signer_signing_profile.this.version_arn
}

output "this" {
  value = aws_signer_signing_profile.this
}
```

[top](#index)