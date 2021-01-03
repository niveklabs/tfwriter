# google_compute_instance_template

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google-beta = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_instance_template" {
  source = "./modules/google-beta/r/google_compute_instance_template"

  # can_ip_forward - (optional) is a type of bool
  can_ip_forward = null
  # description - (optional) is a type of string
  description = null
  # enable_display - (optional) is a type of bool
  enable_display = null
  # instance_description - (optional) is a type of string
  instance_description = null
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
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
  # tags - (optional) is a type of set of string
  tags = []

  confidential_instance_config = [{
    enable_confidential_compute = null
  }]

  disk = [{
    auto_delete = null
    boot        = null
    device_name = null
    disk_encryption_key = [{
      kms_key_self_link = null
    }]
    disk_name    = null
    disk_size_gb = null
    disk_type    = null
    interface    = null
    labels       = {}
    mode         = null
    source       = null
    source_image = null
    type         = null
  }]

  guest_accelerator = [{
    count = null
    type  = null
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
    min_node_cpus     = null
    node_affinities = [{
      key      = null
      operator = null
      values   = []
    }]
    on_host_maintenance = null
    preemptible         = null
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
  }]
}
```

[top](#index)

### Variables

```terraform
variable "can_ip_forward" {
  description = "(optional) - Whether to allow sending and receiving of packets with non-matching source or destination IPs. This defaults to false."
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional) - A brief description of this resource."
  type        = string
  default     = null
}

variable "enable_display" {
  description = "(optional) - Enable Virtual Displays on this instance. Note: allow_stopping_for_update must be set to true in order to update this field."
  type        = bool
  default     = null
}

variable "instance_description" {
  description = "(optional) - A description of the instance."
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - A set of key/value label pairs to assign to instances created from this template,"
  type        = map(string)
  default     = null
}

variable "machine_type" {
  description = "(required) - The machine type to create. To create a machine with a custom type (such as extended memory), format the value like custom-VCPUS-MEM_IN_MB like custom-6-20480 for 6 vCPU and 20GB of RAM."
  type        = string
}

variable "metadata" {
  description = "(optional) - Metadata key/value pairs to make available from within instances created from this template."
  type        = map(string)
  default     = null
}

variable "metadata_startup_script" {
  description = "(optional) - An alternative to using the startup-script metadata key, mostly to match the compute_instance resource. This replaces the startup-script metadata key on the created instance and thus the two mechanisms are not allowed to be used simultaneously."
  type        = string
  default     = null
}

variable "min_cpu_platform" {
  description = "(optional) - Specifies a minimum CPU platform. Applicable values are the friendly names of CPU platforms, such as Intel Haswell or Intel Skylake."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - The name of the instance template. If you leave this blank, Terraform will auto-generate a unique name."
  type        = string
  default     = null
}

variable "name_prefix" {
  description = "(optional) - Creates a unique name beginning with the specified prefix. Conflicts with name."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional) - The ID of the project in which the resource belongs. If it is not provided, the provider project is used."
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - An instance template is a global resource that is not bound to a zone or a region. However, you can still specify some regional resources in an instance template, which restricts the template to the region where that resource resides. For example, a custom subnetwork resource is tied to a specific region. Defaults to the region of the Provider if no value is given."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Tags to attach to the instance."
  type        = set(string)
  default     = null
}

variable "confidential_instance_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enable_confidential_compute = bool
    }
  ))
  default = []
}

variable "disk" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      auto_delete = bool
      boot        = bool
      device_name = string
      disk_encryption_key = list(object(
        {
          kms_key_self_link = string
        }
      ))
      disk_name    = string
      disk_size_gb = number
      disk_type    = string
      interface    = string
      labels       = map(string)
      mode         = string
      source       = string
      source_image = string
      type         = string
    }
  ))
}

variable "guest_accelerator" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      count = number
      type  = string
    }
  ))
  default = []
}

variable "network_interface" {
  description = "nested block: NestingList, min items: 0, max items: 0"
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
  default = []
}

variable "scheduling" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      automatic_restart = bool
      min_node_cpus     = number
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
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_compute_instance_template" "this" {
  can_ip_forward          = var.can_ip_forward
  description             = var.description
  enable_display          = var.enable_display
  instance_description    = var.instance_description
  labels                  = var.labels
  machine_type            = var.machine_type
  metadata                = var.metadata
  metadata_startup_script = var.metadata_startup_script
  min_cpu_platform        = var.min_cpu_platform
  name                    = var.name
  name_prefix             = var.name_prefix
  project                 = var.project
  region                  = var.region
  tags                    = var.tags

  dynamic "confidential_instance_config" {
    for_each = var.confidential_instance_config
    content {
      enable_confidential_compute = confidential_instance_config.value["enable_confidential_compute"]
    }
  }

  dynamic "disk" {
    for_each = var.disk
    content {
      auto_delete  = disk.value["auto_delete"]
      boot         = disk.value["boot"]
      device_name  = disk.value["device_name"]
      disk_name    = disk.value["disk_name"]
      disk_size_gb = disk.value["disk_size_gb"]
      disk_type    = disk.value["disk_type"]
      interface    = disk.value["interface"]
      labels       = disk.value["labels"]
      mode         = disk.value["mode"]
      source       = disk.value["source"]
      source_image = disk.value["source_image"]
      type         = disk.value["type"]

      dynamic "disk_encryption_key" {
        for_each = disk.value.disk_encryption_key
        content {
          kms_key_self_link = disk_encryption_key.value["kms_key_self_link"]
        }
      }

    }
  }

  dynamic "guest_accelerator" {
    for_each = var.guest_accelerator
    content {
      count = guest_accelerator.value["count"]
      type  = guest_accelerator.value["type"]
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
          nat_ip       = access_config.value["nat_ip"]
          network_tier = access_config.value["network_tier"]
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
      min_node_cpus       = scheduling.value["min_node_cpus"]
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
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_compute_instance_template.this.id
}

output "metadata_fingerprint" {
  description = "returns a string"
  value       = google_compute_instance_template.this.metadata_fingerprint
}

output "name" {
  description = "returns a string"
  value       = google_compute_instance_template.this.name
}

output "name_prefix" {
  description = "returns a string"
  value       = google_compute_instance_template.this.name_prefix
}

output "project" {
  description = "returns a string"
  value       = google_compute_instance_template.this.project
}

output "region" {
  description = "returns a string"
  value       = google_compute_instance_template.this.region
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_instance_template.this.self_link
}

output "tags_fingerprint" {
  description = "returns a string"
  value       = google_compute_instance_template.this.tags_fingerprint
}

output "this" {
  value = google_compute_instance_template.this
}
```

[top](#index)