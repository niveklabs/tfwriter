# scaleway_object_bucket

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
module "scaleway_object_bucket" {
  source = "./modules/scaleway/r/scaleway_object_bucket"

  # acl - (optional) is a type of string
  acl = null
  # name - (required) is a type of string
  name = null
  # region - (optional) is a type of string
  region = null
  # tags - (optional) is a type of map of string
  tags = {}

  cors_rule = [{
    allowed_headers = []
    allowed_methods = []
    allowed_origins = []
    expose_headers  = []
    max_age_seconds = null
  }]

  timeouts = [{
    default = null
  }]

  versioning = [{
    enabled = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "acl" {
  description = "(optional) - ACL of the bucket: either 'public-read' or 'private'."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The name of the bucket"
  type        = string
}

variable "region" {
  description = "(optional) - The region you want to attach the resource to"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - The tags associated with this bucket"
  type        = map(string)
  default     = null
}

variable "cors_rule" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      allowed_headers = list(string)
      allowed_methods = list(string)
      allowed_origins = list(string)
      expose_headers  = list(string)
      max_age_seconds = number
    }
  ))
  default = []
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

variable "versioning" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "scaleway_object_bucket" "this" {
  # acl - (optional) is a type of string
  acl = var.acl
  # name - (required) is a type of string
  name = var.name
  # region - (optional) is a type of string
  region = var.region
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "cors_rule" {
    for_each = var.cors_rule
    content {
      # allowed_headers - (optional) is a type of list of string
      allowed_headers = cors_rule.value["allowed_headers"]
      # allowed_methods - (required) is a type of list of string
      allowed_methods = cors_rule.value["allowed_methods"]
      # allowed_origins - (required) is a type of list of string
      allowed_origins = cors_rule.value["allowed_origins"]
      # expose_headers - (optional) is a type of list of string
      expose_headers = cors_rule.value["expose_headers"]
      # max_age_seconds - (optional) is a type of number
      max_age_seconds = cors_rule.value["max_age_seconds"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # default - (optional) is a type of string
      default = timeouts.value["default"]
    }
  }

  dynamic "versioning" {
    for_each = var.versioning
    content {
      # enabled - (optional) is a type of bool
      enabled = versioning.value["enabled"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "endpoint" {
  description = "returns a string"
  value       = scaleway_object_bucket.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = scaleway_object_bucket.this.id
}

output "region" {
  description = "returns a string"
  value       = scaleway_object_bucket.this.region
}

output "this" {
  value = scaleway_object_bucket.this
}
```

[top](#index)