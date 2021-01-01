# google_access_context_manager_access_level_condition

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "google_access_context_manager_access_level_condition" {
  source = "./modules/google/r/google_access_context_manager_access_level_condition"

  # access_level - (required) is a type of string
  access_level = null
  # ip_subnetworks - (optional) is a type of list of string
  ip_subnetworks = []
  # members - (optional) is a type of list of string
  members = []
  # negate - (optional) is a type of bool
  negate = null
  # regions - (optional) is a type of list of string
  regions = []
  # required_access_levels - (optional) is a type of list of string
  required_access_levels = []

  device_policy = [{
    allowed_device_management_levels = []
    allowed_encryption_statuses      = []
    os_constraints = [{
      minimum_version = null
      os_type         = null
    }]
    require_admin_approval = null
    require_corp_owned     = null
    require_screen_lock    = null
  }]

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "access_level" {
  description = "(required) - The name of the Access Level to add this condition to."
  type        = string
}

variable "ip_subnetworks" {
  description = "(optional) - A list of CIDR block IP subnetwork specification. May be IPv4\nor IPv6.\nNote that for a CIDR IP address block, the specified IP address\nportion must be properly truncated (i.e. all the host bits must\nbe zero) or the input is considered malformed. For example,\n\"192.0.2.0/24\" is accepted but \"192.0.2.1/24\" is not. Similarly,\nfor IPv6, \"2001:db8::/32\" is accepted whereas \"2001:db8::1/32\"\nis not. The originating IP of a request must be in one of the\nlisted subnets in order for this Condition to be true.\nIf empty, all IP addresses are allowed."
  type        = list(string)
  default     = null
}

variable "members" {
  description = "(optional) - An allowed list of members (users, service accounts).\nUsing groups is not supported yet.\n\nThe signed-in user originating the request must be a part of one\nof the provided members. If not specified, a request may come\nfrom any user (logged in/not logged in, not present in any\ngroups, etc.).\nFormats: 'user:{emailid}', 'serviceAccount:{emailid}'"
  type        = list(string)
  default     = null
}

variable "negate" {
  description = "(optional) - Whether to negate the Condition. If true, the Condition becomes\na NAND over its non-empty fields, each field must be false for\nthe Condition overall to be satisfied. Defaults to false."
  type        = bool
  default     = null
}

variable "regions" {
  description = "(optional) - The request must originate from one of the provided\ncountries/regions.\nFormat: A valid ISO 3166-1 alpha-2 code."
  type        = list(string)
  default     = null
}

variable "required_access_levels" {
  description = "(optional) - A list of other access levels defined in the same Policy,\nreferenced by resource name. Referencing an AccessLevel which\ndoes not exist is an error. All access levels listed must be\ngranted for the Condition to be true.\nFormat: accessPolicies/{policy_id}/accessLevels/{short_name}"
  type        = list(string)
  default     = null
}

variable "device_policy" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      allowed_device_management_levels = list(string)
      allowed_encryption_statuses      = list(string)
      os_constraints = list(object(
        {
          minimum_version = string
          os_type         = string
        }
      ))
      require_admin_approval = bool
      require_corp_owned     = bool
      require_screen_lock    = bool
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "google_access_context_manager_access_level_condition" "this" {
  access_level           = var.access_level
  ip_subnetworks         = var.ip_subnetworks
  members                = var.members
  negate                 = var.negate
  regions                = var.regions
  required_access_levels = var.required_access_levels

  dynamic "device_policy" {
    for_each = var.device_policy
    content {
      allowed_device_management_levels = device_policy.value["allowed_device_management_levels"]
      allowed_encryption_statuses      = device_policy.value["allowed_encryption_statuses"]
      require_admin_approval           = device_policy.value["require_admin_approval"]
      require_corp_owned               = device_policy.value["require_corp_owned"]
      require_screen_lock              = device_policy.value["require_screen_lock"]

      dynamic "os_constraints" {
        for_each = device_policy.value.os_constraints
        content {
          minimum_version = os_constraints.value["minimum_version"]
          os_type         = os_constraints.value["os_type"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = google_access_context_manager_access_level_condition.this.id
}

output "this" {
  value = google_access_context_manager_access_level_condition.this
}
```

[top](#index)