# google_composer_environment

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
module "google_composer_environment" {
  source = "./modules/google-beta/r/google_composer_environment"

  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null

  config = [{
    airflow_uri    = null
    dag_gcs_prefix = null
    database_config = [{
      machine_type = null
    }]
    gke_cluster = null
    node_config = [{
      disk_size_gb = null
      ip_allocation_policy = [{
        cluster_ipv4_cidr_block       = null
        cluster_secondary_range_name  = null
        services_ipv4_cidr_block      = null
        services_secondary_range_name = null
        use_ip_aliases                = null
      }]
      machine_type    = null
      network         = null
      oauth_scopes    = []
      service_account = null
      subnetwork      = null
      tags            = []
      zone            = null
    }]
    node_count = null
    private_environment_config = [{
      cloud_sql_ipv4_cidr_block  = null
      enable_private_endpoint    = null
      master_ipv4_cidr_block     = null
      web_server_ipv4_cidr_block = null
    }]
    software_config = [{
      airflow_config_overrides = {}
      env_variables            = {}
      image_version            = null
      pypi_packages            = {}
      python_version           = null
    }]
    web_server_config = [{
      machine_type = null
    }]
    web_server_network_access_control = [{
      allowed_ip_range = [{
        description = null
        value       = null
      }]
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
variable "labels" {
  description = "(optional) - User-defined labels for this environment. The labels map can contain no more than 64 entries. Entries of the labels map are UTF8 strings that comply with the following restrictions: Label keys must be between 1 and 63 characters long and must conform to the following regular expression: [a-z]([-a-z0-9]*[a-z0-9])?. Label values must be between 0 and 63 characters long and must conform to the regular expression ([a-z]([-a-z0-9]*[a-z0-9])?)?. No more than 64 labels can be associated with a given environment. Both keys and values must be <= 128 bytes in size."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - Name of the environment."
  type        = string
}

variable "project" {
  description = "(optional) - The ID of the project in which the resource belongs. If it is not provided, the provider project is used."
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The location or Compute Engine region for the environment."
  type        = string
  default     = null
}

variable "config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      airflow_uri    = string
      dag_gcs_prefix = string
      database_config = list(object(
        {
          machine_type = string
        }
      ))
      gke_cluster = string
      node_config = list(object(
        {
          disk_size_gb = number
          ip_allocation_policy = list(object(
            {
              cluster_ipv4_cidr_block       = string
              cluster_secondary_range_name  = string
              services_ipv4_cidr_block      = string
              services_secondary_range_name = string
              use_ip_aliases                = bool
            }
          ))
          machine_type    = string
          network         = string
          oauth_scopes    = set(string)
          service_account = string
          subnetwork      = string
          tags            = set(string)
          zone            = string
        }
      ))
      node_count = number
      private_environment_config = list(object(
        {
          cloud_sql_ipv4_cidr_block  = string
          enable_private_endpoint    = bool
          master_ipv4_cidr_block     = string
          web_server_ipv4_cidr_block = string
        }
      ))
      software_config = list(object(
        {
          airflow_config_overrides = map(string)
          env_variables            = map(string)
          image_version            = string
          pypi_packages            = map(string)
          python_version           = string
        }
      ))
      web_server_config = list(object(
        {
          machine_type = string
        }
      ))
      web_server_network_access_control = list(object(
        {
          allowed_ip_range = set(object(
            {
              description = string
              value       = string
            }
          ))
        }
      ))
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
resource "google_composer_environment" "this" {
  labels  = var.labels
  name    = var.name
  project = var.project
  region  = var.region

  dynamic "config" {
    for_each = var.config
    content {
      node_count = config.value["node_count"]

      dynamic "database_config" {
        for_each = config.value.database_config
        content {
          machine_type = database_config.value["machine_type"]
        }
      }

      dynamic "node_config" {
        for_each = config.value.node_config
        content {
          disk_size_gb         = node_config.value["disk_size_gb"]
          ip_allocation_policy = node_config.value["ip_allocation_policy"]
          machine_type         = node_config.value["machine_type"]
          network              = node_config.value["network"]
          oauth_scopes         = node_config.value["oauth_scopes"]
          service_account      = node_config.value["service_account"]
          subnetwork           = node_config.value["subnetwork"]
          tags                 = node_config.value["tags"]
          zone                 = node_config.value["zone"]
        }
      }

      dynamic "private_environment_config" {
        for_each = config.value.private_environment_config
        content {
          cloud_sql_ipv4_cidr_block  = private_environment_config.value["cloud_sql_ipv4_cidr_block"]
          enable_private_endpoint    = private_environment_config.value["enable_private_endpoint"]
          master_ipv4_cidr_block     = private_environment_config.value["master_ipv4_cidr_block"]
          web_server_ipv4_cidr_block = private_environment_config.value["web_server_ipv4_cidr_block"]
        }
      }

      dynamic "software_config" {
        for_each = config.value.software_config
        content {
          airflow_config_overrides = software_config.value["airflow_config_overrides"]
          env_variables            = software_config.value["env_variables"]
          image_version            = software_config.value["image_version"]
          pypi_packages            = software_config.value["pypi_packages"]
          python_version           = software_config.value["python_version"]
        }
      }

      dynamic "web_server_config" {
        for_each = config.value.web_server_config
        content {
          machine_type = web_server_config.value["machine_type"]
        }
      }

      dynamic "web_server_network_access_control" {
        for_each = config.value.web_server_network_access_control
        content {

          dynamic "allowed_ip_range" {
            for_each = web_server_network_access_control.value.allowed_ip_range
            content {
              description = allowed_ip_range.value["description"]
              value       = allowed_ip_range.value["value"]
            }
          }

        }
      }

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
output "id" {
  description = "returns a string"
  value       = google_composer_environment.this.id
}

output "project" {
  description = "returns a string"
  value       = google_composer_environment.this.project
}

output "this" {
  value = google_composer_environment.this
}
```

[top](#index)