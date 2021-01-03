# fortios_fmg_system_admin_profiles

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_fmg_system_admin_profiles" {
  source = "./modules/fortios/r/fortios_fmg_system_admin_profiles"

  # adom_policy_packages - (optional) is a type of string
  adom_policy_packages = null
  # adom_switch - (optional) is a type of string
  adom_switch = null
  # assignment - (optional) is a type of string
  assignment = null
  # config_retrieve - (optional) is a type of string
  config_retrieve = null
  # config_revert - (optional) is a type of string
  config_revert = null
  # consistency_check - (optional) is a type of string
  consistency_check = null
  # deploy_management - (optional) is a type of string
  deploy_management = null
  # description - (optional) is a type of string
  description = null
  # device_ap - (optional) is a type of string
  device_ap = null
  # device_config - (optional) is a type of string
  device_config = null
  # device_forticlient - (optional) is a type of string
  device_forticlient = null
  # device_fortiswitch - (optional) is a type of string
  device_fortiswitch = null
  # device_manager - (optional) is a type of string
  device_manager = null
  # device_operation - (optional) is a type of string
  device_operation = null
  # device_profile - (optional) is a type of string
  device_profile = null
  # device_revision_deletion - (optional) is a type of string
  device_revision_deletion = null
  # device_wan_link_load_balance - (optional) is a type of string
  device_wan_link_load_balance = null
  # fortiguard_center - (optional) is a type of string
  fortiguard_center = null
  # fortiguard_center_advanced - (optional) is a type of string
  fortiguard_center_advanced = null
  # fortiguard_center_firmware_managerment - (optional) is a type of string
  fortiguard_center_firmware_managerment = null
  # fortiguard_center_licensing - (optional) is a type of string
  fortiguard_center_licensing = null
  # global_policy_packages - (optional) is a type of string
  global_policy_packages = null
  # import_policy_packages - (optional) is a type of string
  import_policy_packages = null
  # intf_mapping - (optional) is a type of string
  intf_mapping = null
  # log_viewer - (optional) is a type of string
  log_viewer = null
  # policy_objects - (optional) is a type of string
  policy_objects = null
  # profileid - (required) is a type of string
  profileid = null
  # set_install_targets - (optional) is a type of string
  set_install_targets = null
  # system_setting - (optional) is a type of string
  system_setting = null
  # terminal_access - (optional) is a type of string
  terminal_access = null
  # vpn_manager - (optional) is a type of string
  vpn_manager = null
}
```

[top](#index)

### Variables

```terraform
variable "adom_policy_packages" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "adom_switch" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "assignment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "config_retrieve" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "config_revert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "consistency_check" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "deploy_management" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device_ap" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device_config" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device_forticlient" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device_fortiswitch" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device_manager" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device_operation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device_revision_deletion" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device_wan_link_load_balance" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fortiguard_center" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fortiguard_center_advanced" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fortiguard_center_firmware_managerment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fortiguard_center_licensing" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "global_policy_packages" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "import_policy_packages" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "intf_mapping" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log_viewer" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policy_objects" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "profileid" {
  description = "(required)"
  type        = string
}

variable "set_install_targets" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "system_setting" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "terminal_access" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpn_manager" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_fmg_system_admin_profiles" "this" {
  adom_policy_packages                   = var.adom_policy_packages
  adom_switch                            = var.adom_switch
  assignment                             = var.assignment
  config_retrieve                        = var.config_retrieve
  config_revert                          = var.config_revert
  consistency_check                      = var.consistency_check
  deploy_management                      = var.deploy_management
  description                            = var.description
  device_ap                              = var.device_ap
  device_config                          = var.device_config
  device_forticlient                     = var.device_forticlient
  device_fortiswitch                     = var.device_fortiswitch
  device_manager                         = var.device_manager
  device_operation                       = var.device_operation
  device_profile                         = var.device_profile
  device_revision_deletion               = var.device_revision_deletion
  device_wan_link_load_balance           = var.device_wan_link_load_balance
  fortiguard_center                      = var.fortiguard_center
  fortiguard_center_advanced             = var.fortiguard_center_advanced
  fortiguard_center_firmware_managerment = var.fortiguard_center_firmware_managerment
  fortiguard_center_licensing            = var.fortiguard_center_licensing
  global_policy_packages                 = var.global_policy_packages
  import_policy_packages                 = var.import_policy_packages
  intf_mapping                           = var.intf_mapping
  log_viewer                             = var.log_viewer
  policy_objects                         = var.policy_objects
  profileid                              = var.profileid
  set_install_targets                    = var.set_install_targets
  system_setting                         = var.system_setting
  terminal_access                        = var.terminal_access
  vpn_manager                            = var.vpn_manager
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_fmg_system_admin_profiles.this.id
}

output "this" {
  value = fortios_fmg_system_admin_profiles.this
}
```

[top](#index)