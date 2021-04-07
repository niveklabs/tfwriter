# thunder_glm_send

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
module "thunder_glm_send" {
  source = "./modules/thunder/r/thunder_glm_send"

  # license_request - (optional) is a type of number
  license_request = null
}
```

[top](#index)

### Variables

```terraform
variable "license_request" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "thunder_glm_send" "this" {
  # license_request - (optional) is a type of number
  license_request = var.license_request
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_glm_send.this.id
}

output "this" {
  value = thunder_glm_send.this
}
```

[top](#index)