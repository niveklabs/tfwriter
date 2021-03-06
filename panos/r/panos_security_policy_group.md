# panos_security_policy_group

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_security_policy_group" {
  source = "./modules/panos/r/panos_security_policy_group"

  # position_keyword - (optional) is a type of string
  position_keyword = null
  # position_reference - (optional) is a type of string
  position_reference = null
  # vsys - (optional) is a type of string
  vsys = null

  rule = [{
    action                             = null
    applications                       = []
    categories                         = []
    data_filtering                     = null
    description                        = null
    destination_addresses              = []
    destination_zones                  = []
    disable_server_response_inspection = null
    disabled                           = null
    file_blocking                      = null
    group                              = null
    hip_profiles                       = []
    icmp_unreachable                   = null
    log_end                            = null
    log_setting                        = null
    log_start                          = null
    name                               = null
    negate_destination                 = null
    negate_source                      = null
    schedule                           = null
    services                           = []
    source_addresses                   = []
    source_users                       = []
    source_zones                       = []
    spyware                            = null
    tags                               = []
    type                               = null
    url_filtering                      = null
    virus                              = null
    vulnerability                      = null
    wildfire_analysis                  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "position_keyword" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "position_reference" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vsys" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rule" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      action                             = string
      applications                       = list(string)
      categories                         = list(string)
      data_filtering                     = string
      description                        = string
      destination_addresses              = list(string)
      destination_zones                  = list(string)
      disable_server_response_inspection = bool
      disabled                           = bool
      file_blocking                      = string
      group                              = string
      hip_profiles                       = list(string)
      icmp_unreachable                   = bool
      log_end                            = bool
      log_setting                        = string
      log_start                          = bool
      name                               = string
      negate_destination                 = bool
      negate_source                      = bool
      schedule                           = string
      services                           = list(string)
      source_addresses                   = list(string)
      source_users                       = list(string)
      source_zones                       = list(string)
      spyware                            = string
      tags                               = set(string)
      type                               = string
      url_filtering                      = string
      virus                              = string
      vulnerability                      = string
      wildfire_analysis                  = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "panos_security_policy_group" "this" {
  # position_keyword - (optional) is a type of string
  position_keyword = var.position_keyword
  # position_reference - (optional) is a type of string
  position_reference = var.position_reference
  # vsys - (optional) is a type of string
  vsys = var.vsys

  dynamic "rule" {
    for_each = var.rule
    content {
      # action - (optional) is a type of string
      action = rule.value["action"]
      # applications - (required) is a type of list of string
      applications = rule.value["applications"]
      # categories - (required) is a type of list of string
      categories = rule.value["categories"]
      # data_filtering - (optional) is a type of string
      data_filtering = rule.value["data_filtering"]
      # description - (optional) is a type of string
      description = rule.value["description"]
      # destination_addresses - (required) is a type of list of string
      destination_addresses = rule.value["destination_addresses"]
      # destination_zones - (required) is a type of list of string
      destination_zones = rule.value["destination_zones"]
      # disable_server_response_inspection - (optional) is a type of bool
      disable_server_response_inspection = rule.value["disable_server_response_inspection"]
      # disabled - (optional) is a type of bool
      disabled = rule.value["disabled"]
      # file_blocking - (optional) is a type of string
      file_blocking = rule.value["file_blocking"]
      # group - (optional) is a type of string
      group = rule.value["group"]
      # hip_profiles - (required) is a type of list of string
      hip_profiles = rule.value["hip_profiles"]
      # icmp_unreachable - (optional) is a type of bool
      icmp_unreachable = rule.value["icmp_unreachable"]
      # log_end - (optional) is a type of bool
      log_end = rule.value["log_end"]
      # log_setting - (optional) is a type of string
      log_setting = rule.value["log_setting"]
      # log_start - (optional) is a type of bool
      log_start = rule.value["log_start"]
      # name - (required) is a type of string
      name = rule.value["name"]
      # negate_destination - (optional) is a type of bool
      negate_destination = rule.value["negate_destination"]
      # negate_source - (optional) is a type of bool
      negate_source = rule.value["negate_source"]
      # schedule - (optional) is a type of string
      schedule = rule.value["schedule"]
      # services - (required) is a type of list of string
      services = rule.value["services"]
      # source_addresses - (required) is a type of list of string
      source_addresses = rule.value["source_addresses"]
      # source_users - (required) is a type of list of string
      source_users = rule.value["source_users"]
      # source_zones - (required) is a type of list of string
      source_zones = rule.value["source_zones"]
      # spyware - (optional) is a type of string
      spyware = rule.value["spyware"]
      # tags - (optional) is a type of set of string
      tags = rule.value["tags"]
      # type - (optional) is a type of string
      type = rule.value["type"]
      # url_filtering - (optional) is a type of string
      url_filtering = rule.value["url_filtering"]
      # virus - (optional) is a type of string
      virus = rule.value["virus"]
      # vulnerability - (optional) is a type of string
      vulnerability = rule.value["vulnerability"]
      # wildfire_analysis - (optional) is a type of string
      wildfire_analysis = rule.value["wildfire_analysis"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_security_policy_group.this.id
}

output "this" {
  value = panos_security_policy_group.this
}
```

[top](#index)