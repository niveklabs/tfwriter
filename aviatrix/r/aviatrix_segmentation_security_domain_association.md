# aviatrix_segmentation_security_domain_association

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
module "aviatrix_segmentation_security_domain_association" {
  source = "./modules/aviatrix/r/aviatrix_segmentation_security_domain_association"

  # attachment_name - (required) is a type of string
  attachment_name = null
  # security_domain_name - (required) is a type of string
  security_domain_name = null
  # transit_gateway_name - (required) is a type of string
  transit_gateway_name = null
}
```

[top](#index)

### Variables

```terraform
variable "attachment_name" {
  description = "(required) - Attachment name, either Spoke or Edge."
  type        = string
}

variable "security_domain_name" {
  description = "(required) - Security Domain name."
  type        = string
}

variable "transit_gateway_name" {
  description = "(required) - Transit Gateway name."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_segmentation_security_domain_association" "this" {
  attachment_name      = var.attachment_name
  security_domain_name = var.security_domain_name
  transit_gateway_name = var.transit_gateway_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_segmentation_security_domain_association.this.id
}

output "this" {
  value = aviatrix_segmentation_security_domain_association.this
}
```

[top](#index)