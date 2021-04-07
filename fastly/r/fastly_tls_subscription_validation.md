# fastly_tls_subscription_validation

[back](../fastly.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fastly = ">= 0.27.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fastly_tls_subscription_validation" {
  source = "./modules/fastly/r/fastly_tls_subscription_validation"

  # subscription_id - (required) is a type of string
  subscription_id = null

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "subscription_id" {
  description = "(required) - The ID of the TLS Subscription that should be validated."
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fastly_tls_subscription_validation" "this" {
  # subscription_id - (required) is a type of string
  subscription_id = var.subscription_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fastly_tls_subscription_validation.this.id
}

output "this" {
  value = fastly_tls_subscription_validation.this
}
```

[top](#index)