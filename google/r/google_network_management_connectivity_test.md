# google_network_management_connectivity_test

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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

```hcl
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
  description = "nested mode: NestingList, min items: 1, max items: 1"
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
  description = "nested mode: NestingList, min items: 1, max items: 1"
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
resource "google_network_management_connectivity_test" "this" {
  description      = var.description
  labels           = var.labels
  name             = var.name
  project          = var.project
  protocol         = var.protocol
  related_projects = var.related_projects

  dynamic "destination" {
    for_each = var.destination
    content {
      instance   = destination.value["instance"]
      ip_address = destination.value["ip_address"]
      network    = destination.value["network"]
      port       = destination.value["port"]
      project_id = destination.value["project_id"]
    }
  }

  dynamic "source" {
    for_each = var.source
    content {
      instance     = source.value["instance"]
      ip_address   = source.value["ip_address"]
      network      = source.value["network"]
      network_type = source.value["network_type"]
      port         = source.value["port"]
      project_id   = source.value["project_id"]
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

```hcl
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