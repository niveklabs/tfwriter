# thunder_ip_dns_suffix

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
module "thunder_ip_dns_suffix" {
  source = "./modules/thunder/r/thunder_ip_dns_suffix"

  # domain_name - (optional) is a type of string
  domain_name = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "domain_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "thunder_ip_dns_suffix" "this" {
  domain_name = var.domain_name
  uuid        = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_ip_dns_suffix.this.id
}

output "this" {
  value = thunder_ip_dns_suffix.this
}
```

[top](#index)