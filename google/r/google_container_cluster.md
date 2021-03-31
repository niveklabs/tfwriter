# google_container_cluster

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
    google = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_container_cluster" {
  source = "./modules/google/r/google_container_cluster"

  # cluster_ipv4_cidr - (optional) is a type of string
  cluster_ipv4_cidr = null
  # datapath_provider - (optional) is a type of string
  datapath_provider = null
  # default_max_pods_per_node - (optional) is a type of number
  default_max_pods_per_node = null
  # description - (optional) is a type of string
  description = null
  # enable_binary_authorization - (optional) is a type of bool
  enable_binary_authorization = null
  # enable_intranode_visibility - (optional) is a type of bool
  enable_intranode_visibility = null
  # enable_kubernetes_alpha - (optional) is a type of bool
  enable_kubernetes_alpha = null
  # enable_legacy_abac - (optional) is a type of bool
  enable_legacy_abac = null
  # enable_shielded_nodes - (optional) is a type of bool
  enable_shielded_nodes = null
  # enable_tpu - (optional) is a type of bool
  enable_tpu = null
  # initial_node_count - (optional) is a type of number
  initial_node_count = null
  # location - (optional) is a type of string
  location = null
  # logging_service - (optional) is a type of string
  logging_service = null
  # min_master_version - (optional) is a type of string
  min_master_version = null
  # monitoring_service - (optional) is a type of string
  monitoring_service = null
  # name - (required) is a type of string
  name = null
  # network - (optional) is a type of string
  network = null
  # node_locations - (optional) is a type of set of string
  node_locations = []
  # node_version - (optional) is a type of string
  node_version = null
  # project - (optional) is a type of string
  project = null
  # remove_default_node_pool - (optional) is a type of bool
  remove_default_node_pool = null
  # resource_labels - (optional) is a type of map of string
  resource_labels = {}
  # subnetwork - (optional) is a type of string
  subnetwork = null

  addons_config = [{
    cloudrun_config = [{
      disabled           = null
      load_balancer_type = null
    }]
    horizontal_pod_autoscaling = [{
      disabled = null
    }]
    http_load_balancing = [{
      disabled = null
    }]
    network_policy_config = [{
      disabled = null
    }]
  }]

  authenticator_groups_config = [{
    security_group = null
  }]

  cluster_autoscaling = [{
    auto_provisioning_defaults = [{
      oauth_scopes    = []
      service_account = null
    }]
    enabled = null
    resource_limits = [{
      maximum       = null
      minimum       = null
      resource_type = null
    }]
  }]

  database_encryption = [{
    key_name = null
    state    = null
  }]

  default_snat_status = [{
    disabled = null
  }]

  ip_allocation_policy = [{
    cluster_ipv4_cidr_block       = null
    cluster_secondary_range_name  = null
    services_ipv4_cidr_block      = null
    services_secondary_range_name = null
  }]

  maintenance_policy = [{
    daily_maintenance_window = [{
      duration   = null
      start_time = null
    }]
    maintenance_exclusion = [{
      end_time       = null
      exclusion_name = null
      start_time     = null
    }]
    recurring_window = [{
      end_time   = null
      recurrence = null
      start_time = null
    }]
  }]

  master_auth = [{
    client_certificate = null
    client_certificate_config = [{
      issue_client_certificate = null
    }]
    client_key             = null
    cluster_ca_certificate = null
    password               = null
    username               = null
  }]

  master_authorized_networks_config = [{
    cidr_blocks = [{
      cidr_block   = null
      display_name = null
    }]
  }]

  network_policy = [{
    enabled  = null
    provider = null
  }]

  node_config = [{
    disk_size_gb = null
    disk_type    = null
    guest_accelerator = [{
      count = null
      type  = null
    }]
    image_type       = null
    labels           = {}
    local_ssd_count  = null
    machine_type     = null
    metadata         = {}
    min_cpu_platform = null
    oauth_scopes     = []
    preemptible      = null
    service_account  = null
    shielded_instance_config = [{
      enable_integrity_monitoring = null
      enable_secure_boot          = null
    }]
    tags = []
    taint = [{
      effect = null
      key    = null
      value  = null
    }]
    workload_metadata_config = [{
      node_metadata = null
    }]
  }]

  node_pool = [{
    autoscaling = [{
      max_node_count = null
      min_node_count = null
    }]
    initial_node_count  = null
    instance_group_urls = []
    management = [{
      auto_repair  = null
      auto_upgrade = null
    }]
    max_pods_per_node = null
    name              = null
    name_prefix       = null
    node_config = [{
      disk_size_gb = null
      disk_type    = null
      guest_accelerator = [{
        count = null
        type  = null
      }]
      image_type       = null
      labels           = {}
      local_ssd_count  = null
      machine_type     = null
      metadata         = {}
      min_cpu_platform = null
      oauth_scopes     = []
      preemptible      = null
      service_account  = null
      shielded_instance_config = [{
        enable_integrity_monitoring = null
        enable_secure_boot          = null
      }]
      tags = []
      taint = [{
        effect = null
        key    = null
        value  = null
      }]
      workload_metadata_config = [{
        node_metadata = null
      }]
    }]
    node_count     = null
    node_locations = []
    upgrade_settings = [{
      max_surge       = null
      max_unavailable = null
    }]
    version = null
  }]

  pod_security_policy_config = [{
    enabled = null
  }]

  private_cluster_config = [{
    enable_private_endpoint = null
    enable_private_nodes    = null
    master_global_access_config = [{
      enabled = null
    }]
    master_ipv4_cidr_block = null
    peering_name           = null
    private_endpoint       = null
    public_endpoint        = null
  }]

  release_channel = [{
    channel = null
  }]

  resource_usage_export_config = [{
    bigquery_destination = [{
      dataset_id = null
    }]
    enable_network_egress_metering       = null
    enable_resource_consumption_metering = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]

  vertical_pod_autoscaling = [{
    enabled = null
  }]

  workload_identity_config = [{
    identity_namespace = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cluster_ipv4_cidr" {
  description = "(optional) - The IP address range of the Kubernetes pods in this cluster in CIDR notation (e.g. 10.96.0.0/14). Leave blank to have one automatically chosen or specify a /14 block in 10.0.0.0/8. This field will only work for routes-based clusters, where ip_allocation_policy is not defined."
  type        = string
  default     = null
}

variable "datapath_provider" {
  description = "(optional) - The desired datapath provider for this cluster. By default, uses the IPTables-based kube-proxy implementation."
  type        = string
  default     = null
}

variable "default_max_pods_per_node" {
  description = "(optional) - The default maximum number of pods per node in this cluster. This doesn't work on \"routes-based\" clusters, clusters that don't have IP Aliasing enabled."
  type        = number
  default     = null
}

variable "description" {
  description = "(optional) -  Description of the cluster."
  type        = string
  default     = null
}

variable "enable_binary_authorization" {
  description = "(optional) - Enable Binary Authorization for this cluster. If enabled, all container images will be validated by Google Binary Authorization."
  type        = bool
  default     = null
}

variable "enable_intranode_visibility" {
  description = "(optional) - Whether Intra-node visibility is enabled for this cluster. This makes same node pod to pod traffic visible for VPC network."
  type        = bool
  default     = null
}

variable "enable_kubernetes_alpha" {
  description = "(optional) - Whether to enable Kubernetes Alpha features for this cluster. Note that when this option is enabled, the cluster cannot be upgraded and will be automatically deleted after 30 days."
  type        = bool
  default     = null
}

variable "enable_legacy_abac" {
  description = "(optional) - Whether the ABAC authorizer is enabled for this cluster. When enabled, identities in the system, including service accounts, nodes, and controllers, will have statically granted permissions beyond those provided by the RBAC configuration or IAM. Defaults to false."
  type        = bool
  default     = null
}

variable "enable_shielded_nodes" {
  description = "(optional) - Enable Shielded Nodes features on all nodes in this cluster. Defaults to false."
  type        = bool
  default     = null
}

variable "enable_tpu" {
  description = "(optional) - Whether to enable Cloud TPU resources in this cluster."
  type        = bool
  default     = null
}

variable "initial_node_count" {
  description = "(optional) - The number of nodes to create in this cluster's default node pool. In regional or multi-zonal clusters, this is the number of nodes per zone. Must be set if node_pool is not set. If you're using google_container_node_pool objects with no default node pool, you'll need to set this to a value of at least 1, alongside setting remove_default_node_pool to true."
  type        = number
  default     = null
}

variable "location" {
  description = "(optional) - The location (region or zone) in which the cluster master will be created, as well as the default node location. If you specify a zone (such as us-central1-a), the cluster will be a zonal cluster with a single cluster master. If you specify a region (such as us-west1), the cluster will be a regional cluster with multiple masters spread across zones in the region, and with default node locations in those zones as well."
  type        = string
  default     = null
}

variable "logging_service" {
  description = "(optional) - The logging service that the cluster should write logs to. Available options include logging.googleapis.com(Legacy Stackdriver), logging.googleapis.com/kubernetes(Stackdriver Kubernetes Engine Logging), and none. Defaults to logging.googleapis.com/kubernetes."
  type        = string
  default     = null
}

variable "min_master_version" {
  description = "(optional) - The minimum version of the master. GKE will auto-update the master to new versions, so this does not guarantee the current master version--use the read-only master_version field to obtain that. If unset, the cluster's version will be set by GKE to the version of the most recent official release (which is not necessarily the latest version)."
  type        = string
  default     = null
}

variable "monitoring_service" {
  description = "(optional) - The monitoring service that the cluster should write metrics to. Automatically send metrics from pods in the cluster to the Google Cloud Monitoring API. VM metrics will be collected by Google Compute Engine regardless of this setting Available options include monitoring.googleapis.com(Legacy Stackdriver), monitoring.googleapis.com/kubernetes(Stackdriver Kubernetes Engine Monitoring), and none. Defaults to monitoring.googleapis.com/kubernetes."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The name of the cluster, unique within the project and location."
  type        = string
}

variable "network" {
  description = "(optional) - The name or self_link of the Google Compute Engine network to which the cluster is connected. For Shared VPC, set this to the self link of the shared network."
  type        = string
  default     = null
}

variable "node_locations" {
  description = "(optional) - The list of zones in which the cluster's nodes are located. Nodes must be in the region of their regional cluster or in the same region as their cluster's zone for zonal clusters. If this is specified for a zonal cluster, omit the cluster's zone."
  type        = set(string)
  default     = null
}

variable "node_version" {
  description = "(optional) - The Kubernetes version on the nodes. Must either be unset or set to the same value as min_master_version on create. Defaults to the default version set by GKE which is not necessarily the latest version. This only affects nodes in the default node pool. While a fuzzy version can be specified, it's recommended that you specify explicit versions as Terraform will see spurious diffs when fuzzy versions are used. See the google_container_engine_versions data source's version_prefix field to approximate fuzzy versions in a Terraform-compatible way. To update nodes in other node pools, use the version attribute on the node pool."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional) - The ID of the project in which the resource belongs. If it is not provided, the provider project is used."
  type        = string
  default     = null
}

variable "remove_default_node_pool" {
  description = "(optional) - If true, deletes the default node pool upon cluster creation. If you're using google_container_node_pool resources with no default node pool, this should be set to true, alongside setting initial_node_count to at least 1."
  type        = bool
  default     = null
}

variable "resource_labels" {
  description = "(optional) - The GCE resource labels (a map of key/value pairs) to be applied to the cluster."
  type        = map(string)
  default     = null
}

variable "subnetwork" {
  description = "(optional) - The name or self_link of the Google Compute Engine subnetwork in which the cluster's instances are launched."
  type        = string
  default     = null
}

variable "addons_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cloudrun_config = list(object(
        {
          disabled           = bool
          load_balancer_type = string
        }
      ))
      horizontal_pod_autoscaling = list(object(
        {
          disabled = bool
        }
      ))
      http_load_balancing = list(object(
        {
          disabled = bool
        }
      ))
      network_policy_config = list(object(
        {
          disabled = bool
        }
      ))
    }
  ))
  default = []
}

variable "authenticator_groups_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      security_group = string
    }
  ))
  default = []
}

variable "cluster_autoscaling" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      auto_provisioning_defaults = list(object(
        {
          oauth_scopes    = list(string)
          service_account = string
        }
      ))
      enabled = bool
      resource_limits = list(object(
        {
          maximum       = number
          minimum       = number
          resource_type = string
        }
      ))
    }
  ))
  default = []
}

variable "database_encryption" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      key_name = string
      state    = string
    }
  ))
  default = []
}

variable "default_snat_status" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      disabled = bool
    }
  ))
  default = []
}

variable "ip_allocation_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cluster_ipv4_cidr_block       = string
      cluster_secondary_range_name  = string
      services_ipv4_cidr_block      = string
      services_secondary_range_name = string
    }
  ))
  default = []
}

variable "maintenance_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      daily_maintenance_window = list(object(
        {
          duration   = string
          start_time = string
        }
      ))
      maintenance_exclusion = set(object(
        {
          end_time       = string
          exclusion_name = string
          start_time     = string
        }
      ))
      recurring_window = list(object(
        {
          end_time   = string
          recurrence = string
          start_time = string
        }
      ))
    }
  ))
  default = []
}

variable "master_auth" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      client_certificate = string
      client_certificate_config = list(object(
        {
          issue_client_certificate = bool
        }
      ))
      client_key             = string
      cluster_ca_certificate = string
      password               = string
      username               = string
    }
  ))
  default = []
}

variable "master_authorized_networks_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cidr_blocks = set(object(
        {
          cidr_block   = string
          display_name = string
        }
      ))
    }
  ))
  default = []
}

variable "network_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled  = bool
      provider = string
    }
  ))
  default = []
}

variable "node_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      disk_size_gb = number
      disk_type    = string
      guest_accelerator = list(object(
        {
          count = number
          type  = string
        }
      ))
      image_type       = string
      labels           = map(string)
      local_ssd_count  = number
      machine_type     = string
      metadata         = map(string)
      min_cpu_platform = string
      oauth_scopes     = set(string)
      preemptible      = bool
      service_account  = string
      shielded_instance_config = list(object(
        {
          enable_integrity_monitoring = bool
          enable_secure_boot          = bool
        }
      ))
      tags = list(string)
      taint = list(object(
        {
          effect = string
          key    = string
          value  = string
        }
      ))
      workload_metadata_config = list(object(
        {
          node_metadata = string
        }
      ))
    }
  ))
  default = []
}

variable "node_pool" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      autoscaling = list(object(
        {
          max_node_count = number
          min_node_count = number
        }
      ))
      initial_node_count  = number
      instance_group_urls = list(string)
      management = list(object(
        {
          auto_repair  = bool
          auto_upgrade = bool
        }
      ))
      max_pods_per_node = number
      name              = string
      name_prefix       = string
      node_config = list(object(
        {
          disk_size_gb = number
          disk_type    = string
          guest_accelerator = list(object(
            {
              count = number
              type  = string
            }
          ))
          image_type       = string
          labels           = map(string)
          local_ssd_count  = number
          machine_type     = string
          metadata         = map(string)
          min_cpu_platform = string
          oauth_scopes     = set(string)
          preemptible      = bool
          service_account  = string
          shielded_instance_config = list(object(
            {
              enable_integrity_monitoring = bool
              enable_secure_boot          = bool
            }
          ))
          tags = list(string)
          taint = list(object(
            {
              effect = string
              key    = string
              value  = string
            }
          ))
          workload_metadata_config = list(object(
            {
              node_metadata = string
            }
          ))
        }
      ))
      node_count     = number
      node_locations = set(string)
      upgrade_settings = list(object(
        {
          max_surge       = number
          max_unavailable = number
        }
      ))
      version = string
    }
  ))
  default = []
}

variable "pod_security_policy_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled = bool
    }
  ))
  default = []
}

variable "private_cluster_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enable_private_endpoint = bool
      enable_private_nodes    = bool
      master_global_access_config = list(object(
        {
          enabled = bool
        }
      ))
      master_ipv4_cidr_block = string
      peering_name           = string
      private_endpoint       = string
      public_endpoint        = string
    }
  ))
  default = []
}

variable "release_channel" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      channel = string
    }
  ))
  default = []
}

variable "resource_usage_export_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      bigquery_destination = list(object(
        {
          dataset_id = string
        }
      ))
      enable_network_egress_metering       = bool
      enable_resource_consumption_metering = bool
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
      read   = string
      update = string
    }
  ))
  default = []
}

variable "vertical_pod_autoscaling" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled = bool
    }
  ))
  default = []
}

variable "workload_identity_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      identity_namespace = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_container_cluster" "this" {
  cluster_ipv4_cidr           = var.cluster_ipv4_cidr
  datapath_provider           = var.datapath_provider
  default_max_pods_per_node   = var.default_max_pods_per_node
  description                 = var.description
  enable_binary_authorization = var.enable_binary_authorization
  enable_intranode_visibility = var.enable_intranode_visibility
  enable_kubernetes_alpha     = var.enable_kubernetes_alpha
  enable_legacy_abac          = var.enable_legacy_abac
  enable_shielded_nodes       = var.enable_shielded_nodes
  enable_tpu                  = var.enable_tpu
  initial_node_count          = var.initial_node_count
  location                    = var.location
  logging_service             = var.logging_service
  min_master_version          = var.min_master_version
  monitoring_service          = var.monitoring_service
  name                        = var.name
  network                     = var.network
  node_locations              = var.node_locations
  node_version                = var.node_version
  project                     = var.project
  remove_default_node_pool    = var.remove_default_node_pool
  resource_labels             = var.resource_labels
  subnetwork                  = var.subnetwork

  dynamic "addons_config" {
    for_each = var.addons_config
    content {

      dynamic "cloudrun_config" {
        for_each = addons_config.value.cloudrun_config
        content {
          disabled           = cloudrun_config.value["disabled"]
          load_balancer_type = cloudrun_config.value["load_balancer_type"]
        }
      }

      dynamic "horizontal_pod_autoscaling" {
        for_each = addons_config.value.horizontal_pod_autoscaling
        content {
          disabled = horizontal_pod_autoscaling.value["disabled"]
        }
      }

      dynamic "http_load_balancing" {
        for_each = addons_config.value.http_load_balancing
        content {
          disabled = http_load_balancing.value["disabled"]
        }
      }

      dynamic "network_policy_config" {
        for_each = addons_config.value.network_policy_config
        content {
          disabled = network_policy_config.value["disabled"]
        }
      }

    }
  }

  dynamic "authenticator_groups_config" {
    for_each = var.authenticator_groups_config
    content {
      security_group = authenticator_groups_config.value["security_group"]
    }
  }

  dynamic "cluster_autoscaling" {
    for_each = var.cluster_autoscaling
    content {
      enabled = cluster_autoscaling.value["enabled"]

      dynamic "auto_provisioning_defaults" {
        for_each = cluster_autoscaling.value.auto_provisioning_defaults
        content {
          oauth_scopes    = auto_provisioning_defaults.value["oauth_scopes"]
          service_account = auto_provisioning_defaults.value["service_account"]
        }
      }

      dynamic "resource_limits" {
        for_each = cluster_autoscaling.value.resource_limits
        content {
          maximum       = resource_limits.value["maximum"]
          minimum       = resource_limits.value["minimum"]
          resource_type = resource_limits.value["resource_type"]
        }
      }

    }
  }

  dynamic "database_encryption" {
    for_each = var.database_encryption
    content {
      key_name = database_encryption.value["key_name"]
      state    = database_encryption.value["state"]
    }
  }

  dynamic "default_snat_status" {
    for_each = var.default_snat_status
    content {
      disabled = default_snat_status.value["disabled"]
    }
  }

  dynamic "ip_allocation_policy" {
    for_each = var.ip_allocation_policy
    content {
      cluster_ipv4_cidr_block       = ip_allocation_policy.value["cluster_ipv4_cidr_block"]
      cluster_secondary_range_name  = ip_allocation_policy.value["cluster_secondary_range_name"]
      services_ipv4_cidr_block      = ip_allocation_policy.value["services_ipv4_cidr_block"]
      services_secondary_range_name = ip_allocation_policy.value["services_secondary_range_name"]
    }
  }

  dynamic "maintenance_policy" {
    for_each = var.maintenance_policy
    content {

      dynamic "daily_maintenance_window" {
        for_each = maintenance_policy.value.daily_maintenance_window
        content {
          start_time = daily_maintenance_window.value["start_time"]
        }
      }

      dynamic "maintenance_exclusion" {
        for_each = maintenance_policy.value.maintenance_exclusion
        content {
          end_time       = maintenance_exclusion.value["end_time"]
          exclusion_name = maintenance_exclusion.value["exclusion_name"]
          start_time     = maintenance_exclusion.value["start_time"]
        }
      }

      dynamic "recurring_window" {
        for_each = maintenance_policy.value.recurring_window
        content {
          end_time   = recurring_window.value["end_time"]
          recurrence = recurring_window.value["recurrence"]
          start_time = recurring_window.value["start_time"]
        }
      }

    }
  }

  dynamic "master_auth" {
    for_each = var.master_auth
    content {
      password = master_auth.value["password"]
      username = master_auth.value["username"]

      dynamic "client_certificate_config" {
        for_each = master_auth.value.client_certificate_config
        content {
          issue_client_certificate = client_certificate_config.value["issue_client_certificate"]
        }
      }

    }
  }

  dynamic "master_authorized_networks_config" {
    for_each = var.master_authorized_networks_config
    content {

      dynamic "cidr_blocks" {
        for_each = master_authorized_networks_config.value.cidr_blocks
        content {
          cidr_block   = cidr_blocks.value["cidr_block"]
          display_name = cidr_blocks.value["display_name"]
        }
      }

    }
  }

  dynamic "network_policy" {
    for_each = var.network_policy
    content {
      enabled  = network_policy.value["enabled"]
      provider = network_policy.value["provider"]
    }
  }

  dynamic "node_config" {
    for_each = var.node_config
    content {
      disk_size_gb      = node_config.value["disk_size_gb"]
      disk_type         = node_config.value["disk_type"]
      guest_accelerator = node_config.value["guest_accelerator"]
      image_type        = node_config.value["image_type"]
      labels            = node_config.value["labels"]
      local_ssd_count   = node_config.value["local_ssd_count"]
      machine_type      = node_config.value["machine_type"]
      metadata          = node_config.value["metadata"]
      min_cpu_platform  = node_config.value["min_cpu_platform"]
      oauth_scopes      = node_config.value["oauth_scopes"]
      preemptible       = node_config.value["preemptible"]
      service_account   = node_config.value["service_account"]
      tags              = node_config.value["tags"]
      taint             = node_config.value["taint"]

      dynamic "shielded_instance_config" {
        for_each = node_config.value.shielded_instance_config
        content {
          enable_integrity_monitoring = shielded_instance_config.value["enable_integrity_monitoring"]
          enable_secure_boot          = shielded_instance_config.value["enable_secure_boot"]
        }
      }

      dynamic "workload_metadata_config" {
        for_each = node_config.value.workload_metadata_config
        content {
          node_metadata = workload_metadata_config.value["node_metadata"]
        }
      }

    }
  }

  dynamic "node_pool" {
    for_each = var.node_pool
    content {
      initial_node_count = node_pool.value["initial_node_count"]
      max_pods_per_node  = node_pool.value["max_pods_per_node"]
      name               = node_pool.value["name"]
      name_prefix        = node_pool.value["name_prefix"]
      node_count         = node_pool.value["node_count"]
      node_locations     = node_pool.value["node_locations"]
      version            = node_pool.value["version"]

      dynamic "autoscaling" {
        for_each = node_pool.value.autoscaling
        content {
          max_node_count = autoscaling.value["max_node_count"]
          min_node_count = autoscaling.value["min_node_count"]
        }
      }

      dynamic "management" {
        for_each = node_pool.value.management
        content {
          auto_repair  = management.value["auto_repair"]
          auto_upgrade = management.value["auto_upgrade"]
        }
      }

      dynamic "node_config" {
        for_each = node_pool.value.node_config
        content {
          disk_size_gb      = node_config.value["disk_size_gb"]
          disk_type         = node_config.value["disk_type"]
          guest_accelerator = node_config.value["guest_accelerator"]
          image_type        = node_config.value["image_type"]
          labels            = node_config.value["labels"]
          local_ssd_count   = node_config.value["local_ssd_count"]
          machine_type      = node_config.value["machine_type"]
          metadata          = node_config.value["metadata"]
          min_cpu_platform  = node_config.value["min_cpu_platform"]
          oauth_scopes      = node_config.value["oauth_scopes"]
          preemptible       = node_config.value["preemptible"]
          service_account   = node_config.value["service_account"]
          tags              = node_config.value["tags"]
          taint             = node_config.value["taint"]

          dynamic "shielded_instance_config" {
            for_each = node_config.value.shielded_instance_config
            content {
              enable_integrity_monitoring = shielded_instance_config.value["enable_integrity_monitoring"]
              enable_secure_boot          = shielded_instance_config.value["enable_secure_boot"]
            }
          }

          dynamic "workload_metadata_config" {
            for_each = node_config.value.workload_metadata_config
            content {
              node_metadata = workload_metadata_config.value["node_metadata"]
            }
          }

        }
      }

      dynamic "upgrade_settings" {
        for_each = node_pool.value.upgrade_settings
        content {
          max_surge       = upgrade_settings.value["max_surge"]
          max_unavailable = upgrade_settings.value["max_unavailable"]
        }
      }

    }
  }

  dynamic "pod_security_policy_config" {
    for_each = var.pod_security_policy_config
    content {
      enabled = pod_security_policy_config.value["enabled"]
    }
  }

  dynamic "private_cluster_config" {
    for_each = var.private_cluster_config
    content {
      enable_private_endpoint = private_cluster_config.value["enable_private_endpoint"]
      enable_private_nodes    = private_cluster_config.value["enable_private_nodes"]
      master_ipv4_cidr_block  = private_cluster_config.value["master_ipv4_cidr_block"]

      dynamic "master_global_access_config" {
        for_each = private_cluster_config.value.master_global_access_config
        content {
          enabled = master_global_access_config.value["enabled"]
        }
      }

    }
  }

  dynamic "release_channel" {
    for_each = var.release_channel
    content {
      channel = release_channel.value["channel"]
    }
  }

  dynamic "resource_usage_export_config" {
    for_each = var.resource_usage_export_config
    content {
      enable_network_egress_metering       = resource_usage_export_config.value["enable_network_egress_metering"]
      enable_resource_consumption_metering = resource_usage_export_config.value["enable_resource_consumption_metering"]

      dynamic "bigquery_destination" {
        for_each = resource_usage_export_config.value.bigquery_destination
        content {
          dataset_id = bigquery_destination.value["dataset_id"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
      update = timeouts.value["update"]
    }
  }

  dynamic "vertical_pod_autoscaling" {
    for_each = var.vertical_pod_autoscaling
    content {
      enabled = vertical_pod_autoscaling.value["enabled"]
    }
  }

  dynamic "workload_identity_config" {
    for_each = var.workload_identity_config
    content {
      identity_namespace = workload_identity_config.value["identity_namespace"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cluster_ipv4_cidr" {
  description = "returns a string"
  value       = google_container_cluster.this.cluster_ipv4_cidr
}

output "datapath_provider" {
  description = "returns a string"
  value       = google_container_cluster.this.datapath_provider
}

output "default_max_pods_per_node" {
  description = "returns a number"
  value       = google_container_cluster.this.default_max_pods_per_node
}

output "endpoint" {
  description = "returns a string"
  value       = google_container_cluster.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = google_container_cluster.this.id
}

output "instance_group_urls" {
  description = "returns a list of string"
  value       = google_container_cluster.this.instance_group_urls
}

output "label_fingerprint" {
  description = "returns a string"
  value       = google_container_cluster.this.label_fingerprint
}

output "location" {
  description = "returns a string"
  value       = google_container_cluster.this.location
}

output "logging_service" {
  description = "returns a string"
  value       = google_container_cluster.this.logging_service
}

output "master_version" {
  description = "returns a string"
  value       = google_container_cluster.this.master_version
}

output "monitoring_service" {
  description = "returns a string"
  value       = google_container_cluster.this.monitoring_service
}

output "node_locations" {
  description = "returns a set of string"
  value       = google_container_cluster.this.node_locations
}

output "node_version" {
  description = "returns a string"
  value       = google_container_cluster.this.node_version
}

output "operation" {
  description = "returns a string"
  value       = google_container_cluster.this.operation
}

output "project" {
  description = "returns a string"
  value       = google_container_cluster.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_container_cluster.this.self_link
}

output "services_ipv4_cidr" {
  description = "returns a string"
  value       = google_container_cluster.this.services_ipv4_cidr
}

output "subnetwork" {
  description = "returns a string"
  value       = google_container_cluster.this.subnetwork
}

output "tpu_ipv4_cidr_block" {
  description = "returns a string"
  value       = google_container_cluster.this.tpu_ipv4_cidr_block
}

output "this" {
  value = google_container_cluster.this
}
```

[top](#index)