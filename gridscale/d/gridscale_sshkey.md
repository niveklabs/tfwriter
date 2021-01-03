# gridscale_sshkey

[back](../gridscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    gridscale = ">= 1.7.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gridscale_sshkey" {
  source = "./modules/gridscale/d/gridscale_sshkey"

  # resource_id - (required) is a type of string
  resource_id = null
}
```

[top](#index)

### Variables

```terraform
variable "resource_id" {
  description = "(required) - ID of a resource"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "gridscale_sshkey" "this" {
  resource_id = var.resource_id
}
```

[top](#index)

### Outputs

```terraform
output "change_time" {
  description = "returns a string"
  value       = data.gridscale_sshkey.this.change_time
}

output "create_time" {
  description = "returns a string"
  value       = data.gridscale_sshkey.this.create_time
}

output "id" {
  description = "returns a string"
  value       = data.gridscale_sshkey.this.id
}

output "labels" {
  description = "returns a set of string"
  value       = data.gridscale_sshkey.this.labels
}

output "name" {
  description = "returns a string"
  value       = data.gridscale_sshkey.this.name
}

output "sshkey" {
  description = "returns a string"
  value       = data.gridscale_sshkey.this.sshkey
}

output "status" {
  description = "returns a string"
  value       = data.gridscale_sshkey.this.status
}

output "this" {
  value = gridscale_sshkey.this
}
```

[top](#index)