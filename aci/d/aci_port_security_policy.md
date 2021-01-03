# aci_port_security_policy

[back](../aci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aci = ">= 0.5.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_port_security_policy" {
  source = "./modules/aci/d/aci_port_security_policy"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # maximum - (optional) is a type of string
  maximum = null
  # mode - (optional) is a type of string
  mode = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # timeout - (optional) is a type of string
  timeout = null
  # violation - (optional) is a type of string
  violation = null
}
```

[top](#index)

### Variables

```terraform
variable "annotation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "maximum" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "name_alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeout" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "violation" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aci_port_security_policy" "this" {
  annotation  = var.annotation
  description = var.description
  maximum     = var.maximum
  mode        = var.mode
  name        = var.name
  name_alias  = var.name_alias
  timeout     = var.timeout
  violation   = var.violation
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.aci_port_security_policy.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aci_port_security_policy.this.id
}

output "maximum" {
  description = "returns a string"
  value       = data.aci_port_security_policy.this.maximum
}

output "mode" {
  description = "returns a string"
  value       = data.aci_port_security_policy.this.mode
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_port_security_policy.this.name_alias
}

output "timeout" {
  description = "returns a string"
  value       = data.aci_port_security_policy.this.timeout
}

output "violation" {
  description = "returns a string"
  value       = data.aci_port_security_policy.this.violation
}

output "this" {
  value = aci_port_security_policy.this
}
```

[top](#index)