# oraclepaas_database_service_instance

[back](../oraclepaas.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oraclepaas = ">= 1.5.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oraclepaas_database_service_instance" {
  source = "./modules/oraclepaas/r/oraclepaas_database_service_instance"

  # availability_domain - (optional) is a type of string
  availability_domain = null
  # bring_your_own_license - (optional) is a type of bool
  bring_your_own_license = null
  # description - (optional) is a type of string
  description = null
  # desired_state - (optional) is a type of string
  desired_state = null
  # edition - (required) is a type of string
  edition = null
  # high_performance_storage - (optional) is a type of bool
  high_performance_storage = null
  # ip_network - (optional) is a type of string
  ip_network = null
  # ip_reservations - (optional) is a type of list of string
  ip_reservations = []
  # level - (optional) is a type of string
  level = null
  # name - (required) is a type of string
  name = null
  # notification_email - (optional) is a type of string
  notification_email = null
  # region - (optional) is a type of string
  region = null
  # shape - (required) is a type of string
  shape = null
  # ssh_public_key - (required) is a type of string
  ssh_public_key = null
  # subnet - (optional) is a type of string
  subnet = null
  # subscription_type - (required) is a type of string
  subscription_type = null
  # version - (required) is a type of string
  version = null

  backups = [{
    cloud_storage_container = null
    cloud_storage_password  = null
    cloud_storage_username  = null
    create_if_missing       = null
  }]

  database_configuration = [{
    admin_password             = null
    backup_destination         = null
    backup_storage_volume_size = null
    character_set              = null
    data_storage_volume_size   = null
    db_demo                    = null
    disaster_recovery          = null
    failover_database          = null
    golden_gate                = null
    is_rac                     = null
    national_character_set     = null
    pdb_name                   = null
    sid                        = null
    snapshot_name              = null
    source_service_name        = null
    timezone                   = null
    type                       = null
    usable_storage             = null
  }]

  default_access_rules = [{
    enable_db_console      = null
    enable_db_express      = null
    enable_db_listener     = null
    enable_em_console      = null
    enable_http            = null
    enable_http_ssl        = null
    enable_rac_db_listener = null
    enable_rac_ons         = null
    enable_scan_listener   = null
    enable_ssh             = null
  }]

  hybrid_disaster_recovery = [{
    cloud_storage_container = null
    cloud_storage_password  = null
    cloud_storage_username  = null
  }]

  instantiate_from_backup = [{
    cloud_storage_container = null
    cloud_storage_password  = null
    cloud_storage_username  = null
    database_id             = null
    decryption_key          = null
    on_premise              = null
    service_id              = null
    wallet_file_content     = null
  }]

  standby = [{
    availability_domain = null
    subnet              = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "availability_domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bring_your_own_license" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "desired_state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "edition" {
  description = "(required)"
  type        = string
}

variable "high_performance_storage" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ip_network" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_reservations" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "level" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "notification_email" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "shape" {
  description = "(required)"
  type        = string
}

variable "ssh_public_key" {
  description = "(required)"
  type        = string
}

variable "subnet" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subscription_type" {
  description = "(required)"
  type        = string
}

variable "version" {
  description = "(required)"
  type        = string
}

variable "backups" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cloud_storage_container = string
      cloud_storage_password  = string
      cloud_storage_username  = string
      create_if_missing       = bool
    }
  ))
  default = []
}

variable "database_configuration" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      admin_password             = string
      backup_destination         = string
      backup_storage_volume_size = number
      character_set              = string
      data_storage_volume_size   = number
      db_demo                    = string
      disaster_recovery          = bool
      failover_database          = bool
      golden_gate                = bool
      is_rac                     = bool
      national_character_set     = string
      pdb_name                   = string
      sid                        = string
      snapshot_name              = string
      source_service_name        = string
      timezone                   = string
      type                       = string
      usable_storage             = number
    }
  ))
}

variable "default_access_rules" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enable_db_console      = bool
      enable_db_express      = bool
      enable_db_listener     = bool
      enable_em_console      = bool
      enable_http            = bool
      enable_http_ssl        = bool
      enable_rac_db_listener = bool
      enable_rac_ons         = bool
      enable_scan_listener   = bool
      enable_ssh             = bool
    }
  ))
  default = []
}

variable "hybrid_disaster_recovery" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cloud_storage_container = string
      cloud_storage_password  = string
      cloud_storage_username  = string
    }
  ))
  default = []
}

variable "instantiate_from_backup" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cloud_storage_container = string
      cloud_storage_password  = string
      cloud_storage_username  = string
      database_id             = string
      decryption_key          = string
      on_premise              = bool
      service_id              = string
      wallet_file_content     = string
    }
  ))
  default = []
}

variable "standby" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      availability_domain = string
      subnet              = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oraclepaas_database_service_instance" "this" {
  availability_domain      = var.availability_domain
  bring_your_own_license   = var.bring_your_own_license
  description              = var.description
  desired_state            = var.desired_state
  edition                  = var.edition
  high_performance_storage = var.high_performance_storage
  ip_network               = var.ip_network
  ip_reservations          = var.ip_reservations
  level                    = var.level
  name                     = var.name
  notification_email       = var.notification_email
  region                   = var.region
  shape                    = var.shape
  ssh_public_key           = var.ssh_public_key
  subnet                   = var.subnet
  subscription_type        = var.subscription_type
  version                  = var.version

  dynamic "backups" {
    for_each = var.backups
    content {
      cloud_storage_container = backups.value["cloud_storage_container"]
      cloud_storage_password  = backups.value["cloud_storage_password"]
      cloud_storage_username  = backups.value["cloud_storage_username"]
      create_if_missing       = backups.value["create_if_missing"]
    }
  }

  dynamic "database_configuration" {
    for_each = var.database_configuration
    content {
      admin_password             = database_configuration.value["admin_password"]
      backup_destination         = database_configuration.value["backup_destination"]
      backup_storage_volume_size = database_configuration.value["backup_storage_volume_size"]
      character_set              = database_configuration.value["character_set"]
      data_storage_volume_size   = database_configuration.value["data_storage_volume_size"]
      db_demo                    = database_configuration.value["db_demo"]
      disaster_recovery          = database_configuration.value["disaster_recovery"]
      failover_database          = database_configuration.value["failover_database"]
      golden_gate                = database_configuration.value["golden_gate"]
      is_rac                     = database_configuration.value["is_rac"]
      national_character_set     = database_configuration.value["national_character_set"]
      pdb_name                   = database_configuration.value["pdb_name"]
      sid                        = database_configuration.value["sid"]
      snapshot_name              = database_configuration.value["snapshot_name"]
      source_service_name        = database_configuration.value["source_service_name"]
      timezone                   = database_configuration.value["timezone"]
      type                       = database_configuration.value["type"]
      usable_storage             = database_configuration.value["usable_storage"]
    }
  }

  dynamic "default_access_rules" {
    for_each = var.default_access_rules
    content {
      enable_db_console      = default_access_rules.value["enable_db_console"]
      enable_db_express      = default_access_rules.value["enable_db_express"]
      enable_db_listener     = default_access_rules.value["enable_db_listener"]
      enable_em_console      = default_access_rules.value["enable_em_console"]
      enable_http            = default_access_rules.value["enable_http"]
      enable_http_ssl        = default_access_rules.value["enable_http_ssl"]
      enable_rac_db_listener = default_access_rules.value["enable_rac_db_listener"]
      enable_rac_ons         = default_access_rules.value["enable_rac_ons"]
      enable_scan_listener   = default_access_rules.value["enable_scan_listener"]
      enable_ssh             = default_access_rules.value["enable_ssh"]
    }
  }

  dynamic "hybrid_disaster_recovery" {
    for_each = var.hybrid_disaster_recovery
    content {
      cloud_storage_container = hybrid_disaster_recovery.value["cloud_storage_container"]
      cloud_storage_password  = hybrid_disaster_recovery.value["cloud_storage_password"]
      cloud_storage_username  = hybrid_disaster_recovery.value["cloud_storage_username"]
    }
  }

  dynamic "instantiate_from_backup" {
    for_each = var.instantiate_from_backup
    content {
      cloud_storage_container = instantiate_from_backup.value["cloud_storage_container"]
      cloud_storage_password  = instantiate_from_backup.value["cloud_storage_password"]
      cloud_storage_username  = instantiate_from_backup.value["cloud_storage_username"]
      database_id             = instantiate_from_backup.value["database_id"]
      decryption_key          = instantiate_from_backup.value["decryption_key"]
      on_premise              = instantiate_from_backup.value["on_premise"]
      service_id              = instantiate_from_backup.value["service_id"]
      wallet_file_content     = instantiate_from_backup.value["wallet_file_content"]
    }
  }

  dynamic "standby" {
    for_each = var.standby
    content {
      availability_domain = standby.value["availability_domain"]
      subnet              = standby.value["subnet"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cloud_storage_container" {
  description = "returns a string"
  value       = oraclepaas_database_service_instance.this.cloud_storage_container
}

output "compute_site_name" {
  description = "returns a string"
  value       = oraclepaas_database_service_instance.this.compute_site_name
}

output "dbaas_monitor_url" {
  description = "returns a string"
  value       = oraclepaas_database_service_instance.this.dbaas_monitor_url
}

output "em_url" {
  description = "returns a string"
  value       = oraclepaas_database_service_instance.this.em_url
}

output "glassfish_url" {
  description = "returns a string"
  value       = oraclepaas_database_service_instance.this.glassfish_url
}

output "id" {
  description = "returns a string"
  value       = oraclepaas_database_service_instance.this.id
}

output "identity_domain" {
  description = "returns a string"
  value       = oraclepaas_database_service_instance.this.identity_domain
}

output "region" {
  description = "returns a string"
  value       = oraclepaas_database_service_instance.this.region
}

output "status" {
  description = "returns a string"
  value       = oraclepaas_database_service_instance.this.status
}

output "uri" {
  description = "returns a string"
  value       = oraclepaas_database_service_instance.this.uri
}

output "this" {
  value = oraclepaas_database_service_instance.this
}
```

[top](#index)