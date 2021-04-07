# hcloud_server_types

[back](../hcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    hcloud = ">= 1.26.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcloud_server_types" {
  source = "./modules/hcloud/d/hcloud_server_types"

  # server_type_ids - (optional) is a type of list of string
  server_type_ids = []
}
```

[top](#index)

### Variables

```terraform
variable "server_type_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "hcloud_server_types" "this" {
  # server_type_ids - (optional) is a type of list of string
  server_type_ids = var.server_type_ids
}
```

[top](#index)

### Outputs

```terraform
output "descriptions" {
  description = "returns a list of string"
  value       = data.hcloud_server_types.this.descriptions
}

output "id" {
  description = "returns a string"
  value       = data.hcloud_server_types.this.id
}

output "names" {
  description = "returns a list of string"
  value       = data.hcloud_server_types.this.names
}

output "this" {
  value = hcloud_server_types.this
}
```

[top](#index)