# google_project

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
module "google_project" {
  source = "./modules/google-beta/r/google_project"

  # auto_create_network - (optional) is a type of bool
  auto_create_network = null
  # billing_account - (optional) is a type of string
  billing_account = null
  # folder_id - (optional) is a type of string
  folder_id = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # org_id - (optional) is a type of string
  org_id = null
  # project_id - (required) is a type of string
  project_id = null
  # skip_delete - (optional) is a type of bool
  skip_delete = null

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auto_create_network" {
  description = "(optional) - Create the 'default' network automatically.  Default true. If set to false, the default network will be deleted.  Note that, for quota purposes, you will still need to have 1 network slot available to create the project successfully, even if you set auto_create_network to false, since the network will exist momentarily."
  type        = bool
  default     = null
}

variable "billing_account" {
  description = "(optional) - The alphanumeric ID of the billing account this project belongs to. The user or service account performing this operation with Terraform must have Billing Account Administrator privileges (roles/billing.admin) in the organization. See Google Cloud Billing API Access Control for more details."
  type        = string
  default     = null
}

variable "folder_id" {
  description = "(optional) - The numeric ID of the folder this project should be created under. Only one of org_id or folder_id may be specified. If the folder_id is specified, then the project is created under the specified folder. Changing this forces the project to be migrated to the newly specified folder."
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - A set of key/value label pairs to assign to the project."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - The display name of the project."
  type        = string
}

variable "org_id" {
  description = "(optional) - The numeric ID of the organization this project belongs to. Changing this forces a new project to be created.  Only one of org_id or folder_id may be specified. If the org_id is specified then the project is created at the top level. Changing this forces the project to be migrated to the newly specified organization."
  type        = string
  default     = null
}

variable "project_id" {
  description = "(required) - The project ID. Changing this forces a new project to be created."
  type        = string
}

variable "skip_delete" {
  description = "(optional) - If true, the Terraform resource can be deleted without deleting the Project via the Google API."
  type        = bool
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_project" "this" {
  # auto_create_network - (optional) is a type of bool
  auto_create_network = var.auto_create_network
  # billing_account - (optional) is a type of string
  billing_account = var.billing_account
  # folder_id - (optional) is a type of string
  folder_id = var.folder_id
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (required) is a type of string
  name = var.name
  # org_id - (optional) is a type of string
  org_id = var.org_id
  # project_id - (required) is a type of string
  project_id = var.project_id
  # skip_delete - (optional) is a type of bool
  skip_delete = var.skip_delete

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "folder_id" {
  description = "returns a string"
  value       = google_project.this.folder_id
}

output "id" {
  description = "returns a string"
  value       = google_project.this.id
}

output "number" {
  description = "returns a string"
  value       = google_project.this.number
}

output "org_id" {
  description = "returns a string"
  value       = google_project.this.org_id
}

output "skip_delete" {
  description = "returns a bool"
  value       = google_project.this.skip_delete
}

output "this" {
  value = google_project.this
}
```

[top](#index)