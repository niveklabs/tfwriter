# linode_instance_type

[back](../linode.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    linode = ">= 1.13.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "linode_instance_type" {
  source = "./modules/linode/d/linode_instance_type"

  # label - (optional) is a type of string
  label = null
}
```

[top](#index)

### Variables

```terraform
variable "label" {
  description = "(optional) - The Linode Type's label is for display purposes only."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "linode_instance_type" "this" {
  label = var.label
}
```

[top](#index)

### Outputs

```terraform
output "addons" {
  description = "returns a list of object"
  value       = data.linode_instance_type.this.addons
}

output "class" {
  description = "returns a string"
  value       = data.linode_instance_type.this.class
}

output "disk" {
  description = "returns a number"
  value       = data.linode_instance_type.this.disk
}

output "id" {
  description = "returns a string"
  value       = data.linode_instance_type.this.id
}

output "label" {
  description = "returns a string"
  value       = data.linode_instance_type.this.label
}

output "memory" {
  description = "returns a number"
  value       = data.linode_instance_type.this.memory
}

output "network_out" {
  description = "returns a number"
  value       = data.linode_instance_type.this.network_out
}

output "price" {
  description = "returns a list of object"
  value       = data.linode_instance_type.this.price
}

output "transfer" {
  description = "returns a number"
  value       = data.linode_instance_type.this.transfer
}

output "vcpus" {
  description = "returns a number"
  value       = data.linode_instance_type.this.vcpus
}

output "this" {
  value = linode_instance_type.this
}
```

[top](#index)