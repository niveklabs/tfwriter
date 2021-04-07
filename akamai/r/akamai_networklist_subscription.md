# akamai_networklist_subscription

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_networklist_subscription" {
  source = "./modules/akamai/r/akamai_networklist_subscription"

  # network_list - (required) is a type of list of string
  network_list = []
  # recipients - (required) is a type of list of string
  recipients = []
}
```

[top](#index)

### Variables

```terraform
variable "network_list" {
  description = "(required)"
  type        = list(string)
}

variable "recipients" {
  description = "(required)"
  type        = list(string)
}
```

[top](#index)

### Resource

```terraform
resource "akamai_networklist_subscription" "this" {
  # network_list - (required) is a type of list of string
  network_list = var.network_list
  # recipients - (required) is a type of list of string
  recipients = var.recipients
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_networklist_subscription.this.id
}

output "this" {
  value = akamai_networklist_subscription.this
}
```

[top](#index)