# launchdarkly_feature_flag

[back](../launchdarkly.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    launchdarkly = ">= 1.5.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "launchdarkly_feature_flag" {
  source = "./modules/launchdarkly/d/launchdarkly_feature_flag"

  # default_off_variation - (optional) is a type of string
  default_off_variation = null
  # default_on_variation - (optional) is a type of string
  default_on_variation = null
  # description - (optional) is a type of string
  description = null
  # include_in_snippet - (optional) is a type of bool
  include_in_snippet = null
  # key - (required) is a type of string
  key = null
  # maintainer_id - (optional) is a type of string
  maintainer_id = null
  # project_key - (required) is a type of string
  project_key = null
  # tags - (optional) is a type of set of string
  tags = []
  # temporary - (optional) is a type of bool
  temporary = null

  custom_properties = [{
    key   = null
    name  = null
    value = []
  }]

  variations = [{
    description = null
    name        = null
    value       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "default_off_variation" {
  description = "(optional) - The value of the variation served when the flag is off for new environments"
  type        = string
  default     = null
}

variable "default_on_variation" {
  description = "(optional) - The value of the variation served when the flag is on for new environments"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "include_in_snippet" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "key" {
  description = "(required) - The human-readable name of the feature flag"
  type        = string
}

variable "maintainer_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_key" {
  description = "(required) - The feature flag's project key"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "temporary" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "custom_properties" {
  description = "nested block: NestingSet, min items: 0, max items: 64"
  type = set(object(
    {
      key   = string
      name  = string
      value = list(string)
    }
  ))
  default = []
}

variable "variations" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      description = string
      name        = string
      value       = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "launchdarkly_feature_flag" "this" {
  default_off_variation = var.default_off_variation
  default_on_variation  = var.default_on_variation
  description           = var.description
  include_in_snippet    = var.include_in_snippet
  key                   = var.key
  maintainer_id         = var.maintainer_id
  project_key           = var.project_key
  tags                  = var.tags
  temporary             = var.temporary

  dynamic "custom_properties" {
    for_each = var.custom_properties
    content {
      key   = custom_properties.value["key"]
      name  = custom_properties.value["name"]
      value = custom_properties.value["value"]
    }
  }

  dynamic "variations" {
    for_each = var.variations
    content {
      description = variations.value["description"]
      name        = variations.value["name"]
      value       = variations.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "client_side_availability" {
  description = "returns a map of string"
  value       = data.launchdarkly_feature_flag.this.client_side_availability
}

output "id" {
  description = "returns a string"
  value       = data.launchdarkly_feature_flag.this.id
}

output "name" {
  description = "returns a string"
  value       = data.launchdarkly_feature_flag.this.name
}

output "variation_type" {
  description = "returns a string"
  value       = data.launchdarkly_feature_flag.this.variation_type
}

output "this" {
  value = launchdarkly_feature_flag.this
}
```

[top](#index)