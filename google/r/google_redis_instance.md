# google_redis_instance

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "google_redis_instance" {
  source = "./modules/google/r/google_redis_instance"

  # alternative_location_id - (optional) is a type of string
  alternative_location_id = null
  # authorized_network - (optional) is a type of string
  authorized_network = null
  # connect_mode - (optional) is a type of string
  connect_mode = null
  # display_name - (optional) is a type of string
  display_name = null
  # labels - (optional) is a type of map of string
  labels = {}
  # location_id - (optional) is a type of string
  location_id = null
  # memory_size_gb - (required) is a type of number
  memory_size_gb = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # redis_configs - (optional) is a type of map of string
  redis_configs = {}
  # redis_version - (optional) is a type of string
  redis_version = null
  # region - (optional) is a type of string
  region = null
  # reserved_ip_range - (optional) is a type of string
  reserved_ip_range = null
  # tier - (optional) is a type of string
  tier = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "alternative_location_id" {
  description = "(optional) - Only applicable to STANDARD_HA tier which protects the instance\nagainst zonal failures by provisioning it across two zones.\nIf provided, it must be a different zone from the one provided in\n[locationId]."
  type        = string
  default     = null
}

variable "authorized_network" {
  description = "(optional) - The full name of the Google Compute Engine network to which the\ninstance is connected. If left unspecified, the default network\nwill be used."
  type        = string
  default     = null
}

variable "connect_mode" {
  description = "(optional) - The connection mode of the Redis instance. Default value: \"DIRECT_PEERING\" Possible values: [\"DIRECT_PEERING\", \"PRIVATE_SERVICE_ACCESS\"]"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - An arbitrary and optional user-provided name for the instance."
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - Resource labels to represent user provided metadata."
  type        = map(string)
  default     = null
}

variable "location_id" {
  description = "(optional) - The zone where the instance will be provisioned. If not provided,\nthe service will choose a zone for the instance. For STANDARD_HA tier,\ninstances will be created across two zones for protection against\nzonal failures. If [alternativeLocationId] is also provided, it must\nbe different from [locationId]."
  type        = string
  default     = null
}

variable "memory_size_gb" {
  description = "(required) - Redis memory size in GiB."
  type        = number
}

variable "name" {
  description = "(required) - The ID of the instance or a fully qualified identifier for the instance."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "redis_configs" {
  description = "(optional) - Redis configuration parameters, according to http://redis.io/topics/config.\nPlease check Memorystore documentation for the list of supported parameters:\nhttps://cloud.google.com/memorystore/docs/redis/reference/rest/v1/projects.locations.instances#Instance.FIELDS.redis_configs"
  type        = map(string)
  default     = null
}

variable "redis_version" {
  description = "(optional) - The version of Redis software. If not provided, latest supported\nversion will be used. Currently, the supported values are:\n\n- REDIS_5_0 for Redis 5.0 compatibility\n- REDIS_4_0 for Redis 4.0 compatibility\n- REDIS_3_2 for Redis 3.2 compatibility"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The name of the Redis region of the instance."
  type        = string
  default     = null
}

variable "reserved_ip_range" {
  description = "(optional) - The CIDR range of internal addresses that are reserved for this\ninstance. If not provided, the service will choose an unused /29\nblock, for example, 10.0.0.0/29 or 192.168.0.0/29. Ranges must be\nunique and non-overlapping with existing subnets in an authorized\nnetwork."
  type        = string
  default     = null
}

variable "tier" {
  description = "(optional) - The service tier of the instance. Must be one of these values:\n\n- BASIC: standalone instance\n- STANDARD_HA: highly available primary/replica instances Default value: \"BASIC\" Possible values: [\"BASIC\", \"STANDARD_HA\"]"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
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

```hcl
resource "google_redis_instance" "this" {
  alternative_location_id = var.alternative_location_id
  authorized_network      = var.authorized_network
  connect_mode            = var.connect_mode
  display_name            = var.display_name
  labels                  = var.labels
  location_id             = var.location_id
  memory_size_gb          = var.memory_size_gb
  name                    = var.name
  project                 = var.project
  redis_configs           = var.redis_configs
  redis_version           = var.redis_version
  region                  = var.region
  reserved_ip_range       = var.reserved_ip_range
  tier                    = var.tier

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

```hcl
output "alternative_location_id" {
  description = "returns a string"
  value       = google_redis_instance.this.alternative_location_id
}

output "authorized_network" {
  description = "returns a string"
  value       = google_redis_instance.this.authorized_network
}

output "create_time" {
  description = "returns a string"
  value       = google_redis_instance.this.create_time
}

output "current_location_id" {
  description = "returns a string"
  value       = google_redis_instance.this.current_location_id
}

output "host" {
  description = "returns a string"
  value       = google_redis_instance.this.host
}

output "id" {
  description = "returns a string"
  value       = google_redis_instance.this.id
}

output "location_id" {
  description = "returns a string"
  value       = google_redis_instance.this.location_id
}

output "persistence_iam_identity" {
  description = "returns a string"
  value       = google_redis_instance.this.persistence_iam_identity
}

output "port" {
  description = "returns a number"
  value       = google_redis_instance.this.port
}

output "project" {
  description = "returns a string"
  value       = google_redis_instance.this.project
}

output "redis_version" {
  description = "returns a string"
  value       = google_redis_instance.this.redis_version
}

output "region" {
  description = "returns a string"
  value       = google_redis_instance.this.region
}

output "reserved_ip_range" {
  description = "returns a string"
  value       = google_redis_instance.this.reserved_ip_range
}

output "this" {
  value = google_redis_instance.this
}
```

[top](#index)