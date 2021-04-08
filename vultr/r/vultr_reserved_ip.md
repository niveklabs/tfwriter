# vultr_reserved_ip

[back](../vultr.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vultr = ">= 2.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vultr_reserved_ip" {
  source = "./modules/vultr/r/vultr_reserved_ip"

  # instance_id - (optional) is a type of string
  instance_id = null
  # ip_type - (required) is a type of string
  ip_type = null
  # label - (optional) is a type of string
  label = null
  # region - (required) is a type of string
  region = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_type" {
  description = "(required)"
  type        = string
}

variable "label" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vultr_reserved_ip" "this" {
  # instance_id - (optional) is a type of string
  instance_id = var.instance_id
  # ip_type - (required) is a type of string
  ip_type = var.ip_type
  # label - (optional) is a type of string
  label = var.label
  # region - (required) is a type of string
  region = var.region
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vultr_reserved_ip.this.id
}

output "instance_id" {
  description = "returns a string"
  value       = vultr_reserved_ip.this.instance_id
}

output "subnet" {
  description = "returns a string"
  value       = vultr_reserved_ip.this.subnet
}

output "subnet_size" {
  description = "returns a number"
  value       = vultr_reserved_ip.this.subnet_size
}

output "this" {
  value = vultr_reserved_ip.this
}
```

[top](#index)