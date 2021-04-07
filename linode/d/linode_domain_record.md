# linode_domain_record

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
module "linode_domain_record" {
  source = "./modules/linode/d/linode_domain_record"

  # domain_id - (required) is a type of number
  domain_id = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "domain_id" {
  description = "(required) - The associated domain's ID."
  type        = number
}

variable "name" {
  description = "(optional) - The name of the Record."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "linode_domain_record" "this" {
  # domain_id - (required) is a type of number
  domain_id = var.domain_id
  # name - (optional) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a number"
  value       = data.linode_domain_record.this.id
}

output "port" {
  description = "returns a number"
  value       = data.linode_domain_record.this.port
}

output "priority" {
  description = "returns a number"
  value       = data.linode_domain_record.this.priority
}

output "protocol" {
  description = "returns a string"
  value       = data.linode_domain_record.this.protocol
}

output "service" {
  description = "returns a string"
  value       = data.linode_domain_record.this.service
}

output "tag" {
  description = "returns a string"
  value       = data.linode_domain_record.this.tag
}

output "target" {
  description = "returns a string"
  value       = data.linode_domain_record.this.target
}

output "ttl_sec" {
  description = "returns a number"
  value       = data.linode_domain_record.this.ttl_sec
}

output "type" {
  description = "returns a string"
  value       = data.linode_domain_record.this.type
}

output "weight" {
  description = "returns a number"
  value       = data.linode_domain_record.this.weight
}

output "this" {
  value = linode_domain_record.this
}
```

[top](#index)