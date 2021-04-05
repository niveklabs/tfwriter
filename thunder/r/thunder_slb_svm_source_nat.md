# thunder_slb_svm_source_nat

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_slb_svm_source_nat" {
  source = "./modules/thunder/r/thunder_slb_svm_source_nat"

  # pool - (optional) is a type of string
  pool = null
}
```

[top](#index)

### Variables

```terraform
variable "pool" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_svm_source_nat" "this" {
  pool = var.pool
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_svm_source_nat.this.id
}

output "this" {
  value = thunder_slb_svm_source_nat.this
}
```

[top](#index)