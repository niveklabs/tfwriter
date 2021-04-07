# akamai_edge_hostname

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_edge_hostname" {
  source = "./modules/akamai/r/akamai_edge_hostname"

  # certificate - (optional) is a type of number
  certificate = null
  # contract - (optional) is a type of string
  contract = null
  # contract_id - (optional) is a type of string
  contract_id = null
  # edge_hostname - (required) is a type of string
  edge_hostname = null
  # group - (optional) is a type of string
  group = null
  # group_id - (optional) is a type of string
  group_id = null
  # ip_behavior - (required) is a type of string
  ip_behavior = null
  # product - (optional) is a type of string
  product = null
  # product_id - (optional) is a type of string
  product_id = null
}
```

[top](#index)

### Variables

```terraform
variable "certificate" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "contract" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "contract_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "edge_hostname" {
  description = "(required)"
  type        = string
}

variable "group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_behavior" {
  description = "(required)"
  type        = string
}

variable "product" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "product_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "akamai_edge_hostname" "this" {
  # certificate - (optional) is a type of number
  certificate = var.certificate
  # contract - (optional) is a type of string
  contract = var.contract
  # contract_id - (optional) is a type of string
  contract_id = var.contract_id
  # edge_hostname - (required) is a type of string
  edge_hostname = var.edge_hostname
  # group - (optional) is a type of string
  group = var.group
  # group_id - (optional) is a type of string
  group_id = var.group_id
  # ip_behavior - (required) is a type of string
  ip_behavior = var.ip_behavior
  # product - (optional) is a type of string
  product = var.product
  # product_id - (optional) is a type of string
  product_id = var.product_id
}
```

[top](#index)

### Outputs

```terraform
output "contract" {
  description = "returns a string"
  value       = akamai_edge_hostname.this.contract
}

output "contract_id" {
  description = "returns a string"
  value       = akamai_edge_hostname.this.contract_id
}

output "group" {
  description = "returns a string"
  value       = akamai_edge_hostname.this.group
}

output "group_id" {
  description = "returns a string"
  value       = akamai_edge_hostname.this.group_id
}

output "id" {
  description = "returns a string"
  value       = akamai_edge_hostname.this.id
}

output "product" {
  description = "returns a string"
  value       = akamai_edge_hostname.this.product
}

output "product_id" {
  description = "returns a string"
  value       = akamai_edge_hostname.this.product_id
}

output "this" {
  value = akamai_edge_hostname.this
}
```

[top](#index)