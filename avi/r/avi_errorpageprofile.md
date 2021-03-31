# avi_errorpageprofile

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
module "avi_errorpageprofile" {
  source = "./modules/avi/r/avi_errorpageprofile"

  # name - (optional) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null

  error_pages = [{
    enable              = null
    error_page_body_ref = null
    error_redirect      = null
    index               = null
    match = [{
      match_criteria = null
      ranges = [{
        begin = null
        end   = null
      }]
      status_codes = []
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
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

variable "error_pages" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      enable              = bool
      error_page_body_ref = string
      error_redirect      = string
      index               = number
      match = set(object(
        {
          match_criteria = string
          ranges = list(object(
            {
              begin = number
              end   = number
            }
          ))
          status_codes = list(number)
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
resource "avi_errorpageprofile" "this" {
  name       = var.name
  tenant_ref = var.tenant_ref
  uuid       = var.uuid

  dynamic "error_pages" {
    for_each = var.error_pages
    content {
      enable              = error_pages.value["enable"]
      error_page_body_ref = error_pages.value["error_page_body_ref"]
      error_redirect      = error_pages.value["error_redirect"]
      index               = error_pages.value["index"]

      dynamic "match" {
        for_each = error_pages.value.match
        content {
          match_criteria = match.value["match_criteria"]
          status_codes   = match.value["status_codes"]

          dynamic "ranges" {
            for_each = match.value.ranges
            content {
              begin = ranges.value["begin"]
              end   = ranges.value["end"]
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
output "id" {
  description = "returns a string"
  value       = avi_errorpageprofile.this.id
}

output "name" {
  description = "returns a string"
  value       = avi_errorpageprofile.this.name
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_errorpageprofile.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_errorpageprofile.this.uuid
}

output "this" {
  value = avi_errorpageprofile.this
}
```

[top](#index)