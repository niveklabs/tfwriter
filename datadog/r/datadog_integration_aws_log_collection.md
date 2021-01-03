# datadog_integration_aws_log_collection

[back](../datadog.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    datadog = ">= 2.18.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "datadog_integration_aws_log_collection" {
  source = "./modules/datadog/r/datadog_integration_aws_log_collection"

  # account_id - (required) is a type of string
  account_id = null
  # services - (required) is a type of list of string
  services = []
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(required)"
  type        = string
}

variable "services" {
  description = "(required)"
  type        = list(string)
}
```

[top](#index)

### Resource

```terraform
resource "datadog_integration_aws_log_collection" "this" {
  account_id = var.account_id
  services   = var.services
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_integration_aws_log_collection.this.id
}

output "this" {
  value = datadog_integration_aws_log_collection.this
}
```

[top](#index)