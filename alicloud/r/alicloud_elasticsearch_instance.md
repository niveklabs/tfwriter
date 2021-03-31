# alicloud_elasticsearch_instance

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_elasticsearch_instance" {
  source = "./modules/alicloud/r/alicloud_elasticsearch_instance"

  # client_node_amount - (optional) is a type of number
  client_node_amount = null
  # client_node_spec - (optional) is a type of string
  client_node_spec = null
  # data_node_amount - (required) is a type of number
  data_node_amount = null
  # data_node_disk_encrypted - (optional) is a type of bool
  data_node_disk_encrypted = null
  # data_node_disk_size - (required) is a type of number
  data_node_disk_size = null
  # data_node_disk_type - (required) is a type of string
  data_node_disk_type = null
  # data_node_spec - (required) is a type of string
  data_node_spec = null
  # description - (optional) is a type of string
  description = null
  # enable_kibana_private_network - (optional) is a type of bool
  enable_kibana_private_network = null
  # enable_kibana_public_network - (optional) is a type of bool
  enable_kibana_public_network = null
  # enable_public - (optional) is a type of bool
  enable_public = null
  # instance_charge_type - (optional) is a type of string
  instance_charge_type = null
  # kibana_private_whitelist - (optional) is a type of set of string
  kibana_private_whitelist = []
  # kibana_whitelist - (optional) is a type of set of string
  kibana_whitelist = []
  # kms_encrypted_password - (optional) is a type of string
  kms_encrypted_password = null
  # kms_encryption_context - (optional) is a type of map of string
  kms_encryption_context = {}
  # master_node_spec - (optional) is a type of string
  master_node_spec = null
  # password - (optional) is a type of string
  password = null
  # period - (optional) is a type of number
  period = null
  # private_whitelist - (optional) is a type of set of string
  private_whitelist = []
  # protocol - (optional) is a type of string
  protocol = null
  # public_whitelist - (optional) is a type of set of string
  public_whitelist = []
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # version - (required) is a type of string
  version = null
  # vswitch_id - (required) is a type of string
  vswitch_id = null
  # zone_count - (optional) is a type of number
  zone_count = null

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
variable "client_node_amount" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "client_node_spec" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "data_node_amount" {
  description = "(required)"
  type        = number
}

variable "data_node_disk_encrypted" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "data_node_disk_size" {
  description = "(required)"
  type        = number
}

variable "data_node_disk_type" {
  description = "(required)"
  type        = string
}

variable "data_node_spec" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_kibana_private_network" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_kibana_public_network" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_public" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "instance_charge_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kibana_private_whitelist" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "kibana_whitelist" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "kms_encrypted_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kms_encryption_context" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "master_node_spec" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "private_whitelist" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "public_whitelist" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "version" {
  description = "(required)"
  type        = string
}

variable "vswitch_id" {
  description = "(required)"
  type        = string
}

variable "zone_count" {
  description = "(optional)"
  type        = number
  default     = null
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
resource "alicloud_elasticsearch_instance" "this" {
  client_node_amount            = var.client_node_amount
  client_node_spec              = var.client_node_spec
  data_node_amount              = var.data_node_amount
  data_node_disk_encrypted      = var.data_node_disk_encrypted
  data_node_disk_size           = var.data_node_disk_size
  data_node_disk_type           = var.data_node_disk_type
  data_node_spec                = var.data_node_spec
  description                   = var.description
  enable_kibana_private_network = var.enable_kibana_private_network
  enable_kibana_public_network  = var.enable_kibana_public_network
  enable_public                 = var.enable_public
  instance_charge_type          = var.instance_charge_type
  kibana_private_whitelist      = var.kibana_private_whitelist
  kibana_whitelist              = var.kibana_whitelist
  kms_encrypted_password        = var.kms_encrypted_password
  kms_encryption_context        = var.kms_encryption_context
  master_node_spec              = var.master_node_spec
  password                      = var.password
  period                        = var.period
  private_whitelist             = var.private_whitelist
  protocol                      = var.protocol
  public_whitelist              = var.public_whitelist
  resource_group_id             = var.resource_group_id
  tags                          = var.tags
  version                       = var.version
  vswitch_id                    = var.vswitch_id
  zone_count                    = var.zone_count

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
output "description" {
  description = "returns a string"
  value       = alicloud_elasticsearch_instance.this.description
}

output "domain" {
  description = "returns a string"
  value       = alicloud_elasticsearch_instance.this.domain
}

output "id" {
  description = "returns a string"
  value       = alicloud_elasticsearch_instance.this.id
}

output "kibana_domain" {
  description = "returns a string"
  value       = alicloud_elasticsearch_instance.this.kibana_domain
}

output "kibana_port" {
  description = "returns a number"
  value       = alicloud_elasticsearch_instance.this.kibana_port
}

output "kibana_private_whitelist" {
  description = "returns a set of string"
  value       = alicloud_elasticsearch_instance.this.kibana_private_whitelist
}

output "kibana_whitelist" {
  description = "returns a set of string"
  value       = alicloud_elasticsearch_instance.this.kibana_whitelist
}

output "port" {
  description = "returns a number"
  value       = alicloud_elasticsearch_instance.this.port
}

output "private_whitelist" {
  description = "returns a set of string"
  value       = alicloud_elasticsearch_instance.this.private_whitelist
}

output "public_whitelist" {
  description = "returns a set of string"
  value       = alicloud_elasticsearch_instance.this.public_whitelist
}

output "resource_group_id" {
  description = "returns a string"
  value       = alicloud_elasticsearch_instance.this.resource_group_id
}

output "status" {
  description = "returns a string"
  value       = alicloud_elasticsearch_instance.this.status
}

output "this" {
  value = alicloud_elasticsearch_instance.this
}
```

[top](#index)