# google_notebooks_instance

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
module "google_notebooks_instance" {
  source = "./modules/google/r/google_notebooks_instance"

  # boot_disk_size_gb - (optional) is a type of number
  boot_disk_size_gb = null
  # boot_disk_type - (optional) is a type of string
  boot_disk_type = null
  # create_time - (optional) is a type of string
  create_time = null
  # custom_gpu_driver_path - (optional) is a type of string
  custom_gpu_driver_path = null
  # data_disk_size_gb - (optional) is a type of number
  data_disk_size_gb = null
  # data_disk_type - (optional) is a type of string
  data_disk_type = null
  # disk_encryption - (optional) is a type of string
  disk_encryption = null
  # install_gpu_driver - (optional) is a type of bool
  install_gpu_driver = null
  # instance_owners - (optional) is a type of list of string
  instance_owners = []
  # kms_key - (optional) is a type of string
  kms_key = null
  # labels - (optional) is a type of map of string
  labels = {}
  # location - (required) is a type of string
  location = null
  # machine_type - (required) is a type of string
  machine_type = null
  # metadata - (optional) is a type of map of string
  metadata = {}
  # name - (required) is a type of string
  name = null
  # network - (optional) is a type of string
  network = null
  # no_proxy_access - (optional) is a type of bool
  no_proxy_access = null
  # no_public_ip - (optional) is a type of bool
  no_public_ip = null
  # no_remove_data_disk - (optional) is a type of bool
  no_remove_data_disk = null
  # post_startup_script - (optional) is a type of string
  post_startup_script = null
  # project - (optional) is a type of string
  project = null
  # service_account - (optional) is a type of string
  service_account = null
  # service_account_scopes - (optional) is a type of list of string
  service_account_scopes = []
  # subnet - (optional) is a type of string
  subnet = null
  # tags - (optional) is a type of list of string
  tags = []
  # update_time - (optional) is a type of string
  update_time = null

  accelerator_config = [{
    core_count = null
    type       = null
  }]

  container_image = [{
    repository = null
    tag        = null
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

  vm_image = [{
    image_family = null
    image_name   = null
    project      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "boot_disk_size_gb" {
  description = "(optional) - The size of the boot disk in GB attached to this instance,\nup to a maximum of 64000 GB (64 TB). The minimum recommended value is 100 GB.\nIf not specified, this defaults to 100."
  type        = number
  default     = null
}

variable "boot_disk_type" {
  description = "(optional) - Possible disk types for notebook instances. Possible values: [\"DISK_TYPE_UNSPECIFIED\", \"PD_STANDARD\", \"PD_SSD\", \"PD_BALANCED\"]"
  type        = string
  default     = null
}

variable "create_time" {
  description = "(optional) - Instance creation time"
  type        = string
  default     = null
}

variable "custom_gpu_driver_path" {
  description = "(optional) - Specify a custom Cloud Storage path where the GPU driver is stored.\nIf not specified, we'll automatically choose from official GPU drivers."
  type        = string
  default     = null
}

variable "data_disk_size_gb" {
  description = "(optional) - The size of the data disk in GB attached to this instance,\nup to a maximum of 64000 GB (64 TB).\nYou can choose the size of the data disk based on how big your notebooks and data are.\nIf not specified, this defaults to 100."
  type        = number
  default     = null
}

variable "data_disk_type" {
  description = "(optional) - Possible disk types for notebook instances. Possible values: [\"DISK_TYPE_UNSPECIFIED\", \"PD_STANDARD\", \"PD_SSD\", \"PD_BALANCED\"]"
  type        = string
  default     = null
}

variable "disk_encryption" {
  description = "(optional) - Disk encryption method used on the boot and data disks, defaults to GMEK. Possible values: [\"DISK_ENCRYPTION_UNSPECIFIED\", \"GMEK\", \"CMEK\"]"
  type        = string
  default     = null
}

variable "install_gpu_driver" {
  description = "(optional) - Whether the end user authorizes Google Cloud to install GPU driver\non this instance. If this field is empty or set to false, the GPU driver\nwon't be installed. Only applicable to instances with GPUs."
  type        = bool
  default     = null
}

variable "instance_owners" {
  description = "(optional) - The list of owners of this instance after creation.\nFormat: alias@example.com.\nCurrently supports one owner only.\nIf not specified, all of the service account users of\nyour VM instance's service account can use the instance."
  type        = list(string)
  default     = null
}

variable "kms_key" {
  description = "(optional) - The KMS key used to encrypt the disks, only applicable if diskEncryption is CMEK.\nFormat: projects/{project_id}/locations/{location}/keyRings/{key_ring_id}/cryptoKeys/{key_id}"
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - Labels to apply to this instance. These can be later modified by the setLabels method.\nAn object containing a list of \"key\": value pairs. Example: { \"name\": \"wrench\", \"mass\": \"1.3kg\", \"count\": \"3\" }."
  type        = map(string)
  default     = null
}

variable "location" {
  description = "(required) - A reference to the zone where the machine resides."
  type        = string
}

variable "machine_type" {
  description = "(required) - A reference to a machine type which defines VM kind."
  type        = string
}

variable "metadata" {
  description = "(optional) - Custom metadata to apply to this instance.\nAn object containing a list of \"key\": value pairs. Example: { \"name\": \"wrench\", \"mass\": \"1.3kg\", \"count\": \"3\" }."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - The name specified for the Notebook instance."
  type        = string
}

variable "network" {
  description = "(optional) - The name of the VPC that this instance is in.\nFormat: projects/{project_id}/global/networks/{network_id}"
  type        = string
  default     = null
}

variable "no_proxy_access" {
  description = "(optional) - The notebook instance will not register with the proxy.."
  type        = bool
  default     = null
}

variable "no_public_ip" {
  description = "(optional) - No public IP will be assigned to this instance."
  type        = bool
  default     = null
}

variable "no_remove_data_disk" {
  description = "(optional) - If true, the data disk will not be auto deleted when deleting the instance."
  type        = bool
  default     = null
}

variable "post_startup_script" {
  description = "(optional) - Path to a Bash script that automatically runs after a\nnotebook instance fully boots up. The path must be a URL\nor Cloud Storage path (gs://path-to-file/file-name)."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_account" {
  description = "(optional) - The service account on this instance, giving access to other\nGoogle Cloud services. You can use any service account within\nthe same project, but you must have the service account user\npermission to use the instance. If not specified,\nthe Compute Engine default service account is used."
  type        = string
  default     = null
}

variable "service_account_scopes" {
  description = "(optional) - Optional. The URIs of service account scopes to be included in Compute Engine instances.\nIf not specified, the following scopes are defined:\n- https://www.googleapis.com/auth/cloud-platform\n- https://www.googleapis.com/auth/userinfo.email"
  type        = list(string)
  default     = null
}

variable "subnet" {
  description = "(optional) - The name of the subnet that this instance is in.\nFormat: projects/{project_id}/regions/{region}/subnetworks/{subnetwork_id}"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - The Compute Engine tags to add to runtime."
  type        = list(string)
  default     = null
}

variable "update_time" {
  description = "(optional) - Instance update time."
  type        = string
  default     = null
}

variable "accelerator_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      core_count = number
      type       = string
    }
  ))
  default = []
}

variable "container_image" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      repository = string
      tag        = string
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

variable "vm_image" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      image_family = string
      image_name   = string
      project      = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_notebooks_instance" "this" {
  boot_disk_size_gb      = var.boot_disk_size_gb
  boot_disk_type         = var.boot_disk_type
  create_time            = var.create_time
  custom_gpu_driver_path = var.custom_gpu_driver_path
  data_disk_size_gb      = var.data_disk_size_gb
  data_disk_type         = var.data_disk_type
  disk_encryption        = var.disk_encryption
  install_gpu_driver     = var.install_gpu_driver
  instance_owners        = var.instance_owners
  kms_key                = var.kms_key
  labels                 = var.labels
  location               = var.location
  machine_type           = var.machine_type
  metadata               = var.metadata
  name                   = var.name
  network                = var.network
  no_proxy_access        = var.no_proxy_access
  no_public_ip           = var.no_public_ip
  no_remove_data_disk    = var.no_remove_data_disk
  post_startup_script    = var.post_startup_script
  project                = var.project
  service_account        = var.service_account
  service_account_scopes = var.service_account_scopes
  subnet                 = var.subnet
  tags                   = var.tags
  update_time            = var.update_time

  dynamic "accelerator_config" {
    for_each = var.accelerator_config
    content {
      core_count = accelerator_config.value["core_count"]
      type       = accelerator_config.value["type"]
    }
  }

  dynamic "container_image" {
    for_each = var.container_image
    content {
      repository = container_image.value["repository"]
      tag        = container_image.value["tag"]
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

  dynamic "vm_image" {
    for_each = var.vm_image
    content {
      image_family = vm_image.value["image_family"]
      image_name   = vm_image.value["image_name"]
      project      = vm_image.value["project"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = google_notebooks_instance.this.create_time
}

output "id" {
  description = "returns a string"
  value       = google_notebooks_instance.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = google_notebooks_instance.this.labels
}

output "network" {
  description = "returns a string"
  value       = google_notebooks_instance.this.network
}

output "project" {
  description = "returns a string"
  value       = google_notebooks_instance.this.project
}

output "proxy_uri" {
  description = "returns a string"
  value       = google_notebooks_instance.this.proxy_uri
}

output "service_account" {
  description = "returns a string"
  value       = google_notebooks_instance.this.service_account
}

output "state" {
  description = "returns a string"
  value       = google_notebooks_instance.this.state
}

output "subnet" {
  description = "returns a string"
  value       = google_notebooks_instance.this.subnet
}

output "update_time" {
  description = "returns a string"
  value       = google_notebooks_instance.this.update_time
}

output "this" {
  value = google_notebooks_instance.this
}
```

[top](#index)