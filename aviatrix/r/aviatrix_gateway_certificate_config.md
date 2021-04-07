# aviatrix_gateway_certificate_config

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
module "aviatrix_gateway_certificate_config" {
  source = "./modules/aviatrix/r/aviatrix_gateway_certificate_config"

  # ca_certificate - (required) is a type of string
  ca_certificate = null
  # ca_private_key - (required) is a type of string
  ca_private_key = null
}
```

[top](#index)

### Variables

```terraform
variable "ca_certificate" {
  description = "(required) - CA Certificate."
  type        = string
}

variable "ca_private_key" {
  description = "(required) - CA Private Key."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_gateway_certificate_config" "this" {
  # ca_certificate - (required) is a type of string
  ca_certificate = var.ca_certificate
  # ca_private_key - (required) is a type of string
  ca_private_key = var.ca_private_key
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_gateway_certificate_config.this.id
}

output "this" {
  value = aviatrix_gateway_certificate_config.this
}
```

[top](#index)