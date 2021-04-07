# ns1_record

[back](../ns1.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ns1 = ">= 1.9.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ns1_record" {
  source = "./modules/ns1/r/ns1_record"

  # domain - (required) is a type of string
  domain = null
  # link - (optional) is a type of string
  link = null
  # meta - (optional) is a type of map of string
  meta = {}
  # short_answers - (optional) is a type of list of string
  short_answers = []
  # ttl - (optional) is a type of number
  ttl = null
  # type - (required) is a type of string
  type = null
  # use_client_subnet - (optional) is a type of bool
  use_client_subnet = null
  # zone - (required) is a type of string
  zone = null

  answers = [{
    answer = null
    meta   = {}
    region = null
  }]

  filters = [{
    config   = {}
    disabled = null
    filter   = null
  }]

  regions = [{
    meta = {}
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "domain" {
  description = "(required)"
  type        = string
}

variable "link" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "meta" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "short_answers" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "use_client_subnet" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "zone" {
  description = "(required)"
  type        = string
}

variable "answers" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      answer = string
      meta   = map(string)
      region = string
    }
  ))
  default = []
}

variable "filters" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      config   = map(string)
      disabled = bool
      filter   = string
    }
  ))
  default = []
}

variable "regions" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      meta = map(string)
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "ns1_record" "this" {
  # domain - (required) is a type of string
  domain = var.domain
  # link - (optional) is a type of string
  link = var.link
  # meta - (optional) is a type of map of string
  meta = var.meta
  # short_answers - (optional) is a type of list of string
  short_answers = var.short_answers
  # ttl - (optional) is a type of number
  ttl = var.ttl
  # type - (required) is a type of string
  type = var.type
  # use_client_subnet - (optional) is a type of bool
  use_client_subnet = var.use_client_subnet
  # zone - (required) is a type of string
  zone = var.zone

  dynamic "answers" {
    for_each = var.answers
    content {
      # answer - (optional) is a type of string
      answer = answers.value["answer"]
      # meta - (optional) is a type of map of string
      meta = answers.value["meta"]
      # region - (optional) is a type of string
      region = answers.value["region"]
    }
  }

  dynamic "filters" {
    for_each = var.filters
    content {
      # config - (optional) is a type of map of string
      config = filters.value["config"]
      # disabled - (optional) is a type of bool
      disabled = filters.value["disabled"]
      # filter - (required) is a type of string
      filter = filters.value["filter"]
    }
  }

  dynamic "regions" {
    for_each = var.regions
    content {
      # meta - (optional) is a type of map of string
      meta = regions.value["meta"]
      # name - (required) is a type of string
      name = regions.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ns1_record.this.id
}

output "ttl" {
  description = "returns a number"
  value       = ns1_record.this.ttl
}

output "this" {
  value = ns1_record.this
}
```

[top](#index)