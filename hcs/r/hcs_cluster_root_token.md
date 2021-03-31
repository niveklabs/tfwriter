# hcs_cluster_root_token

[back](../hcs.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    hcs = ">= 0.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcs_cluster_root_token" {
  source = "./modules/hcs/r/hcs_cluster_root_token"

  # managed_application_name - (required) is a type of string
  managed_application_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "managed_application_name" {
  description = "(required) - The name of the HCS Azure Managed Application."
  type        = string
}

variable "resource_group_name" {
  description = "(required) - The name of the Resource Group in which the HCS Azure Managed Application belongs."
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
resource "hcs_cluster_root_token" "this" {
  managed_application_name = var.managed_application_name
  resource_group_name      = var.resource_group_name

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
output "accessor_id" {
  description = "returns a string"
  value       = hcs_cluster_root_token.this.accessor_id
}

output "id" {
  description = "returns a string"
  value       = hcs_cluster_root_token.this.id
}

output "kubernetes_secret" {
  description = "returns a string"
  value       = hcs_cluster_root_token.this.kubernetes_secret
  sensitive   = true
}

output "secret_id" {
  description = "returns a string"
  value       = hcs_cluster_root_token.this.secret_id
  sensitive   = true
}

output "this" {
  value = hcs_cluster_root_token.this
}
```

[top](#index)