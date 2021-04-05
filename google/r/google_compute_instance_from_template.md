# google_compute_instance_from_template

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
    google = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_instance_from_template" {
  source = "./modules/google/r/google_compute_instance_from_template"

  # allow_stopping_for_update - (optional) is a type of bool
  allow_stopping_for_update = null
  # attached_disk - (optional) is a type of list of object
  attached_disk = [{
    device_name                = null
    disk_encryption_key_raw    = null
    disk_encryption_key_sha256 = null
    kms_key_self_link          = null
    mode                       = null
    source                     = null
  }]
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
  # scratch_disk - (optional) is a type of list of object
  scratch_disk = [{
    interface = null
  }]
  # service_account - (optional) is a type of list of object
  service_account = [{
    email  = null
    scopes = []
  }]
  # source_instance_template - (required) is a type of string
  source_instance_template = null
  # tags - (optional) is a type of set of string
  tags = []
  # zone - (optional) is a type of string
  zone = null

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

variable "attached_disk" {
  description = "(optional) - List of disks attached to the instance"
  type = list(object(
    {
      device_name                = string
      disk_encryption_key_raw    = string
      disk_encryption_key_sha256 = string
      kms_key_self_link          = string
      mode                       = string
      source                     = string
    }
  ))
  default = null
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

variable "scratch_disk" {
  description = "(optional) - The scratch disks attached to the instance."
  type = list(object(
    {
      interface = string
    }
  ))
  default = null
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

variable "source_instance_template" {
  description = "(required) - Name or self link of an instance template to create the instance based on."
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

variable "boot_disk" {
  description = "nested block: NestingList, min items: 0, max items: 1"
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
  default = []
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
resource "google_compute_instance_from_template" "this" {
  allow_stopping_for_update = var.allow_stopping_for_update
  attached_disk             = var.attached_disk
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
  scratch_disk              = var.scratch_disk
  service_account           = var.service_account
  source_instance_template  = var.source_instance_template
  tags                      = var.tags
  zone                      = var.zone

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
  value       = google_compute_instance_from_template.this.allow_stopping_for_update
}

output "attached_disk" {
  description = "returns a list of object"
  value       = google_compute_instance_from_template.this.attached_disk
}

output "can_ip_forward" {
  description = "returns a bool"
  value       = google_compute_instance_from_template.this.can_ip_forward
}

output "cpu_platform" {
  description = "returns a string"
  value       = google_compute_instance_from_template.this.cpu_platform
}

output "current_status" {
  description = "returns a string"
  value       = google_compute_instance_from_template.this.current_status
}

output "deletion_protection" {
  description = "returns a bool"
  value       = google_compute_instance_from_template.this.deletion_protection
}

output "description" {
  description = "returns a string"
  value       = google_compute_instance_from_template.this.description
}

output "desired_status" {
  description = "returns a string"
  value       = google_compute_instance_from_template.this.desired_status
}

output "enable_display" {
  description = "returns a bool"
  value       = google_compute_instance_from_template.this.enable_display
}

output "guest_accelerator" {
  description = "returns a list of object"
  value       = google_compute_instance_from_template.this.guest_accelerator
}

output "hostname" {
  description = "returns a string"
  value       = google_compute_instance_from_template.this.hostname
}

output "id" {
  description = "returns a string"
  value       = google_compute_instance_from_template.this.id
}

output "instance_id" {
  description = "returns a string"
  value       = google_compute_instance_from_template.this.instance_id
}

output "label_fingerprint" {
  description = "returns a string"
  value       = google_compute_instance_from_template.this.label_fingerprint
}

output "labels" {
  description = "returns a map of string"
  value       = google_compute_instance_from_template.this.labels
}

output "machine_type" {
  description = "returns a string"
  value       = google_compute_instance_from_template.this.machine_type
}

output "metadata" {
  description = "returns a map of string"
  value       = google_compute_instance_from_template.this.metadata
}

output "metadata_fingerprint" {
  description = "returns a string"
  value       = google_compute_instance_from_template.this.metadata_fingerprint
}

output "metadata_startup_script" {
  description = "returns a string"
  value       = google_compute_instance_from_template.this.metadata_startup_script
}

output "min_cpu_platform" {
  description = "returns a string"
  value       = google_compute_instance_from_template.this.min_cpu_platform
}

output "project" {
  description = "returns a string"
  value       = google_compute_instance_from_template.this.project
}

output "resource_policies" {
  description = "returns a list of string"
  value       = google_compute_instance_from_template.this.resource_policies
}

output "scratch_disk" {
  description = "returns a list of object"
  value       = google_compute_instance_from_template.this.scratch_disk
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_instance_from_template.this.self_link
}

output "service_account" {
  description = "returns a list of object"
  value       = google_compute_instance_from_template.this.service_account
}

output "tags" {
  description = "returns a set of string"
  value       = google_compute_instance_from_template.this.tags
}

output "tags_fingerprint" {
  description = "returns a string"
  value       = google_compute_instance_from_template.this.tags_fingerprint
}

output "zone" {
  description = "returns a string"
  value       = google_compute_instance_from_template.this.zone
}

output "this" {
  value = google_compute_instance_from_template.this
}
```

[top](#index)