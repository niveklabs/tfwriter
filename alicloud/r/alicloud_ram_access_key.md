# alicloud_ram_access_key

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_ram_access_key" {
  source = "./modules/alicloud/r/alicloud_ram_access_key"

  # pgp_key - (optional) is a type of string
  pgp_key = null
  # secret_file - (optional) is a type of string
  secret_file = null
  # status - (optional) is a type of string
  status = null
  # user_name - (optional) is a type of string
  user_name = null
}
```

[top](#index)

### Variables

```terraform
variable "pgp_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secret_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ram_access_key" "this" {
  pgp_key     = var.pgp_key
  secret_file = var.secret_file
  status      = var.status
  user_name   = var.user_name
}
```

[top](#index)

### Outputs

```terraform
output "encrypted_secret" {
  description = "returns a string"
  value       = alicloud_ram_access_key.this.encrypted_secret
}

output "id" {
  description = "returns a string"
  value       = alicloud_ram_access_key.this.id
}

output "key_fingerprint" {
  description = "returns a string"
  value       = alicloud_ram_access_key.this.key_fingerprint
}

output "secret" {
  description = "returns a string"
  value       = alicloud_ram_access_key.this.secret
  sensitive   = true
}

output "this" {
  value = alicloud_ram_access_key.this
}
```

[top](#index)