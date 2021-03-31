# aviatrix_controller_private_oob

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.18.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_controller_private_oob" {
  source = "./modules/aviatrix/r/aviatrix_controller_private_oob"

  # enable_private_oob - (optional) is a type of bool
  enable_private_oob = null
}
```

[top](#index)

### Variables

```terraform
variable "enable_private_oob" {
  description = "(optional) - Switch to enable/disable Aviatrix controller private OOB."
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_controller_private_oob" "this" {
  enable_private_oob = var.enable_private_oob
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_controller_private_oob.this.id
}

output "this" {
  value = aviatrix_controller_private_oob.this
}
```

[top](#index)