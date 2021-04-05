# signalfx_pagerduty_integration

[back](../signalfx.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    signalfx = ">= 6.7.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "signalfx_pagerduty_integration" {
  source = "./modules/signalfx/d/signalfx_pagerduty_integration"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "signalfx_pagerduty_integration" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "enabled" {
  description = "returns a bool"
  value       = data.signalfx_pagerduty_integration.this.enabled
}

output "id" {
  description = "returns a string"
  value       = data.signalfx_pagerduty_integration.this.id
}

output "this" {
  value = signalfx_pagerduty_integration.this
}
```

[top](#index)