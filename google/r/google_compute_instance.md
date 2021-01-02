# google_compute_instance

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_instance" {
  source = "./modules/google/r/google_compute_instance"

  # allow_stopping_for_update - (optional) is a type of bool
  allow_stopping_for_update = null
  # can_ip_forward - (optional) is a type of bool
  can_ip_forward = null
  # deletion_protection - (optional) is a type of bool
  deletion_protection = null
  # description - (optional) is a type of string
  description = null
  # desired_status - (optional) is a type of string
  desired_status = null
  # enable_display - (optional) is a type of bool
  enable_display = null
  # guest_accelerator - (optional) is a type of list of object
  guest_accelerator = [{
    count = null
    type  = null
  }]
  # hostname - (optional) is a type of string
  hostname = null
  # labels - (optional) is a type of map of string
  labels = {}
  # machine_type - (required) is a type of string
  machine_type = null
  # metadata - (optional) is a type of map of string
  metadata = {}
  # metadata_startup_script - (optional) is a type of string
  metadata_startup_script = null
  # min_cpu_platform - (optional) is a type of string
  min_cpu_platform = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # resource_policies - (optional) is a type of list of string
  resource_policies = []
  # tags - (optional) is a type of set of string
  tags = []
  # zone - (optional) is a type of string
  zone = null

  attached_disk = [{
    device_name                = null
    disk_encryption_key_raw    = null
    disk_encryption_key_sha256 = null
    kms_key_self_link          = null
    mode                       = null
    source                     = null
  }]

  boot_disk = [{
    auto_delete                = null
    device_name                = null
    disk_encryption_key_raw    = null
    disk_encryption_key_sha256 = null
    initialize_params = [{
      image  = null
      labels = {}
      size   = null
      type   = null
    }]
    kms_key_self_link = null
    mode              = null
    source            = null
  }]

  network_interface = [{
    access_config = [{
      nat_ip                 = null
      network_tier           = null
      public_ptr_domain_name = null
    }]
    alias_ip_range = [{
      ip_cidr_range         = null
      subnetwork_range_name = null
    }]
    name               = null
    network            = null
    network_ip         = null
    subnetwork         = null
    subnetwork_project = null
  }]

  scheduling = [{
    automatic_restart = null
    node_affinities = [{
      key      = null
      operator = null
      values   = []
    }]
    on_host_maintenance = null
    preemptible         = null
  }]

  scratch_disk = [{
    interface = null
  }]

  service_account = [{
    email  = null
    scopes = []
  }]

  shielded_instance_config = [{
    enable_integrity_monitoring = null
    enable_secure_boot          = null
    enable_vtpm                 = null
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
variable "allow_stopping_for_update" {
  description = "(optional) - If true, allows Terraform to stop the instance to update its properties. If you try to update a property that requires stopping the instance without setting this field, the update will fail."
  type        = bool
  default     = null
}

variable "can_ip_forward" {
  description = "(optional) - Whether sending and receiving of packets with non-matching source or destination IPs is allowed."
  type        = bool
  default     = null
}

variable "deletion_protection" {
  description = "(optional) - Whether deletion protection is enabled on this instance."
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional) - A brief description of the resource."
  type        = string
  default     = null
}

variable "desired_status" {
  description = "(optional) - Desired status of the instance. Either \"RUNNING\" or \"TERMINATED\"."
  type        = string
  default     = null
}

variable "enable_display" {
  description = "(optional) - Whether the instance has virtual displays enabled."
  type        = bool
  default     = null
}

variable "guest_accelerator" {
  description = "(optional) - List of the type and count of accelerator cards attached to the instance."
  type = list(object(
    {
      count = number
      type  = string
    }
  ))
  default = null
}

variable "hostname" {
  description = "(optional) - A custom hostname for the instance. Must be a fully qualified DNS name and RFC-1035-valid. Valid format is a series of labels 1-63 characters long matching the regular expression [a-z]([-a-z0-9]*[a-z0-9]), concatenated with periods. The entire hostname must not exceed 253 characters. Changing this forces a new resource to be created."
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - A set of key/value label pairs assigned to the instance."
  type        = map(string)
  default     = null
}

variable "machine_type" {
  description = "(required) - The machine type to create."
  type        = string
}

variable "metadata" {
  description = "(optional) - Metadata key/value pairs made available within the instance."
  type        = map(string)
  default     = null
}

variable "metadata_startup_script" {
  description = "(optional) - Metadata startup scripts made available within the instance."
  type        = string
  default     = null
}

variable "min_cpu_platform" {
  description = "(optional) - The minimum CPU platform specified for the VM instance."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The name of the instance. One of name or self_link must be provided."
  type        = string
}

variable "project" {
  description = "(optional) - The ID of the project in which the resource belongs. If self_link is provided, this value is ignored. If neither self_link nor project are provided, the provider project is used."
  type        = string
  default     = null
}

variable "resource_policies" {
  description = "(optional) - A list of short names or self_links of resource policies to attach to the instance. Modifying this list will cause the instance to recreate. Currently a max of 1 resource policy is supported."
  type        = list(string)
  default     = null
}

variable "tags" {
  description = "(optional) - The list of tags attached to the instance."
  type        = set(string)
  default     = null
}

variable "zone" {
  description = "(optional) - The zone of the instance. If self_link is provided, this value is ignored. If neither self_link nor zone are provided, the provider zone is used."
  type        = string
  default     = null
}

variable "attached_disk" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      device_name                = string
      disk_encryption_key_raw    = string
      disk_encryption_key_sha256 = string
      kms_key_self_link          = string
      mode                       = string
      source                     = string
    }
  ))
  default = []
}

variable "boot_disk" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      auto_delete                = bool
      device_name                = string
      disk_encryption_key_raw    = string
      disk_encryption_key_sha256 = string
      initialize_params = list(object(
        {
          image  = string
          labels = map(string)
          size   = number
          type   = string
        }
      ))
      kms_key_self_link = string
      mode              = string
      source            = string
    }
  ))
}

variable "network_interface" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      access_config = list(object(
        {
          nat_ip                 = string
          network_tier           = string
          public_ptr_domain_name = string
        }
      ))
      alias_ip_range = list(object(
        {
          ip_cidr_range         = string
          subnetwork_range_name = string
        }
      ))
      name               = string
      network            = string
      network_ip         = string
      subnetwork         = string
      subnetwork_project = string
    }
  ))
}

variable "scheduling" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      automatic_restart = bool
      node_affinities = set(object(
        {
          key      = string
          operator = string
          values   = set(string)
        }
      ))
      on_host_maintenance = string
      preemptible         = bool
    }
  ))
  default = []
}

variable "scratch_disk" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      interface = string
    }
  ))
  default = []
}

variable "service_account" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      email  = string
      scopes = set(string)
    }
  ))
  default = []
}

variable "shielded_instance_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enable_integrity_monitoring = bool
      enable_secure_boot          = bool
      enable_vtpm                 = bool
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
resource "google_compute_instance" "this" {
  allow_stopping_for_update = var.allow_stopping_for_update
  can_ip_forward            = var.can_ip_forward
  deletion_protection       = var.deletion_protection
  description               = var.description
  desired_status            = var.desired_status
  enable_display            = var.enable_display
  guest_accelerator         = var.guest_accelerator
  hostname                  = var.hostname
  labels                    = var.labels
  machine_type              = var.machine_type
  metadata                  = var.metadata
  metadata_startup_script   = var.metadata_startup_script
  min_cpu_platform          = var.min_cpu_platform
  name                      = var.name
  project                   = var.project
  resource_policies         = var.resource_policies
  tags                      = var.tags
  zone                      = var.zone

  dynamic "attached_disk" {
    for_each = var.attached_disk
    content {
      device_name             = attached_disk.value["device_name"]
      disk_encryption_key_raw = attached_disk.value["disk_encryption_key_raw"]
      kms_key_self_link       = attached_disk.value["kms_key_self_link"]
      mode                    = attached_disk.value["mode"]
      source                  = attached_disk.value["source"]
    }
  }

  dynamic "boot_disk" {
    for_each = var.boot_disk
    content {
      auto_delete             = boot_disk.value["auto_delete"]
      device_name             = boot_disk.value["device_name"]
      disk_encryption_key_raw = boot_disk.value["disk_encryption_key_raw"]
      kms_key_self_link       = boot_disk.value["kms_key_self_link"]
      mode                    = boot_disk.value["mode"]
      source                  = boot_disk.value["source"]

      dynamic "initialize_params" {
        for_each = boot_disk.value.initialize_params
        content {
          image  = initialize_params.value["image"]
          labels = initialize_params.value["labels"]
          size   = initialize_params.value["size"]
          type   = initialize_params.value["type"]
        }
      }

    }
  }

  dynamic "network_interface" {
    for_each = var.network_interface
    content {
      network            = network_interface.value["network"]
      network_ip         = network_interface.value["network_ip"]
      subnetwork         = network_interface.value["subnetwork"]
      subnetwork_project = network_interface.value["subnetwork_project"]

      dynamic "access_config" {
        for_each = network_interface.value.access_config
        content {
          nat_ip                 = access_config.value["nat_ip"]
          network_tier           = access_config.value["network_tier"]
          public_ptr_domain_name = access_config.value["public_ptr_domain_name"]
        }
      }

      dynamic "alias_ip_range" {
        for_each = network_interface.value.alias_ip_range
        content {
          ip_cidr_range         = alias_ip_range.value["ip_cidr_range"]
          subnetwork_range_name = alias_ip_range.value["subnetwork_range_name"]
        }
      }

    }
  }

  dynamic "scheduling" {
    for_each = var.scheduling
    content {
      automatic_restart   = scheduling.value["automatic_restart"]
      on_host_maintenance = scheduling.value["on_host_maintenance"]
      preemptible         = scheduling.value["preemptible"]

      dynamic "node_affinities" {
        for_each = scheduling.value.node_affinities
        content {
          key      = node_affinities.value["key"]
          operator = node_affinities.value["operator"]
          values   = node_affinities.value["values"]
        }
      }

    }
  }

  dynamic "scratch_disk" {
    for_each = var.scratch_disk
    content {
      interface = scratch_disk.value["interface"]
    }
  }

  dynamic "service_account" {
    for_each = var.service_account
    content {
      email  = service_account.value["email"]
      scopes = service_account.value["scopes"]
    }
  }

  dynamic "shielded_instance_config" {
    for_each = var.shielded_instance_config
    content {
      enable_integrity_monitoring = shielded_instance_config.value["enable_integrity_monitoring"]
      enable_secure_boot          = shielded_instance_config.value["enable_secure_boot"]
      enable_vtpm                 = shielded_instance_config.value["enable_vtpm"]
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
output "cpu_platform" {
  description = "returns a string"
  value       = google_compute_instance.this.cpu_platform
}

output "current_status" {
  description = "returns a string"
  value       = google_compute_instance.this.current_status
}

output "guest_accelerator" {
  description = "returns a list of object"
  value       = google_compute_instance.this.guest_accelerator
}

output "id" {
  description = "returns a string"
  value       = google_compute_instance.this.id
}

output "instance_id" {
  description = "returns a string"
  value       = google_compute_instance.this.instance_id
}

output "label_fingerprint" {
  description = "returns a string"
  value       = google_compute_instance.this.label_fingerprint
}

output "metadata_fingerprint" {
  description = "returns a string"
  value       = google_compute_instance.this.metadata_fingerprint
}

output "min_cpu_platform" {
  description = "returns a string"
  value       = google_compute_instance.this.min_cpu_platform
}

output "project" {
  description = "returns a string"
  value       = google_compute_instance.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_instance.this.self_link
}

output "tags_fingerprint" {
  description = "returns a string"
  value       = google_compute_instance.this.tags_fingerprint
}

output "zone" {
  description = "returns a string"
  value       = google_compute_instance.this.zone
}

output "this" {
  value = google_compute_instance.this
}
```

[top](#index)