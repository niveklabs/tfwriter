# google_tpu_node

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
module "google_tpu_node" {
  source = "./modules/google/r/google_tpu_node"

  # accelerator_type - (required) is a type of string
  accelerator_type = null
  # cidr_block - (optional) is a type of string
  cidr_block = null
  # description - (optional) is a type of string
  description = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # network - (optional) is a type of string
  network = null
  # project - (optional) is a type of string
  project = null
  # tensorflow_version - (required) is a type of string
  tensorflow_version = null
  # use_service_networking - (optional) is a type of bool
  use_service_networking = null
  # zone - (required) is a type of string
  zone = null

  scheduling_config = [{
    preemptible = null
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
variable "accelerator_type" {
  description = "(required) - The type of hardware accelerators associated with this node."
  type        = string
}

variable "cidr_block" {
  description = "(optional) - The CIDR block that the TPU node will use when selecting an IP\naddress. This CIDR block must be a /29 block; the Compute Engine\nnetworks API forbids a smaller block, and using a larger block would\nbe wasteful (a node can only consume one IP address).\n\nErrors will occur if the CIDR block has already been used for a\ncurrently existing TPU node, the CIDR block conflicts with any\nsubnetworks in the user's provided network, or the provided network\nis peered with another network that is using that CIDR block."
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - The user-supplied description of the TPU. Maximum of 512 characters."
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - Resource labels to represent user provided metadata."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - The immutable name of the TPU."
  type        = string
}

variable "network" {
  description = "(optional) - The name of a network to peer the TPU node to. It must be a\npreexisting Compute Engine network inside of the project on which\nthis API has been activated. If none is provided, \"default\" will be\nused."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tensorflow_version" {
  description = "(required) - The version of Tensorflow running in the Node."
  type        = string
}

variable "use_service_networking" {
  description = "(optional) - Whether the VPC peering for the node is set up through Service Networking API.\nThe VPC Peering should be set up before provisioning the node. If this field is set,\ncidr_block field should not be specified. If the network that you want to peer the\nTPU Node to is a Shared VPC network, the node must be created with this this field enabled."
  type        = bool
  default     = null
}

variable "zone" {
  description = "(required) - The GCP location for the TPU."
  type        = string
}

variable "scheduling_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      preemptible = bool
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
resource "google_tpu_node" "this" {
  accelerator_type       = var.accelerator_type
  cidr_block             = var.cidr_block
  description            = var.description
  labels                 = var.labels
  name                   = var.name
  network                = var.network
  project                = var.project
  tensorflow_version     = var.tensorflow_version
  use_service_networking = var.use_service_networking
  zone                   = var.zone

  dynamic "scheduling_config" {
    for_each = var.scheduling_config
    content {
      preemptible = scheduling_config.value["preemptible"]
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
output "cidr_block" {
  description = "returns a string"
  value       = google_tpu_node.this.cidr_block
}

output "id" {
  description = "returns a string"
  value       = google_tpu_node.this.id
}

output "network" {
  description = "returns a string"
  value       = google_tpu_node.this.network
}

output "network_endpoints" {
  description = "returns a list of object"
  value       = google_tpu_node.this.network_endpoints
}

output "project" {
  description = "returns a string"
  value       = google_tpu_node.this.project
}

output "service_account" {
  description = "returns a string"
  value       = google_tpu_node.this.service_account
}

output "this" {
  value = google_tpu_node.this
}
```

[top](#index)