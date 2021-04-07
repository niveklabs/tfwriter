# linode_instance_ip

[back](../linode.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "linode_instance_ip" {
  source = "./modules/linode/r/linode_instance_ip"

  # linode_id - (required) is a type of number
  linode_id = null
  # public - (optional) is a type of bool
  public = null
  # rdns - (optional) is a type of string
  rdns = null
}
```

[top](#index)

### Variables

```terraform
variable "linode_id" {
  description = "(required) - The ID of the Linode to allocate an IPv4 address for."
  type        = number
}

variable "public" {
  description = "(optional) - Whether the IPv4 address is public or private."
  type        = bool
  default     = null
}

variable "rdns" {
  description = "(optional) - The reverse DNS assigned to this address."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "linode_instance_ip" "this" {
  # linode_id - (required) is a type of number
  linode_id = var.linode_id
  # public - (optional) is a type of bool
  public = var.public
  # rdns - (optional) is a type of string
  rdns = var.rdns
}
```

[top](#index)

### Outputs

```terraform
output "address" {
  description = "returns a string"
  value       = linode_instance_ip.this.address
}

output "gateway" {
  description = "returns a string"
  value       = linode_instance_ip.this.gateway
}

output "id" {
  description = "returns a string"
  value       = linode_instance_ip.this.id
}

output "prefix" {
  description = "returns a number"
  value       = linode_instance_ip.this.prefix
}

output "rdns" {
  description = "returns a string"
  value       = linode_instance_ip.this.rdns
}

output "region" {
  description = "returns a string"
  value       = linode_instance_ip.this.region
}

output "subnet_mask" {
  description = "returns a string"
  value       = linode_instance_ip.this.subnet_mask
}

output "type" {
  description = "returns a string"
  value       = linode_instance_ip.this.type
}

output "this" {
  value = linode_instance_ip.this
}
```

[top](#index)