# cloudscale_objects_user

[back](../cloudscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    cloudscale = ">= 2.3.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudscale_objects_user" {
  source = "./modules/cloudscale/r/cloudscale_objects_user"

  # display_name - (required) is a type of string
  display_name = null
}
```

[top](#index)

### Variables

```terraform
variable "display_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "cloudscale_objects_user" "this" {
  # display_name - (required) is a type of string
  display_name = var.display_name
}
```

[top](#index)

### Outputs

```terraform
output "href" {
  description = "returns a string"
  value       = cloudscale_objects_user.this.href
}

output "id" {
  description = "returns a string"
  value       = cloudscale_objects_user.this.id
}

output "keys" {
  description = "returns a list of object"
  value       = cloudscale_objects_user.this.keys
}

output "user_id" {
  description = "returns a string"
  value       = cloudscale_objects_user.this.user_id
}

output "this" {
  value = cloudscale_objects_user.this
}
```

[top](#index)