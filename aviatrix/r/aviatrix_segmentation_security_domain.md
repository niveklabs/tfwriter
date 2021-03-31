# aviatrix_segmentation_security_domain

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
module "aviatrix_segmentation_security_domain" {
  source = "./modules/aviatrix/r/aviatrix_segmentation_security_domain"

  # domain_name - (required) is a type of string
  domain_name = null
}
```

[top](#index)

### Variables

```terraform
variable "domain_name" {
  description = "(required) - Security domain name."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_segmentation_security_domain" "this" {
  domain_name = var.domain_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_segmentation_security_domain.this.id
}

output "this" {
  value = aviatrix_segmentation_security_domain.this
}
```

[top](#index)