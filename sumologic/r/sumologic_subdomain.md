# sumologic_subdomain

[back](../sumologic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    sumologic = ">= 2.9.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "sumologic_subdomain" {
  source = "./modules/sumologic/r/sumologic_subdomain"

  # subdomain - (required) is a type of string
  subdomain = null
}
```

[top](#index)

### Variables

```terraform
variable "subdomain" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "sumologic_subdomain" "this" {
  subdomain = var.subdomain
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = sumologic_subdomain.this.id
}

output "this" {
  value = sumologic_subdomain.this
}
```

[top](#index)