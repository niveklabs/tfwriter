# dome9_cloudaccount_kubernetes

[back](../dome9.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dome9 = ">= 1.20.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dome9_cloudaccount_kubernetes" {
  source = "./modules/dome9/r/dome9_cloudaccount_kubernetes"

  # name - (required) is a type of string
  name = null
  # organizational_unit_id - (optional) is a type of string
  organizational_unit_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "organizational_unit_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "dome9_cloudaccount_kubernetes" "this" {
  name                   = var.name
  organizational_unit_id = var.organizational_unit_id
}
```

[top](#index)

### Outputs

```terraform
output "cluster_version" {
  description = "returns a string"
  value       = dome9_cloudaccount_kubernetes.this.cluster_version
}

output "creation_date" {
  description = "returns a string"
  value       = dome9_cloudaccount_kubernetes.this.creation_date
}

output "id" {
  description = "returns a string"
  value       = dome9_cloudaccount_kubernetes.this.id
}

output "organizational_unit_name" {
  description = "returns a string"
  value       = dome9_cloudaccount_kubernetes.this.organizational_unit_name
}

output "organizational_unit_path" {
  description = "returns a string"
  value       = dome9_cloudaccount_kubernetes.this.organizational_unit_path
}

output "vendor" {
  description = "returns a string"
  value       = dome9_cloudaccount_kubernetes.this.vendor
}

output "this" {
  value = dome9_cloudaccount_kubernetes.this
}
```

[top](#index)