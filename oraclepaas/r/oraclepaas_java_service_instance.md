# oraclepaas_java_service_instance

[back](../oraclepaas.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oraclepaas = ">= 1.5.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oraclepaas_java_service_instance" {
  source = "./modules/oraclepaas/r/oraclepaas_java_service_instance"

  # assign_public_ip - (optional) is a type of bool
  assign_public_ip = null
  # availability_domain - (optional) is a type of string
  availability_domain = null
  # backup_destination - (optional) is a type of string
  backup_destination = null
  # bring_your_own_license - (optional) is a type of bool
  bring_your_own_license = null
  # description - (optional) is a type of string
  description = null
  # desired_state - (optional) is a type of string
  desired_state = null
  # edition - (required) is a type of string
  edition = null
  # enable_admin_console - (optional) is a type of bool
  enable_admin_console = null
  # force_delete - (optional) is a type of bool
  force_delete = null
  # ip_network - (optional) is a type of string
  ip_network = null
  # level - (optional) is a type of string
  level = null
  # metering_frequency - (optional) is a type of string
  metering_frequency = null
  # name - (required) is a type of string
  name = null
  # notification_email - (optional) is a type of string
  notification_email = null
  # region - (optional) is a type of string
  region = null
  # service_version - (optional) is a type of string
  service_version = null
  # snapshot_name - (optional) is a type of string
  snapshot_name = null
  # source_service_name - (optional) is a type of string
  source_service_name = null
  # ssh_public_key - (required) is a type of string
  ssh_public_key = null
  # subnet - (optional) is a type of string
  subnet = null
  # use_identity_service - (optional) is a type of bool
  use_identity_service = null

  backups = [{
    auto_generate           = null
    cloud_storage_container = null
    cloud_storage_password  = null
    cloud_storage_username  = null
    use_oauth_for_storage   = null
  }]

  load_balancer = [{
    admin_url             = null
    console_url           = null
    load_balancing_policy = null
    subnets               = []
    url                   = null
  }]

  oracle_traffic_director = [{
    admin = [{
      hostname = null
      password = null
      port     = null
      username = null
    }]
    high_availability = null
    ip_reservations   = []
    listener = [{
      port                    = null
      privileged_port         = null
      privileged_secured_port = null
      secured_port            = null
    }]
    load_balancing_policy = null
    root_url              = null
    shape                 = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]

  weblogic_server = [{
    admin = [{
      hostname     = null
      password     = null
      port         = null
      secured_port = null
      username     = null
    }]
    application_database = [{
      name     = null
      password = null
      pdb_name = null
      username = null
    }]
    backup_volume_size = null
    cluster = [{
      name             = null
      path_prefixes    = []
      server_count     = null
      servers_per_node = null
      shape            = null
      type             = null
    }]
    cluster_name   = null
    connect_string = null
    database = [{
      hostname = null
      name     = null
      password = null
      pdb_name = null
      username = null
    }]
    domain = [{
      mode            = null
      name            = null
      partition_count = null
      volume_size     = null
    }]
    ip_reservations = []
    managed_servers = [{
      initial_heap_size            = null
      initial_permanent_generation = null
      jvm_args                     = null
      max_heap_size                = null
      max_permanent_generation     = null
      overwrite_jvm_args           = null
      server_count                 = null
    }]
    middleware_volume_size = null
    node_manager = [{
      password = null
      port     = null
      username = null
    }]
    ports = [{
      content_port                    = null
      deployment_channel_port         = null
      privileged_content_port         = null
      privileged_secured_content_port = null
    }]
    root_url                 = null
    shape                    = null
    upper_stack_product_name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "assign_public_ip" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "availability_domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "backup_destination" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bring_your_own_license" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "desired_state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "edition" {
  description = "(required)"
  type        = string
}

variable "enable_admin_console" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "force_delete" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ip_network" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "level" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "metering_frequency" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "notification_email" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "snapshot_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_service_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssh_public_key" {
  description = "(required)"
  type        = string
}

variable "subnet" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "use_identity_service" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "backups" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      auto_generate           = bool
      cloud_storage_container = string
      cloud_storage_password  = string
      cloud_storage_username  = string
      use_oauth_for_storage   = bool
    }
  ))
}

variable "load_balancer" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      admin_url             = string
      console_url           = string
      load_balancing_policy = string
      subnets               = set(string)
      url                   = string
    }
  ))
  default = []
}

variable "oracle_traffic_director" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      admin = list(object(
        {
          hostname = string
          password = string
          port     = number
          username = string
        }
      ))
      high_availability = bool
      ip_reservations   = list(string)
      listener = list(object(
        {
          port                    = number
          privileged_port         = number
          privileged_secured_port = number
          secured_port            = number
        }
      ))
      load_balancing_policy = string
      root_url              = string
      shape                 = string
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

variable "weblogic_server" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      admin = list(object(
        {
          hostname     = string
          password     = string
          port         = number
          secured_port = number
          username     = string
        }
      ))
      application_database = set(object(
        {
          name     = string
          password = string
          pdb_name = string
          username = string
        }
      ))
      backup_volume_size = string
      cluster = list(object(
        {
          name             = string
          path_prefixes    = set(string)
          server_count     = number
          servers_per_node = number
          shape            = string
          type             = string
        }
      ))
      cluster_name   = string
      connect_string = string
      database = list(object(
        {
          hostname = string
          name     = string
          password = string
          pdb_name = string
          username = string
        }
      ))
      domain = list(object(
        {
          mode            = string
          name            = string
          partition_count = number
          volume_size     = string
        }
      ))
      ip_reservations = list(string)
      managed_servers = list(object(
        {
          initial_heap_size            = number
          initial_permanent_generation = number
          jvm_args                     = string
          max_heap_size                = number
          max_permanent_generation     = number
          overwrite_jvm_args           = bool
          server_count                 = number
        }
      ))
      middleware_volume_size = string
      node_manager = list(object(
        {
          password = string
          port     = number
          username = string
        }
      ))
      ports = list(object(
        {
          content_port                    = number
          deployment_channel_port         = number
          privileged_content_port         = number
          privileged_secured_content_port = number
        }
      ))
      root_url                 = string
      shape                    = string
      upper_stack_product_name = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "oraclepaas_java_service_instance" "this" {
  # assign_public_ip - (optional) is a type of bool
  assign_public_ip = var.assign_public_ip
  # availability_domain - (optional) is a type of string
  availability_domain = var.availability_domain
  # backup_destination - (optional) is a type of string
  backup_destination = var.backup_destination
  # bring_your_own_license - (optional) is a type of bool
  bring_your_own_license = var.bring_your_own_license
  # description - (optional) is a type of string
  description = var.description
  # desired_state - (optional) is a type of string
  desired_state = var.desired_state
  # edition - (required) is a type of string
  edition = var.edition
  # enable_admin_console - (optional) is a type of bool
  enable_admin_console = var.enable_admin_console
  # force_delete - (optional) is a type of bool
  force_delete = var.force_delete
  # ip_network - (optional) is a type of string
  ip_network = var.ip_network
  # level - (optional) is a type of string
  level = var.level
  # metering_frequency - (optional) is a type of string
  metering_frequency = var.metering_frequency
  # name - (required) is a type of string
  name = var.name
  # notification_email - (optional) is a type of string
  notification_email = var.notification_email
  # region - (optional) is a type of string
  region = var.region
  # service_version - (optional) is a type of string
  service_version = var.service_version
  # snapshot_name - (optional) is a type of string
  snapshot_name = var.snapshot_name
  # source_service_name - (optional) is a type of string
  source_service_name = var.source_service_name
  # ssh_public_key - (required) is a type of string
  ssh_public_key = var.ssh_public_key
  # subnet - (optional) is a type of string
  subnet = var.subnet
  # use_identity_service - (optional) is a type of bool
  use_identity_service = var.use_identity_service

  dynamic "backups" {
    for_each = var.backups
    content {
      # auto_generate - (optional) is a type of bool
      auto_generate = backups.value["auto_generate"]
      # cloud_storage_container - (required) is a type of string
      cloud_storage_container = backups.value["cloud_storage_container"]
      # cloud_storage_password - (optional) is a type of string
      cloud_storage_password = backups.value["cloud_storage_password"]
      # cloud_storage_username - (optional) is a type of string
      cloud_storage_username = backups.value["cloud_storage_username"]
      # use_oauth_for_storage - (optional) is a type of bool
      use_oauth_for_storage = backups.value["use_oauth_for_storage"]
    }
  }

  dynamic "load_balancer" {
    for_each = var.load_balancer
    content {
      # load_balancing_policy - (optional) is a type of string
      load_balancing_policy = load_balancer.value["load_balancing_policy"]
      # subnets - (optional) is a type of set of string
      subnets = load_balancer.value["subnets"]
    }
  }

  dynamic "oracle_traffic_director" {
    for_each = var.oracle_traffic_director
    content {
      # high_availability - (optional) is a type of bool
      high_availability = oracle_traffic_director.value["high_availability"]
      # ip_reservations - (optional) is a type of list of string
      ip_reservations = oracle_traffic_director.value["ip_reservations"]
      # load_balancing_policy - (optional) is a type of string
      load_balancing_policy = oracle_traffic_director.value["load_balancing_policy"]
      # shape - (required) is a type of string
      shape = oracle_traffic_director.value["shape"]

      dynamic "admin" {
        for_each = oracle_traffic_director.value.admin
        content {
          # password - (required) is a type of string
          password = admin.value["password"]
          # port - (optional) is a type of number
          port = admin.value["port"]
          # username - (required) is a type of string
          username = admin.value["username"]
        }
      }

      dynamic "listener" {
        for_each = oracle_traffic_director.value.listener
        content {
          # port - (optional) is a type of number
          port = listener.value["port"]
          # privileged_port - (optional) is a type of number
          privileged_port = listener.value["privileged_port"]
          # privileged_secured_port - (optional) is a type of number
          privileged_secured_port = listener.value["privileged_secured_port"]
          # secured_port - (optional) is a type of number
          secured_port = listener.value["secured_port"]
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

  dynamic "weblogic_server" {
    for_each = var.weblogic_server
    content {
      # backup_volume_size - (optional) is a type of string
      backup_volume_size = weblogic_server.value["backup_volume_size"]
      # cluster_name - (optional) is a type of string
      cluster_name = weblogic_server.value["cluster_name"]
      # connect_string - (optional) is a type of string
      connect_string = weblogic_server.value["connect_string"]
      # ip_reservations - (optional) is a type of list of string
      ip_reservations = weblogic_server.value["ip_reservations"]
      # middleware_volume_size - (optional) is a type of string
      middleware_volume_size = weblogic_server.value["middleware_volume_size"]
      # shape - (required) is a type of string
      shape = weblogic_server.value["shape"]
      # upper_stack_product_name - (optional) is a type of string
      upper_stack_product_name = weblogic_server.value["upper_stack_product_name"]

      dynamic "admin" {
        for_each = weblogic_server.value.admin
        content {
          # password - (required) is a type of string
          password = admin.value["password"]
          # port - (optional) is a type of number
          port = admin.value["port"]
          # secured_port - (optional) is a type of number
          secured_port = admin.value["secured_port"]
          # username - (required) is a type of string
          username = admin.value["username"]
        }
      }

      dynamic "application_database" {
        for_each = weblogic_server.value.application_database
        content {
          # name - (required) is a type of string
          name = application_database.value["name"]
          # password - (required) is a type of string
          password = application_database.value["password"]
          # pdb_name - (optional) is a type of string
          pdb_name = application_database.value["pdb_name"]
          # username - (required) is a type of string
          username = application_database.value["username"]
        }
      }

      dynamic "cluster" {
        for_each = weblogic_server.value.cluster
        content {
          # name - (required) is a type of string
          name = cluster.value["name"]
          # path_prefixes - (optional) is a type of set of string
          path_prefixes = cluster.value["path_prefixes"]
          # server_count - (optional) is a type of number
          server_count = cluster.value["server_count"]
          # servers_per_node - (optional) is a type of number
          servers_per_node = cluster.value["servers_per_node"]
          # shape - (optional) is a type of string
          shape = cluster.value["shape"]
          # type - (required) is a type of string
          type = cluster.value["type"]
        }
      }

      dynamic "database" {
        for_each = weblogic_server.value.database
        content {
          # name - (optional) is a type of string
          name = database.value["name"]
          # password - (required) is a type of string
          password = database.value["password"]
          # pdb_name - (optional) is a type of string
          pdb_name = database.value["pdb_name"]
          # username - (required) is a type of string
          username = database.value["username"]
        }
      }

      dynamic "domain" {
        for_each = weblogic_server.value.domain
        content {
          # mode - (optional) is a type of string
          mode = domain.value["mode"]
          # name - (optional) is a type of string
          name = domain.value["name"]
          # partition_count - (optional) is a type of number
          partition_count = domain.value["partition_count"]
          # volume_size - (optional) is a type of string
          volume_size = domain.value["volume_size"]
        }
      }

      dynamic "managed_servers" {
        for_each = weblogic_server.value.managed_servers
        content {
          # initial_heap_size - (optional) is a type of number
          initial_heap_size = managed_servers.value["initial_heap_size"]
          # initial_permanent_generation - (optional) is a type of number
          initial_permanent_generation = managed_servers.value["initial_permanent_generation"]
          # jvm_args - (optional) is a type of string
          jvm_args = managed_servers.value["jvm_args"]
          # max_heap_size - (optional) is a type of number
          max_heap_size = managed_servers.value["max_heap_size"]
          # max_permanent_generation - (optional) is a type of number
          max_permanent_generation = managed_servers.value["max_permanent_generation"]
          # overwrite_jvm_args - (optional) is a type of bool
          overwrite_jvm_args = managed_servers.value["overwrite_jvm_args"]
          # server_count - (optional) is a type of number
          server_count = managed_servers.value["server_count"]
        }
      }

      dynamic "node_manager" {
        for_each = weblogic_server.value.node_manager
        content {
          # password - (optional) is a type of string
          password = node_manager.value["password"]
          # port - (optional) is a type of number
          port = node_manager.value["port"]
          # username - (optional) is a type of string
          username = node_manager.value["username"]
        }
      }

      dynamic "ports" {
        for_each = weblogic_server.value.ports
        content {
          # content_port - (optional) is a type of number
          content_port = ports.value["content_port"]
          # deployment_channel_port - (optional) is a type of number
          deployment_channel_port = ports.value["deployment_channel_port"]
          # privileged_content_port - (optional) is a type of number
          privileged_content_port = ports.value["privileged_content_port"]
          # privileged_secured_content_port - (optional) is a type of number
          privileged_secured_content_port = ports.value["privileged_secured_content_port"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = oraclepaas_java_service_instance.this.description
}

output "id" {
  description = "returns a string"
  value       = oraclepaas_java_service_instance.this.id
}

output "region" {
  description = "returns a string"
  value       = oraclepaas_java_service_instance.this.region
}

output "status" {
  description = "returns a string"
  value       = oraclepaas_java_service_instance.this.status
}

output "this" {
  value = oraclepaas_java_service_instance.this
}
```

[top](#index)