# hcloud_datacenters

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
module "hcloud_datacenters" {
  source = "./modules/hcloud/d/hcloud_datacenters"

  # datacenter_ids - (optional) is a type of list of string
  datacenter_ids = []
}
```

[top](#index)

### Variables

```terraform
variable "datacenter_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "hcloud_datacenters" "this" {
  datacenter_ids = var.datacenter_ids
}
```

[top](#index)

### Outputs

```terraform
output "descriptions" {
  description = "returns a list of string"
  value       = data.hcloud_datacenters.this.descriptions
}

output "id" {
  description = "returns a string"
  value       = data.hcloud_datacenters.this.id
}

output "names" {
  description = "returns a list of string"
  value       = data.hcloud_datacenters.this.names
}

output "this" {
  value = hcloud_datacenters.this
}
```

[top](#index)