# google_dataproc_cluster

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
module "google_dataproc_cluster" {
  source = "./modules/google/r/google_dataproc_cluster"

  # graceful_decommission_timeout - (optional) is a type of string
  graceful_decommission_timeout = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null

  cluster_config = [{
    autoscaling_config = [{
      policy_uri = null
    }]
    bucket = null
    encryption_config = [{
      kms_key_name = null
    }]
    gce_cluster_config = [{
      internal_ip_only       = null
      metadata               = {}
      network                = null
      service_account        = null
      service_account_scopes = []
      subnetwork             = null
      tags                   = []
      zone                   = null
    }]
    initialization_action = [{
      script      = null
      timeout_sec = null
    }]
    master_config = [{
      accelerators = [{
        accelerator_count = null
        accelerator_type  = null
      }]
      disk_config = [{
        boot_disk_size_gb = null
        boot_disk_type    = null
        num_local_ssds    = null
      }]
      image_uri        = null
      instance_names   = []
      machine_type     = null
      min_cpu_platform = null
      num_instances    = null
    }]
    preemptible_worker_config = [{
      disk_config = [{
        boot_disk_size_gb = null
        boot_disk_type    = null
        num_local_ssds    = null
      }]
      instance_names = []
      num_instances  = null
    }]
    security_config = [{
      kerberos_config = [{
        cross_realm_trust_admin_server        = null
        cross_realm_trust_kdc                 = null
        cross_realm_trust_realm               = null
        cross_realm_trust_shared_password_uri = null
        enable_kerberos                       = null
        kdc_db_key_uri                        = null
        key_password_uri                      = null
        keystore_password_uri                 = null
        keystore_uri                          = null
        kms_key_uri                           = null
        realm                                 = null
        root_principal_password_uri           = null
        tgt_lifetime_hours                    = null
        truststore_password_uri               = null
        truststore_uri                        = null
      }]
    }]
    software_config = [{
      image_version       = null
      optional_components = []
      override_properties = {}
      properties          = {}
    }]
    staging_bucket = null
    temp_bucket    = null
    worker_config = [{
      accelerators = [{
        accelerator_count = null
        accelerator_type  = null
      }]
      disk_config = [{
        boot_disk_size_gb = null
        boot_disk_type    = null
        num_local_ssds    = null
      }]
      image_uri        = null
      instance_names   = []
      machine_type     = null
      min_cpu_platform = null
      num_instances    = null
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
variable "graceful_decommission_timeout" {
  description = "(optional) - The timeout duration which allows graceful decomissioning when you change the number of worker nodes directly through a terraform apply"
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - The list of labels (key/value pairs) to be applied to instances in the cluster. GCP generates some itself including goog-dataproc-cluster-name which is the name of the cluster."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - The name of the cluster, unique within the project and zone."
  type        = string
}

variable "project" {
  description = "(optional) - The ID of the project in which the cluster will exist. If it is not provided, the provider project is used."
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The region in which the cluster and associated nodes will be created in. Defaults to global."
  type        = string
  default     = null
}

variable "cluster_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      autoscaling_config = list(object(
        {
          policy_uri = string
        }
      ))
      bucket = string
      encryption_config = list(object(
        {
          kms_key_name = string
        }
      ))
      gce_cluster_config = list(object(
        {
          internal_ip_only       = bool
          metadata               = map(string)
          network                = string
          service_account        = string
          service_account_scopes = set(string)
          subnetwork             = string
          tags                   = set(string)
          zone                   = string
        }
      ))
      initialization_action = list(object(
        {
          script      = string
          timeout_sec = number
        }
      ))
      master_config = list(object(
        {
          accelerators = set(object(
            {
              accelerator_count = number
              accelerator_type  = string
            }
          ))
          disk_config = list(object(
            {
              boot_disk_size_gb = number
              boot_disk_type    = string
              num_local_ssds    = number
            }
          ))
          image_uri        = string
          instance_names   = list(string)
          machine_type     = string
          min_cpu_platform = string
          num_instances    = number
        }
      ))
      preemptible_worker_config = list(object(
        {
          disk_config = list(object(
            {
              boot_disk_size_gb = number
              boot_disk_type    = string
              num_local_ssds    = number
            }
          ))
          instance_names = list(string)
          num_instances  = number
        }
      ))
      security_config = list(object(
        {
          kerberos_config = list(object(
            {
              cross_realm_trust_admin_server        = string
              cross_realm_trust_kdc                 = string
              cross_realm_trust_realm               = string
              cross_realm_trust_shared_password_uri = string
              enable_kerberos                       = bool
              kdc_db_key_uri                        = string
              key_password_uri                      = string
              keystore_password_uri                 = string
              keystore_uri                          = string
              kms_key_uri                           = string
              realm                                 = string
              root_principal_password_uri           = string
              tgt_lifetime_hours                    = number
              truststore_password_uri               = string
              truststore_uri                        = string
            }
          ))
        }
      ))
      software_config = list(object(
        {
          image_version       = string
          optional_components = set(string)
          override_properties = map(string)
          properties          = map(string)
        }
      ))
      staging_bucket = string
      temp_bucket    = string
      worker_config = list(object(
        {
          accelerators = set(object(
            {
              accelerator_count = number
              accelerator_type  = string
            }
          ))
          disk_config = list(object(
            {
              boot_disk_size_gb = number
              boot_disk_type    = string
              num_local_ssds    = number
            }
          ))
          image_uri        = string
          instance_names   = list(string)
          machine_type     = string
          min_cpu_platform = string
          num_instances    = number
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
resource "google_dataproc_cluster" "this" {
  # graceful_decommission_timeout - (optional) is a type of string
  graceful_decommission_timeout = var.graceful_decommission_timeout
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (required) is a type of string
  name = var.name
  # project - (optional) is a type of string
  project = var.project
  # region - (optional) is a type of string
  region = var.region

  dynamic "cluster_config" {
    for_each = var.cluster_config
    content {
      # staging_bucket - (optional) is a type of string
      staging_bucket = cluster_config.value["staging_bucket"]
      # temp_bucket - (optional) is a type of string
      temp_bucket = cluster_config.value["temp_bucket"]

      dynamic "autoscaling_config" {
        for_each = cluster_config.value.autoscaling_config
        content {
          # policy_uri - (required) is a type of string
          policy_uri = autoscaling_config.value["policy_uri"]
        }
      }

      dynamic "encryption_config" {
        for_each = cluster_config.value.encryption_config
        content {
          # kms_key_name - (required) is a type of string
          kms_key_name = encryption_config.value["kms_key_name"]
        }
      }

      dynamic "gce_cluster_config" {
        for_each = cluster_config.value.gce_cluster_config
        content {
          # internal_ip_only - (optional) is a type of bool
          internal_ip_only = gce_cluster_config.value["internal_ip_only"]
          # metadata - (optional) is a type of map of string
          metadata = gce_cluster_config.value["metadata"]
          # network - (optional) is a type of string
          network = gce_cluster_config.value["network"]
          # service_account - (optional) is a type of string
          service_account = gce_cluster_config.value["service_account"]
          # service_account_scopes - (optional) is a type of set of string
          service_account_scopes = gce_cluster_config.value["service_account_scopes"]
          # subnetwork - (optional) is a type of string
          subnetwork = gce_cluster_config.value["subnetwork"]
          # tags - (optional) is a type of set of string
          tags = gce_cluster_config.value["tags"]
          # zone - (optional) is a type of string
          zone = gce_cluster_config.value["zone"]
        }
      }

      dynamic "initialization_action" {
        for_each = cluster_config.value.initialization_action
        content {
          # script - (required) is a type of string
          script = initialization_action.value["script"]
          # timeout_sec - (optional) is a type of number
          timeout_sec = initialization_action.value["timeout_sec"]
        }
      }

      dynamic "master_config" {
        for_each = cluster_config.value.master_config
        content {
          # image_uri - (optional) is a type of string
          image_uri = master_config.value["image_uri"]
          # machine_type - (optional) is a type of string
          machine_type = master_config.value["machine_type"]
          # min_cpu_platform - (optional) is a type of string
          min_cpu_platform = master_config.value["min_cpu_platform"]
          # num_instances - (optional) is a type of number
          num_instances = master_config.value["num_instances"]

          dynamic "accelerators" {
            for_each = master_config.value.accelerators
            content {
              # accelerator_count - (required) is a type of number
              accelerator_count = accelerators.value["accelerator_count"]
              # accelerator_type - (required) is a type of string
              accelerator_type = accelerators.value["accelerator_type"]
            }
          }

          dynamic "disk_config" {
            for_each = master_config.value.disk_config
            content {
              # boot_disk_size_gb - (optional) is a type of number
              boot_disk_size_gb = disk_config.value["boot_disk_size_gb"]
              # boot_disk_type - (optional) is a type of string
              boot_disk_type = disk_config.value["boot_disk_type"]
              # num_local_ssds - (optional) is a type of number
              num_local_ssds = disk_config.value["num_local_ssds"]
            }
          }

        }
      }

      dynamic "preemptible_worker_config" {
        for_each = cluster_config.value.preemptible_worker_config
        content {
          # num_instances - (optional) is a type of number
          num_instances = preemptible_worker_config.value["num_instances"]

          dynamic "disk_config" {
            for_each = preemptible_worker_config.value.disk_config
            content {
              # boot_disk_size_gb - (optional) is a type of number
              boot_disk_size_gb = disk_config.value["boot_disk_size_gb"]
              # boot_disk_type - (optional) is a type of string
              boot_disk_type = disk_config.value["boot_disk_type"]
              # num_local_ssds - (optional) is a type of number
              num_local_ssds = disk_config.value["num_local_ssds"]
            }
          }

        }
      }

      dynamic "security_config" {
        for_each = cluster_config.value.security_config
        content {

          dynamic "kerberos_config" {
            for_each = security_config.value.kerberos_config
            content {
              # cross_realm_trust_admin_server - (optional) is a type of string
              cross_realm_trust_admin_server = kerberos_config.value["cross_realm_trust_admin_server"]
              # cross_realm_trust_kdc - (optional) is a type of string
              cross_realm_trust_kdc = kerberos_config.value["cross_realm_trust_kdc"]
              # cross_realm_trust_realm - (optional) is a type of string
              cross_realm_trust_realm = kerberos_config.value["cross_realm_trust_realm"]
              # cross_realm_trust_shared_password_uri - (optional) is a type of string
              cross_realm_trust_shared_password_uri = kerberos_config.value["cross_realm_trust_shared_password_uri"]
              # enable_kerberos - (optional) is a type of bool
              enable_kerberos = kerberos_config.value["enable_kerberos"]
              # kdc_db_key_uri - (optional) is a type of string
              kdc_db_key_uri = kerberos_config.value["kdc_db_key_uri"]
              # key_password_uri - (optional) is a type of string
              key_password_uri = kerberos_config.value["key_password_uri"]
              # keystore_password_uri - (optional) is a type of string
              keystore_password_uri = kerberos_config.value["keystore_password_uri"]
              # keystore_uri - (optional) is a type of string
              keystore_uri = kerberos_config.value["keystore_uri"]
              # kms_key_uri - (required) is a type of string
              kms_key_uri = kerberos_config.value["kms_key_uri"]
              # realm - (optional) is a type of string
              realm = kerberos_config.value["realm"]
              # root_principal_password_uri - (required) is a type of string
              root_principal_password_uri = kerberos_config.value["root_principal_password_uri"]
              # tgt_lifetime_hours - (optional) is a type of number
              tgt_lifetime_hours = kerberos_config.value["tgt_lifetime_hours"]
              # truststore_password_uri - (optional) is a type of string
              truststore_password_uri = kerberos_config.value["truststore_password_uri"]
              # truststore_uri - (optional) is a type of string
              truststore_uri = kerberos_config.value["truststore_uri"]
            }
          }

        }
      }

      dynamic "software_config" {
        for_each = cluster_config.value.software_config
        content {
          # image_version - (optional) is a type of string
          image_version = software_config.value["image_version"]
          # optional_components - (optional) is a type of set of string
          optional_components = software_config.value["optional_components"]
          # override_properties - (optional) is a type of map of string
          override_properties = software_config.value["override_properties"]
        }
      }

      dynamic "worker_config" {
        for_each = cluster_config.value.worker_config
        content {
          # image_uri - (optional) is a type of string
          image_uri = worker_config.value["image_uri"]
          # machine_type - (optional) is a type of string
          machine_type = worker_config.value["machine_type"]
          # min_cpu_platform - (optional) is a type of string
          min_cpu_platform = worker_config.value["min_cpu_platform"]
          # num_instances - (optional) is a type of number
          num_instances = worker_config.value["num_instances"]

          dynamic "accelerators" {
            for_each = worker_config.value.accelerators
            content {
              # accelerator_count - (required) is a type of number
              accelerator_count = accelerators.value["accelerator_count"]
              # accelerator_type - (required) is a type of string
              accelerator_type = accelerators.value["accelerator_type"]
            }
          }

          dynamic "disk_config" {
            for_each = worker_config.value.disk_config
            content {
              # boot_disk_size_gb - (optional) is a type of number
              boot_disk_size_gb = disk_config.value["boot_disk_size_gb"]
              # boot_disk_type - (optional) is a type of string
              boot_disk_type = disk_config.value["boot_disk_type"]
              # num_local_ssds - (optional) is a type of number
              num_local_ssds = disk_config.value["num_local_ssds"]
            }
          }

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
  value       = google_dataproc_cluster.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = google_dataproc_cluster.this.labels
}

output "project" {
  description = "returns a string"
  value       = google_dataproc_cluster.this.project
}

output "this" {
  value = google_dataproc_cluster.this
}
```

[top](#index)