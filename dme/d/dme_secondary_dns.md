# dme_secondary_dns

[back](../dme.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/dme/d/dme_secondary_dns"

  # folder_id - (optional) is a type of string
  folder_id = null
  # ipset_id - (optional) is a type of string
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
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "dme_secondary_dns" "this" {
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
  value       = data.dme_secondary_dns.this.folder_id
}

output "id" {
  description = "returns a string"
  value       = data.dme_secondary_dns.this.id
}

output "ipset_id" {
  description = "returns a string"
  value       = data.dme_secondary_dns.this.ipset_id
}

output "this" {
  value = dme_secondary_dns.this
}
```

[top](#index)