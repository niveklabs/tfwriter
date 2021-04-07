# google_network_management_connectivity_test

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
    google-beta = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_network_management_connectivity_test" {
  source = [{
    instance     = null
    ip_address   = null
    network      = null
    network_type = null
    port         = null
    project_id   = null
  }]

  # description - (optional) is a type of string
  description = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # protocol - (optional) is a type of string
  protocol = null
  # related_projects - (optional) is a type of list of string
  related_projects = []

  destination = [{
    instance   = null
    ip_address = null
    network    = null
    port       = null
    project_id = null
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
variable "description" {
  description = "(optional) - The user-supplied description of the Connectivity Test.\nMaximum of 512 characters."
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - Resource labels to represent user-provided metadata."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - Unique name for the connectivity test."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "protocol" {
  description = "(optional) - IP Protocol of the test. When not provided, \"TCP\" is assumed."
  type        = string
  default     = null
}

variable "related_projects" {
  description = "(optional) - Other projects that may be relevant for reachability analysis.\nThis is applicable to scenarios where a test can cross project\nboundaries."
  type        = list(string)
  default     = null
}

variable "destination" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      instance   = string
      ip_address = string
      network    = string
      port       = number
      project_id = string
    }
  ))
}

variable "source" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      instance     = string
      ip_address   = string
      network      = string
      network_type = string
      port         = number
      project_id   = string
    }
  ))
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
resource "google_network_management_connectivity_test" "this" {
  # description - (optional) is a type of string
  description = var.description
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (required) is a type of string
  name = var.name
  # project - (optional) is a type of string
  project = var.project
  # protocol - (optional) is a type of string
  protocol = var.protocol
  # related_projects - (optional) is a type of list of string
  related_projects = var.related_projects

  dynamic "destination" {
    for_each = var.destination
    content {
      # instance - (optional) is a type of string
      instance = destination.value["instance"]
      # ip_address - (optional) is a type of string
      ip_address = destination.value["ip_address"]
      # network - (optional) is a type of string
      network = destination.value["network"]
      # port - (optional) is a type of number
      port = destination.value["port"]
      # project_id - (optional) is a type of string
      project_id = destination.value["project_id"]
    }
  }

  dynamic "source" {
    for_each = var.source
    content {
      # instance - (optional) is a type of string
      instance = source.value["instance"]
      # ip_address - (optional) is a type of string
      ip_address = source.value["ip_address"]
      # network - (optional) is a type of string
      network = source.value["network"]
      # network_type - (optional) is a type of string
      network_type = source.value["network_type"]
      # port - (optional) is a type of number
      port = source.value["port"]
      # project_id - (optional) is a type of string
      project_id = source.value["project_id"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_network_management_connectivity_test.this.id
}

output "project" {
  description = "returns a string"
  value       = google_network_management_connectivity_test.this.project
}

output "this" {
  value = google_network_management_connectivity_test.this
}
```

[top](#index)