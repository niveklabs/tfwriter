# newrelic_entity

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
    newrelic = ">= 2.14.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "newrelic_entity" {
  source = "./modules/newrelic/d/newrelic_entity"

  # domain - (optional) is a type of string
  domain = null
  # name - (required) is a type of string
  name = null
  # type - (optional) is a type of string
  type = null

  tag = [{
    key   = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "domain" {
  description = "(optional) - The entity's domain. Valid values are APM, BROWSER, INFRA, MOBILE, SYNTH, and VIZ. If not specified, all domains are searched."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The name of the entity in New Relic One.  The first entity matching this name for the given search parameters will be returned."
  type        = string
}

variable "type" {
  description = "(optional) - The entity's type. Valid values are APPLICATION, DASHBOARD, HOST, MONITOR, and WORKLOAD."
  type        = string
  default     = null
}

variable "tag" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      key   = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "newrelic_entity" "this" {
  domain = var.domain
  name   = var.name
  type   = var.type

  dynamic "tag" {
    for_each = var.tag
    content {
      key   = tag.value["key"]
      value = tag.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "account_id" {
  description = "returns a number"
  value       = data.newrelic_entity.this.account_id
}

output "application_id" {
  description = "returns a number"
  value       = data.newrelic_entity.this.application_id
}

output "domain" {
  description = "returns a string"
  value       = data.newrelic_entity.this.domain
}

output "guid" {
  description = "returns a string"
  value       = data.newrelic_entity.this.guid
}

output "id" {
  description = "returns a string"
  value       = data.newrelic_entity.this.id
}

output "serving_apm_application_id" {
  description = "returns a number"
  value       = data.newrelic_entity.this.serving_apm_application_id
}

output "type" {
  description = "returns a string"
  value       = data.newrelic_entity.this.type
}

output "this" {
  value = newrelic_entity.this
}
```

[top](#index)