# thunder_slb_template_http_policy

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_slb_template_http_policy" {
  source = "./modules/thunder/r/thunder_slb_template_http_policy"

  # cookie_name - (optional) is a type of string
  cookie_name = null
  # name - (optional) is a type of string
  name = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null

  geo_location_match = [{
    geo_location               = null
    geo_location_service_group = null
    geo_location_template      = null
    geo_location_template_name = null
  }]

  http_policy_match = [{
    match_string       = null
    match_type         = null
    other_match_string = null
    other_match_type   = null
    service_group      = null
    template           = null
    template_name      = null
    type               = null
    url_under_host     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cookie_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "geo_location_match" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      geo_location               = string
      geo_location_service_group = string
      geo_location_template      = string
      geo_location_template_name = string
    }
  ))
  default = []
}

variable "http_policy_match" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      match_string       = string
      match_type         = string
      other_match_string = string
      other_match_type   = string
      service_group      = string
      template           = string
      template_name      = string
      type               = string
      url_under_host     = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_template_http_policy" "this" {
  cookie_name = var.cookie_name
  name        = var.name
  user_tag    = var.user_tag
  uuid        = var.uuid

  dynamic "geo_location_match" {
    for_each = var.geo_location_match
    content {
      geo_location               = geo_location_match.value["geo_location"]
      geo_location_service_group = geo_location_match.value["geo_location_service_group"]
      geo_location_template      = geo_location_match.value["geo_location_template"]
      geo_location_template_name = geo_location_match.value["geo_location_template_name"]
    }
  }

  dynamic "http_policy_match" {
    for_each = var.http_policy_match
    content {
      match_string       = http_policy_match.value["match_string"]
      match_type         = http_policy_match.value["match_type"]
      other_match_string = http_policy_match.value["other_match_string"]
      other_match_type   = http_policy_match.value["other_match_type"]
      service_group      = http_policy_match.value["service_group"]
      template           = http_policy_match.value["template"]
      template_name      = http_policy_match.value["template_name"]
      type               = http_policy_match.value["type"]
      url_under_host     = http_policy_match.value["url_under_host"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_http_policy.this.id
}

output "this" {
  value = thunder_slb_template_http_policy.this
}
```

[top](#index)