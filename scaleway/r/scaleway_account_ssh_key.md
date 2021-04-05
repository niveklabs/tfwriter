# scaleway_account_ssh_key

[back](../scaleway.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    scaleway = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "scaleway_account_ssh_key" {
  source = "./modules/scaleway/r/scaleway_account_ssh_key"

  # name - (optional) is a type of string
  name = null
  # project_id - (optional) is a type of string
  project_id = null
  # public_key - (required) is a type of string
  public_key = null

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - The name of the SSH key"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional) - The project_id you want to attach the resource to"
  type        = string
  default     = null
}

variable "public_key" {
  description = "(required) - The public SSH key"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      default = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "scaleway_account_ssh_key" "this" {
  name       = var.name
  project_id = var.project_id
  public_key = var.public_key

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      default = timeouts.value["default"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = scaleway_account_ssh_key.this.id
}

output "organization_id" {
  description = "returns a string"
  value       = scaleway_account_ssh_key.this.organization_id
}

output "project_id" {
  description = "returns a string"
  value       = scaleway_account_ssh_key.this.project_id
}

output "this" {
  value = scaleway_account_ssh_key.this
}
```

[top](#index)