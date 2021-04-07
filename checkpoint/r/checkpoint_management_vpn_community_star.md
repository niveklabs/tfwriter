# checkpoint_management_vpn_community_star

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    checkpoint = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_vpn_community_star" {
  source = "./modules/checkpoint/r/checkpoint_management_vpn_community_star"

  # center_gateways - (optional) is a type of set of string
  center_gateways = []
  # color - (optional) is a type of string
  color = null
  # comments - (optional) is a type of string
  comments = null
  # encryption_method - (optional) is a type of string
  encryption_method = null
  # encryption_suite - (optional) is a type of string
  encryption_suite = null
  # ignore_errors - (optional) is a type of bool
  ignore_errors = null
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = null
  # ike_phase_1 - (optional) is a type of map of string
  ike_phase_1 = {}
  # ike_phase_2 - (optional) is a type of map of string
  ike_phase_2 = {}
  # mesh_center_gateways - (optional) is a type of bool
  mesh_center_gateways = null
  # name - (required) is a type of string
  name = null
  # satellite_gateways - (optional) is a type of set of string
  satellite_gateways = []
  # tags - (optional) is a type of set of string
  tags = []
  # use_shared_secret - (optional) is a type of bool
  use_shared_secret = null

  override_vpn_domains = [{
    gateway    = null
    vpn_domain = null
  }]

  shared_secrets = [{
    external_gateway = null
    shared_secret    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "center_gateways" {
  description = "(optional) - Collection of Gateway objects representing center gateways identified by the name or UID."
  type        = set(string)
  default     = null
}

variable "color" {
  description = "(optional) - Color of the object. Should be one of existing colors."
  type        = string
  default     = null
}

variable "comments" {
  description = "(optional) - Comments string."
  type        = string
  default     = null
}

variable "encryption_method" {
  description = "(optional) - The encryption method to be used."
  type        = string
  default     = null
}

variable "encryption_suite" {
  description = "(optional) - The encryption suite to be used."
  type        = string
  default     = null
}

variable "ignore_errors" {
  description = "(optional) - Apply changes ignoring errors. You won't be able to publish such a changes. If ignore-warnings flag was omitted - warnings will also be ignored."
  type        = bool
  default     = null
}

variable "ignore_warnings" {
  description = "(optional) - Apply changes ignoring warnings."
  type        = bool
  default     = null
}

variable "ike_phase_1" {
  description = "(optional) - Ike Phase 1 settings. Only applicable when the encryption-suite is set to [custom]."
  type        = map(string)
  default     = null
}

variable "ike_phase_2" {
  description = "(optional) - Ike Phase 2 settings. Only applicable when the encryption-suite is set to [custom]."
  type        = map(string)
  default     = null
}

variable "mesh_center_gateways" {
  description = "(optional) - Indicates whether the meshed community is in center."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Object name."
  type        = string
}

variable "satellite_gateways" {
  description = "(optional) - Collection of Gateway objects representing satellite gateways identified by the name or UID."
  type        = set(string)
  default     = null
}

variable "tags" {
  description = "(optional) - Collection of tag identifiers."
  type        = set(string)
  default     = null
}

variable "use_shared_secret" {
  description = "(optional) - Indicates whether the shared secret should be used for all external gateways."
  type        = bool
  default     = null
}

variable "override_vpn_domains" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      gateway    = string
      vpn_domain = string
    }
  ))
  default = []
}

variable "shared_secrets" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      external_gateway = string
      shared_secret    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_vpn_community_star" "this" {
  # center_gateways - (optional) is a type of set of string
  center_gateways = var.center_gateways
  # color - (optional) is a type of string
  color = var.color
  # comments - (optional) is a type of string
  comments = var.comments
  # encryption_method - (optional) is a type of string
  encryption_method = var.encryption_method
  # encryption_suite - (optional) is a type of string
  encryption_suite = var.encryption_suite
  # ignore_errors - (optional) is a type of bool
  ignore_errors = var.ignore_errors
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = var.ignore_warnings
  # ike_phase_1 - (optional) is a type of map of string
  ike_phase_1 = var.ike_phase_1
  # ike_phase_2 - (optional) is a type of map of string
  ike_phase_2 = var.ike_phase_2
  # mesh_center_gateways - (optional) is a type of bool
  mesh_center_gateways = var.mesh_center_gateways
  # name - (required) is a type of string
  name = var.name
  # satellite_gateways - (optional) is a type of set of string
  satellite_gateways = var.satellite_gateways
  # tags - (optional) is a type of set of string
  tags = var.tags
  # use_shared_secret - (optional) is a type of bool
  use_shared_secret = var.use_shared_secret

  dynamic "override_vpn_domains" {
    for_each = var.override_vpn_domains
    content {
      # gateway - (optional) is a type of string
      gateway = override_vpn_domains.value["gateway"]
      # vpn_domain - (optional) is a type of string
      vpn_domain = override_vpn_domains.value["vpn_domain"]
    }
  }

  dynamic "shared_secrets" {
    for_each = var.shared_secrets
    content {
      # external_gateway - (optional) is a type of string
      external_gateway = shared_secrets.value["external_gateway"]
      # shared_secret - (optional) is a type of string
      shared_secret = shared_secrets.value["shared_secret"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_vpn_community_star.this.id
}

output "this" {
  value = checkpoint_management_vpn_community_star.this
}
```

[top](#index)