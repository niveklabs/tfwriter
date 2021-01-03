# ns1_user

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
    ns1 = ">= 1.9.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ns1_user" {
  source = "./modules/ns1/r/ns1_user"

  # account_manage_account_settings - (optional) is a type of bool
  account_manage_account_settings = null
  # account_manage_apikeys - (optional) is a type of bool
  account_manage_apikeys = null
  # account_manage_payment_methods - (optional) is a type of bool
  account_manage_payment_methods = null
  # account_manage_plan - (optional) is a type of bool
  account_manage_plan = null
  # account_manage_teams - (optional) is a type of bool
  account_manage_teams = null
  # account_manage_users - (optional) is a type of bool
  account_manage_users = null
  # account_view_activity_log - (optional) is a type of bool
  account_view_activity_log = null
  # account_view_invoices - (optional) is a type of bool
  account_view_invoices = null
  # data_manage_datafeeds - (optional) is a type of bool
  data_manage_datafeeds = null
  # data_manage_datasources - (optional) is a type of bool
  data_manage_datasources = null
  # data_push_to_datafeeds - (optional) is a type of bool
  data_push_to_datafeeds = null
  # dhcp_manage_dhcp - (optional) is a type of bool
  dhcp_manage_dhcp = null
  # dhcp_view_dhcp - (optional) is a type of bool
  dhcp_view_dhcp = null
  # dns_manage_zones - (optional) is a type of bool
  dns_manage_zones = null
  # dns_view_zones - (optional) is a type of bool
  dns_view_zones = null
  # dns_zones_allow - (optional) is a type of list of string
  dns_zones_allow = []
  # dns_zones_allow_by_default - (optional) is a type of bool
  dns_zones_allow_by_default = null
  # dns_zones_deny - (optional) is a type of list of string
  dns_zones_deny = []
  # email - (required) is a type of string
  email = null
  # ip_whitelist - (optional) is a type of list of string
  ip_whitelist = []
  # ip_whitelist_strict - (optional) is a type of bool
  ip_whitelist_strict = null
  # ipam_manage_ipam - (optional) is a type of bool
  ipam_manage_ipam = null
  # ipam_view_ipam - (optional) is a type of bool
  ipam_view_ipam = null
  # monitoring_manage_jobs - (optional) is a type of bool
  monitoring_manage_jobs = null
  # monitoring_manage_lists - (optional) is a type of bool
  monitoring_manage_lists = null
  # monitoring_view_jobs - (optional) is a type of bool
  monitoring_view_jobs = null
  # name - (required) is a type of string
  name = null
  # notify - (optional) is a type of map of bool
  notify = {}
  # security_manage_active_directory - (optional) is a type of bool
  security_manage_active_directory = null
  # security_manage_global_2fa - (optional) is a type of bool
  security_manage_global_2fa = null
  # teams - (optional) is a type of list of string
  teams = []
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "account_manage_account_settings" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "account_manage_apikeys" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "account_manage_payment_methods" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "account_manage_plan" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "account_manage_teams" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "account_manage_users" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "account_view_activity_log" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "account_view_invoices" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "data_manage_datafeeds" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "data_manage_datasources" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "data_push_to_datafeeds" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "dhcp_manage_dhcp" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "dhcp_view_dhcp" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "dns_manage_zones" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "dns_view_zones" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "dns_zones_allow" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "dns_zones_allow_by_default" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "dns_zones_deny" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "email" {
  description = "(required)"
  type        = string
}

variable "ip_whitelist" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "ip_whitelist_strict" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ipam_manage_ipam" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ipam_view_ipam" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "monitoring_manage_jobs" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "monitoring_manage_lists" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "monitoring_view_jobs" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "notify" {
  description = "(optional)"
  type        = map(bool)
  default     = null
}

variable "security_manage_active_directory" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "security_manage_global_2fa" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "teams" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "username" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "ns1_user" "this" {
  account_manage_account_settings  = var.account_manage_account_settings
  account_manage_apikeys           = var.account_manage_apikeys
  account_manage_payment_methods   = var.account_manage_payment_methods
  account_manage_plan              = var.account_manage_plan
  account_manage_teams             = var.account_manage_teams
  account_manage_users             = var.account_manage_users
  account_view_activity_log        = var.account_view_activity_log
  account_view_invoices            = var.account_view_invoices
  data_manage_datafeeds            = var.data_manage_datafeeds
  data_manage_datasources          = var.data_manage_datasources
  data_push_to_datafeeds           = var.data_push_to_datafeeds
  dhcp_manage_dhcp                 = var.dhcp_manage_dhcp
  dhcp_view_dhcp                   = var.dhcp_view_dhcp
  dns_manage_zones                 = var.dns_manage_zones
  dns_view_zones                   = var.dns_view_zones
  dns_zones_allow                  = var.dns_zones_allow
  dns_zones_allow_by_default       = var.dns_zones_allow_by_default
  dns_zones_deny                   = var.dns_zones_deny
  email                            = var.email
  ip_whitelist                     = var.ip_whitelist
  ip_whitelist_strict              = var.ip_whitelist_strict
  ipam_manage_ipam                 = var.ipam_manage_ipam
  ipam_view_ipam                   = var.ipam_view_ipam
  monitoring_manage_jobs           = var.monitoring_manage_jobs
  monitoring_manage_lists          = var.monitoring_manage_lists
  monitoring_view_jobs             = var.monitoring_view_jobs
  name                             = var.name
  notify                           = var.notify
  security_manage_active_directory = var.security_manage_active_directory
  security_manage_global_2fa       = var.security_manage_global_2fa
  teams                            = var.teams
  username                         = var.username
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ns1_user.this.id
}

output "this" {
  value = ns1_user.this
}
```

[top](#index)