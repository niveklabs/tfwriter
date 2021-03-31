# avi_wafcrs

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_wafcrs" {
  source = "./modules/avi/r/avi_wafcrs"

  # description - (optional) is a type of string
  description = null
  # integrity - (optional) is a type of string
  integrity = null
  # name - (optional) is a type of string
  name = null
  # release_date - (optional) is a type of string
  release_date = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null
  # version - (optional) is a type of string
  version = null

  groups = [{
    enable = null
    exclude_list = [{
      client_subnet = [{
        ip_addr = [{
          addr = null
          type = null
        }]
        mask = null
      }]
      description   = null
      match_element = null
      match_element_criteria = [{
        match_case = null
        match_op   = null
      }]
      uri_match_criteria = [{
        match_case = null
        match_op   = null
      }]
      uri_path = null
    }]
    index = null
    name  = null
    rules = [{
      enable = null
      exclude_list = [{
        client_subnet = [{
          ip_addr = [{
            addr = null
            type = null
          }]
          mask = null
        }]
        description   = null
        match_element = null
        match_element_criteria = [{
          match_case = null
          match_op   = null
        }]
        uri_match_criteria = [{
          match_case = null
          match_op   = null
        }]
        uri_path = null
      }]
      index   = null
      mode    = null
      name    = null
      rule    = null
      rule_id = null
      tags    = []
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "integrity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "release_date" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "groups" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      enable = bool
      exclude_list = list(object(
        {
          client_subnet = set(object(
            {
              ip_addr = set(object(
                {
                  addr = string
                  type = string
                }
              ))
              mask = number
            }
          ))
          description   = string
          match_element = string
          match_element_criteria = set(object(
            {
              match_case = string
              match_op   = string
            }
          ))
          uri_match_criteria = set(object(
            {
              match_case = string
              match_op   = string
            }
          ))
          uri_path = string
        }
      ))
      index = number
      name  = string
      rules = list(object(
        {
          enable = bool
          exclude_list = list(object(
            {
              client_subnet = set(object(
                {
                  ip_addr = set(object(
                    {
                      addr = string
                      type = string
                    }
                  ))
                  mask = number
                }
              ))
              description   = string
              match_element = string
              match_element_criteria = set(object(
                {
                  match_case = string
                  match_op   = string
                }
              ))
              uri_match_criteria = set(object(
                {
                  match_case = string
                  match_op   = string
                }
              ))
              uri_path = string
            }
          ))
          index   = number
          mode    = string
          name    = string
          rule    = string
          rule_id = string
          tags    = list(string)
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_wafcrs" "this" {
  description  = var.description
  integrity    = var.integrity
  name         = var.name
  release_date = var.release_date
  tenant_ref   = var.tenant_ref
  uuid         = var.uuid
  version      = var.version

  dynamic "groups" {
    for_each = var.groups
    content {
      enable = groups.value["enable"]
      index  = groups.value["index"]
      name   = groups.value["name"]

      dynamic "exclude_list" {
        for_each = groups.value.exclude_list
        content {
          description   = exclude_list.value["description"]
          match_element = exclude_list.value["match_element"]
          uri_path      = exclude_list.value["uri_path"]

          dynamic "client_subnet" {
            for_each = exclude_list.value.client_subnet
            content {
              mask = client_subnet.value["mask"]

              dynamic "ip_addr" {
                for_each = client_subnet.value.ip_addr
                content {
                  addr = ip_addr.value["addr"]
                  type = ip_addr.value["type"]
                }
              }

            }
          }

          dynamic "match_element_criteria" {
            for_each = exclude_list.value.match_element_criteria
            content {
              match_case = match_element_criteria.value["match_case"]
              match_op   = match_element_criteria.value["match_op"]
            }
          }

          dynamic "uri_match_criteria" {
            for_each = exclude_list.value.uri_match_criteria
            content {
              match_case = uri_match_criteria.value["match_case"]
              match_op   = uri_match_criteria.value["match_op"]
            }
          }

        }
      }

      dynamic "rules" {
        for_each = groups.value.rules
        content {
          enable  = rules.value["enable"]
          index   = rules.value["index"]
          mode    = rules.value["mode"]
          name    = rules.value["name"]
          rule    = rules.value["rule"]
          rule_id = rules.value["rule_id"]
          tags    = rules.value["tags"]

          dynamic "exclude_list" {
            for_each = rules.value.exclude_list
            content {
              description   = exclude_list.value["description"]
              match_element = exclude_list.value["match_element"]
              uri_path      = exclude_list.value["uri_path"]

              dynamic "client_subnet" {
                for_each = exclude_list.value.client_subnet
                content {
                  mask = client_subnet.value["mask"]

                  dynamic "ip_addr" {
                    for_each = client_subnet.value.ip_addr
                    content {
                      addr = ip_addr.value["addr"]
                      type = ip_addr.value["type"]
                    }
                  }

                }
              }

              dynamic "match_element_criteria" {
                for_each = exclude_list.value.match_element_criteria
                content {
                  match_case = match_element_criteria.value["match_case"]
                  match_op   = match_element_criteria.value["match_op"]
                }
              }

              dynamic "uri_match_criteria" {
                for_each = exclude_list.value.uri_match_criteria
                content {
                  match_case = uri_match_criteria.value["match_case"]
                  match_op   = uri_match_criteria.value["match_op"]
                }
              }

            }
          }

        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = avi_wafcrs.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_wafcrs.this.id
}

output "integrity" {
  description = "returns a string"
  value       = avi_wafcrs.this.integrity
}

output "name" {
  description = "returns a string"
  value       = avi_wafcrs.this.name
}

output "release_date" {
  description = "returns a string"
  value       = avi_wafcrs.this.release_date
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_wafcrs.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_wafcrs.this.uuid
}

output "version" {
  description = "returns a string"
  value       = avi_wafcrs.this.version
}

output "this" {
  value = avi_wafcrs.this
}
```

[top](#index)