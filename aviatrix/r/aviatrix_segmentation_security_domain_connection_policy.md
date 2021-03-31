# aviatrix_segmentation_security_domain_connection_policy

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
module "aviatrix_segmentation_security_domain_connection_policy" {
  source = "./modules/aviatrix/r/aviatrix_segmentation_security_domain_connection_policy"

  # domain_name_1 - (required) is a type of string
  domain_name_1 = null
  # domain_name_2 - (required) is a type of string
  domain_name_2 = null
}
```

[top](#index)

### Variables

```terraform
variable "domain_name_1" {
  description = "(required) - Name of security domain that will be connected to domain 2."
  type        = string
}

variable "domain_name_2" {
  description = "(required) - Name of security domain that will be connected to domain 1."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_segmentation_security_domain_connection_policy" "this" {
  domain_name_1 = var.domain_name_1
  domain_name_2 = var.domain_name_2
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_segmentation_security_domain_connection_policy.this.id
}

output "this" {
  value = aviatrix_segmentation_security_domain_connection_policy.this
}
```

[top](#index)