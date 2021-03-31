# linode_networking_ip

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
    linode = ">= 1.16.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "linode_networking_ip" {
  source = "./modules/linode/d/linode_networking_ip"

  # address - (required) is a type of string
  address = null
}
```

[top](#index)

### Variables

```terraform
variable "address" {
  description = "(required) - The IP address."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "linode_networking_ip" "this" {
  address = var.address
}
```

[top](#index)

### Outputs

```terraform
output "gateway" {
  description = "returns a string"
  value       = data.linode_networking_ip.this.gateway
}

output "id" {
  description = "returns a string"
  value       = data.linode_networking_ip.this.id
}

output "linode_id" {
  description = "returns a number"
  value       = data.linode_networking_ip.this.linode_id
}

output "prefix" {
  description = "returns a number"
  value       = data.linode_networking_ip.this.prefix
}

output "public" {
  description = "returns a bool"
  value       = data.linode_networking_ip.this.public
}

output "rdns" {
  description = "returns a string"
  value       = data.linode_networking_ip.this.rdns
}

output "region" {
  description = "returns a string"
  value       = data.linode_networking_ip.this.region
}

output "subnet_mask" {
  description = "returns a string"
  value       = data.linode_networking_ip.this.subnet_mask
}

output "type" {
  description = "returns a string"
  value       = data.linode_networking_ip.this.type
}

output "this" {
  value = linode_networking_ip.this
}
```

[top](#index)