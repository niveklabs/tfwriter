# google_cloud_asset_project_feed

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
module "google_cloud_asset_project_feed" {
  source = "./modules/google-beta/r/google_cloud_asset_project_feed"

  # asset_names - (optional) is a type of list of string
  asset_names = []
  # asset_types - (optional) is a type of list of string
  asset_types = []
  # billing_project - (optional) is a type of string
  billing_project = null
  # content_type - (optional) is a type of string
  content_type = null
  # feed_id - (required) is a type of string
  feed_id = null
  # project - (optional) is a type of string
  project = null

  condition = [{
    description = null
    expression  = null
    location    = null
    title       = null
  }]

  feed_output_config = [{
    pubsub_destination = [{
      topic = null
    }]
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
variable "asset_names" {
  description = "(optional) - A list of the full names of the assets to receive updates. You must specify either or both of \nassetNames and assetTypes. Only asset updates matching specified assetNames and assetTypes are\nexported to the feed. For example: //compute.googleapis.com/projects/my_project_123/zones/zone1/instances/instance1.\nSee https://cloud.google.com/apis/design/resourceNames#fullResourceName for more info."
  type        = list(string)
  default     = null
}

variable "asset_types" {
  description = "(optional) - A list of types of the assets to receive updates. You must specify either or both of assetNames\nand assetTypes. Only asset updates matching specified assetNames and assetTypes are exported to\nthe feed. For example: \"compute.googleapis.com/Disk\"\nSee https://cloud.google.com/asset-inventory/docs/supported-asset-types for a list of all\nsupported asset types."
  type        = list(string)
  default     = null
}

variable "billing_project" {
  description = "(optional) - The project whose identity will be used when sending messages to the\ndestination pubsub topic. It also specifies the project for API \nenablement check, quota, and billing. If not specified, the resource's\nproject will be used."
  type        = string
  default     = null
}

variable "content_type" {
  description = "(optional) - Asset content type. If not specified, no content but the asset name and type will be returned. Possible values: [\"CONTENT_TYPE_UNSPECIFIED\", \"RESOURCE\", \"IAM_POLICY\", \"ORG_POLICY\", \"ACCESS_POLICY\"]"
  type        = string
  default     = null
}

variable "feed_id" {
  description = "(required) - This is the client-assigned asset feed identifier and it needs to be unique under a specific parent."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "condition" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      description = string
      expression  = string
      location    = string
      title       = string
    }
  ))
  default = []
}

variable "feed_output_config" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      pubsub_destination = list(object(
        {
          topic = string
        }
      ))
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
resource "google_cloud_asset_project_feed" "this" {
  # asset_names - (optional) is a type of list of string
  asset_names = var.asset_names
  # asset_types - (optional) is a type of list of string
  asset_types = var.asset_types
  # billing_project - (optional) is a type of string
  billing_project = var.billing_project
  # content_type - (optional) is a type of string
  content_type = var.content_type
  # feed_id - (required) is a type of string
  feed_id = var.feed_id
  # project - (optional) is a type of string
  project = var.project

  dynamic "condition" {
    for_each = var.condition
    content {
      # description - (optional) is a type of string
      description = condition.value["description"]
      # expression - (required) is a type of string
      expression = condition.value["expression"]
      # location - (optional) is a type of string
      location = condition.value["location"]
      # title - (optional) is a type of string
      title = condition.value["title"]
    }
  }

  dynamic "feed_output_config" {
    for_each = var.feed_output_config
    content {

      dynamic "pubsub_destination" {
        for_each = feed_output_config.value.pubsub_destination
        content {
          # topic - (required) is a type of string
          topic = pubsub_destination.value["topic"]
        }
      }

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
  value       = google_cloud_asset_project_feed.this.id
}

output "name" {
  description = "returns a string"
  value       = google_cloud_asset_project_feed.this.name
}

output "project" {
  description = "returns a string"
  value       = google_cloud_asset_project_feed.this.project
}

output "this" {
  value = google_cloud_asset_project_feed.this
}
```

[top](#index)