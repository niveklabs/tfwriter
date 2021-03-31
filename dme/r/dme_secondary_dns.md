# dme_secondary_dns

[back](../dme.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dme = ">= 0.1.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dme_secondary_dns" {
  source = "./modules/dme/r/dme_secondary_dns"

  # folder_id - (optional) is a type of string
  folder_id = null
  # ipset_id - (required) is a type of string
  ipset_id = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "folder_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipset_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "dme_secondary_dns" "this" {
  folder_id = var.folder_id
  ipset_id  = var.ipset_id
  name      = var.name
}
```

[top](#index)

### Outputs

```terraform
output "folder_id" {
  description = "returns a string"
  value       = dme_secondary_dns.this.folder_id
}

output "id" {
  description = "returns a string"
  value       = dme_secondary_dns.this.id
}

output "this" {
  value = dme_secondary_dns.this
}
```

[top](#index)