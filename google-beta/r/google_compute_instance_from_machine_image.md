# google_compute_instance_from_machine_image

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
    google-beta = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_instance_from_machine_image" {
  source = "./modules/google-beta/r/google_compute_instance_from_machine_image"

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
  # machine_type - (optional) is a type of string
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
  # service_account - (optional) is a type of list of object
  service_account = [{
    email  = null
    scopes = []
  }]
  # source_machine_image - (required) is a type of string
  source_machine_image = null
  # tags - (optional) is a type of set of string
  tags = []
  # zone - (optional) is a type of string
  zone = null

  confidential_instance_config = [{
    enable_confidential_compute = null
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
    nic_type           = null
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
  description = "(optional) - The machine type to create."
  type        = string
  default     = null
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

variable "service_account" {
  description = "(optional) - The service account to attach to the instance."
  type = list(object(
    {
      email  = string
      scopes = set(string)
    }
  ))
  default = null
}

variable "source_machine_image" {
  description = "(required) - Name or self link of a machine image to create the instance from on."
  type        = string
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

variable "confidential_instance_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enable_confidential_compute = bool
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
      nic_type           = string
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
resource "google_compute_instance_from_machine_image" "this" {
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
  service_account           = var.service_account
  source_machine_image      = var.source_machine_image
  tags                      = var.tags
  zone                      = var.zone

  dynamic "confidential_instance_config" {
    for_each = var.confidential_instance_config
    content {
      enable_confidential_compute = confidential_instance_config.value["enable_confidential_compute"]
    }
  }

  dynamic "network_interface" {
    for_each = var.network_interface
    content {
      access_config      = network_interface.value["access_config"]
      alias_ip_range     = network_interface.value["alias_ip_range"]
      network            = network_interface.value["network"]
      network_ip         = network_interface.value["network_ip"]
      nic_type           = network_interface.value["nic_type"]
      subnetwork         = network_interface.value["subnetwork"]
      subnetwork_project = network_interface.value["subnetwork_project"]
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
output "allow_stopping_for_update" {
  description = "returns a bool"
  value       = google_compute_instance_from_machine_image.this.allow_stopping_for_update
}

output "attached_disk" {
  description = "returns a list of object"
  value       = google_compute_instance_from_machine_image.this.attached_disk
}

output "boot_disk" {
  description = "returns a list of object"
  value       = google_compute_instance_from_machine_image.this.boot_disk
}

output "can_ip_forward" {
  description = "returns a bool"
  value       = google_compute_instance_from_machine_image.this.can_ip_forward
}

output "cpu_platform" {
  description = "returns a string"
  value       = google_compute_instance_from_machine_image.this.cpu_platform
}

output "current_status" {
  description = "returns a string"
  value       = google_compute_instance_from_machine_image.this.current_status
}

output "deletion_protection" {
  description = "returns a bool"
  value       = google_compute_instance_from_machine_image.this.deletion_protection
}

output "description" {
  description = "returns a string"
  value       = google_compute_instance_from_machine_image.this.description
}

output "desired_status" {
  description = "returns a string"
  value       = google_compute_instance_from_machine_image.this.desired_status
}

output "enable_display" {
  description = "returns a bool"
  value       = google_compute_instance_from_machine_image.this.enable_display
}

output "guest_accelerator" {
  description = "returns a list of object"
  value       = google_compute_instance_from_machine_image.this.guest_accelerator
}

output "hostname" {
  description = "returns a string"
  value       = google_compute_instance_from_machine_image.this.hostname
}

output "id" {
  description = "returns a string"
  value       = google_compute_instance_from_machine_image.this.id
}

output "instance_id" {
  description = "returns a string"
  value       = google_compute_instance_from_machine_image.this.instance_id
}

output "label_fingerprint" {
  description = "returns a string"
  value       = google_compute_instance_from_machine_image.this.label_fingerprint
}

output "labels" {
  description = "returns a map of string"
  value       = google_compute_instance_from_machine_image.this.labels
}

output "machine_type" {
  description = "returns a string"
  value       = google_compute_instance_from_machine_image.this.machine_type
}

output "metadata" {
  description = "returns a map of string"
  value       = google_compute_instance_from_machine_image.this.metadata
}

output "metadata_fingerprint" {
  description = "returns a string"
  value       = google_compute_instance_from_machine_image.this.metadata_fingerprint
}

output "metadata_startup_script" {
  description = "returns a string"
  value       = google_compute_instance_from_machine_image.this.metadata_startup_script
}

output "min_cpu_platform" {
  description = "returns a string"
  value       = google_compute_instance_from_machine_image.this.min_cpu_platform
}

output "project" {
  description = "returns a string"
  value       = google_compute_instance_from_machine_image.this.project
}

output "resource_policies" {
  description = "returns a list of string"
  value       = google_compute_instance_from_machine_image.this.resource_policies
}

output "scratch_disk" {
  description = "returns a list of object"
  value       = google_compute_instance_from_machine_image.this.scratch_disk
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_instance_from_machine_image.this.self_link
}

output "service_account" {
  description = "returns a list of object"
  value       = google_compute_instance_from_machine_image.this.service_account
}

output "tags" {
  description = "returns a set of string"
  value       = google_compute_instance_from_machine_image.this.tags
}

output "tags_fingerprint" {
  description = "returns a string"
  value       = google_compute_instance_from_machine_image.this.tags_fingerprint
}

output "zone" {
  description = "returns a string"
  value       = google_compute_instance_from_machine_image.this.zone
}

output "this" {
  value = google_compute_instance_from_machine_image.this
}
```

[top](#index)