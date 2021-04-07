# scaleway_instance_security_group

[back](../scaleway.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    scaleway = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "scaleway_instance_security_group" {
  source = "./modules/scaleway/d/scaleway_instance_security_group"

  # name - (optional) is a type of string
  name = null
  # security_group_id - (optional) is a type of string
  security_group_id = null
  # zone - (optional) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - The name of the security group"
  type        = string
  default     = null
}

variable "security_group_id" {
  description = "(optional) - The ID of the security group"
  type        = string
  default     = null
}

variable "zone" {
  description = "(optional) - The zone you want to attach the resource to"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "scaleway_instance_security_group" "this" {
  # name - (optional) is a type of string
  name = var.name
  # security_group_id - (optional) is a type of string
  security_group_id = var.security_group_id
  # zone - (optional) is a type of string
  zone = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.scaleway_instance_security_group.this.description
}

output "enable_default_security" {
  description = "returns a bool"
  value       = data.scaleway_instance_security_group.this.enable_default_security
}

output "external_rules" {
  description = "returns a bool"
  value       = data.scaleway_instance_security_group.this.external_rules
}

output "id" {
  description = "returns a string"
  value       = data.scaleway_instance_security_group.this.id
}

output "inbound_default_policy" {
  description = "returns a string"
  value       = data.scaleway_instance_security_group.this.inbound_default_policy
}

output "inbound_rule" {
  description = "returns a list of object"
  value       = data.scaleway_instance_security_group.this.inbound_rule
}

output "organization_id" {
  description = "returns a string"
  value       = data.scaleway_instance_security_group.this.organization_id
}

output "outbound_default_policy" {
  description = "returns a string"
  value       = data.scaleway_instance_security_group.this.outbound_default_policy
}

output "outbound_rule" {
  description = "returns a list of object"
  value       = data.scaleway_instance_security_group.this.outbound_rule
}

output "project_id" {
  description = "returns a string"
  value       = data.scaleway_instance_security_group.this.project_id
}

output "stateful" {
  description = "returns a bool"
  value       = data.scaleway_instance_security_group.this.stateful
}

output "this" {
  value = scaleway_instance_security_group.this
}
```

[top](#index)