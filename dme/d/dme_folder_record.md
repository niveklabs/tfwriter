# dme_folder_record

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
module "dme_folder_record" {
  source = "./modules/dme/d/dme_folder_record"

  # default_folder - (optional) is a type of string
  default_folder = null
  # domains - (optional) is a type of list of string
  domains = []
  # name - (required) is a type of string
  name = null
  # secondaries - (optional) is a type of list of string
  secondaries = []

  folder_permissions = [{
    group_id   = null
    group_name = null
    permission = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "default_folder" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domains" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "secondaries" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "folder_permissions" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      group_id   = string
      group_name = string
      permission = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "dme_folder_record" "this" {
  default_folder = var.default_folder
  domains        = var.domains
  name           = var.name
  secondaries    = var.secondaries

  dynamic "folder_permissions" {
    for_each = var.folder_permissions
    content {
      group_id   = folder_permissions.value["group_id"]
      group_name = folder_permissions.value["group_name"]
      permission = folder_permissions.value["permission"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "default_folder" {
  description = "returns a string"
  value       = data.dme_folder_record.this.default_folder
}

output "domains" {
  description = "returns a list of string"
  value       = data.dme_folder_record.this.domains
}

output "id" {
  description = "returns a string"
  value       = data.dme_folder_record.this.id
}

output "secondaries" {
  description = "returns a list of string"
  value       = data.dme_folder_record.this.secondaries
}

output "this" {
  value = dme_folder_record.this
}
```

[top](#index)