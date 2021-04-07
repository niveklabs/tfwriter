# newrelic_application

[back](../newrelic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    newrelic = ">= 2.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "newrelic_application" {
  source = "./modules/newrelic/d/newrelic_application"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - The name of the application in New Relic."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "newrelic_application" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "host_ids" {
  description = "returns a list of number"
  value       = data.newrelic_application.this.host_ids
}

output "id" {
  description = "returns a string"
  value       = data.newrelic_application.this.id
}

output "instance_ids" {
  description = "returns a list of number"
  value       = data.newrelic_application.this.instance_ids
}

output "this" {
  value = newrelic_application.this
}
```

[top](#index)