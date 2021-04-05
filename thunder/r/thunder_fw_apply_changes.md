# thunder_fw_apply_changes

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
module "thunder_fw_apply_changes" {
  source = "./modules/thunder/r/thunder_fw_apply_changes"

  # forced - (optional) is a type of number
  forced = null
}
```

[top](#index)

### Variables

```terraform
variable "forced" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "thunder_fw_apply_changes" "this" {
  forced = var.forced
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_fw_apply_changes.this.id
}

output "this" {
  value = thunder_fw_apply_changes.this
}
```

[top](#index)