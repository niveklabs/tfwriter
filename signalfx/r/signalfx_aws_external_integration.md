# signalfx_aws_external_integration

[back](../signalfx.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "signalfx_aws_external_integration" {
  source = "./modules/signalfx/r/signalfx_aws_external_integration"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of the integration"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "signalfx_aws_external_integration" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "external_id" {
  description = "returns a string"
  value       = signalfx_aws_external_integration.this.external_id
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = signalfx_aws_external_integration.this.id
}

output "signalfx_aws_account" {
  description = "returns a string"
  value       = signalfx_aws_external_integration.this.signalfx_aws_account
  sensitive   = true
}

output "this" {
  value = signalfx_aws_external_integration.this
}
```

[top](#index)