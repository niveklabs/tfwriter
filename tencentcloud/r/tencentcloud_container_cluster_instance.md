# tencentcloud_container_cluster_instance

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_container_cluster_instance" {
  source = "./modules/tencentcloud/r/tencentcloud_container_cluster_instance"

  # bandwidth - (required) is a type of number
  bandwidth = null
  # bandwidth_type - (required) is a type of string
  bandwidth_type = null
  # cluster_id - (required) is a type of string
  cluster_id = null
  # cpu - (optional) is a type of number
  cpu = null
  # cvm_type - (optional) is a type of string
  cvm_type = null
  # docker_graph_path - (optional) is a type of string
  docker_graph_path = null
  # instance_name - (optional) is a type of string
  instance_name = null
  # instance_type - (optional) is a type of string
  instance_type = null
  # is_vpc_gateway - (required) is a type of number
  is_vpc_gateway = null
  # key_id - (optional) is a type of string
  key_id = null
  # mem - (optional) is a type of number
  mem = null
  # mount_target - (optional) is a type of string
  mount_target = null
  # password - (optional) is a type of string
  password = null
  # period - (optional) is a type of number
  period = null
  # require_wan_ip - (optional) is a type of number
  require_wan_ip = null
  # root_size - (required) is a type of number
  root_size = null
  # root_type - (optional) is a type of string
  root_type = null
  # sg_id - (optional) is a type of string
  sg_id = null
  # storage_size - (required) is a type of number
  storage_size = null
  # storage_type - (optional) is a type of string
  storage_type = null
  # subnet_id - (required) is a type of string
  subnet_id = null
  # unschedulable - (optional) is a type of number
  unschedulable = null
  # user_script - (optional) is a type of string
  user_script = null
  # zone_id - (required) is a type of string
  zone_id = null
}
```

[top](#index)

### Variables

```terraform
variable "bandwidth" {
  description = "(required) - The network bandwidth of the node."
  type        = number
}

variable "bandwidth_type" {
  description = "(required) - The network type of the node."
  type        = string
}

variable "cluster_id" {
  description = "(required) - The id of the cluster."
  type        = string
}

variable "cpu" {
  description = "(optional) - The cpu of the node."
  type        = number
  default     = null
}

variable "cvm_type" {
  description = "(optional) - The type of node needed by cvm."
  type        = string
  default     = null
}

variable "docker_graph_path" {
  description = "(optional) - The docker graph path is going to mounted."
  type        = string
  default     = null
}

variable "instance_name" {
  description = "(optional) - The name ot node."
  type        = string
  default     = null
}

variable "instance_type" {
  description = "(optional) - The instance type of the node needed by cvm."
  type        = string
  default     = null
}

variable "is_vpc_gateway" {
  description = "(required) - Describe whether the node enable the gateway capability."
  type        = number
}

variable "key_id" {
  description = "(optional) - The key_id of each node(if using key pair to access)."
  type        = string
  default     = null
}

variable "mem" {
  description = "(optional) - The memory of the node."
  type        = number
  default     = null
}

variable "mount_target" {
  description = "(optional) - The path which volume is going to be mounted."
  type        = string
  default     = null
}

variable "password" {
  description = "(optional) - The password of each node."
  type        = string
  default     = null
}

variable "period" {
  description = "(optional) - The puchase duration of the node needed by cvm."
  type        = number
  default     = null
}

variable "require_wan_ip" {
  description = "(optional) - Indicate whether wan ip is needed."
  type        = number
  default     = null
}

variable "root_size" {
  description = "(required) - The size of the root volume."
  type        = number
}

variable "root_type" {
  description = "(optional) - The type of the root volume. see more from CVM."
  type        = string
  default     = null
}

variable "sg_id" {
  description = "(optional) - The security group id."
  type        = string
  default     = null
}

variable "storage_size" {
  description = "(required) - The size of the data volume."
  type        = number
}

variable "storage_type" {
  description = "(optional) - The type of the data volume. see more from CVM."
  type        = string
  default     = null
}

variable "subnet_id" {
  description = "(required) - The subnet id which the node stays in."
  type        = string
}

variable "unschedulable" {
  description = "(optional) - Determine whether the node will be schedulable. 0 is the default meaning node will be schedulable. 1 for unschedulable."
  type        = number
  default     = null
}

variable "user_script" {
  description = "(optional) - User defined script in a base64-format. The script runs after the kubernetes component is ready on node. see more from CCS api documents."
  type        = string
  default     = null
}

variable "zone_id" {
  description = "(required) - The zone which the node stays in."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_container_cluster_instance" "this" {
  bandwidth         = var.bandwidth
  bandwidth_type    = var.bandwidth_type
  cluster_id        = var.cluster_id
  cpu               = var.cpu
  cvm_type          = var.cvm_type
  docker_graph_path = var.docker_graph_path
  instance_name     = var.instance_name
  instance_type     = var.instance_type
  is_vpc_gateway    = var.is_vpc_gateway
  key_id            = var.key_id
  mem               = var.mem
  mount_target      = var.mount_target
  password          = var.password
  period            = var.period
  require_wan_ip    = var.require_wan_ip
  root_size         = var.root_size
  root_type         = var.root_type
  sg_id             = var.sg_id
  storage_size      = var.storage_size
  storage_type      = var.storage_type
  subnet_id         = var.subnet_id
  unschedulable     = var.unschedulable
  user_script       = var.user_script
  zone_id           = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "abnormal_reason" {
  description = "returns a string"
  value       = tencentcloud_container_cluster_instance.this.abnormal_reason
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_container_cluster_instance.this.id
}

output "instance_id" {
  description = "returns a string"
  value       = tencentcloud_container_cluster_instance.this.instance_id
}

output "is_normal" {
  description = "returns a number"
  value       = tencentcloud_container_cluster_instance.this.is_normal
}

output "lan_ip" {
  description = "returns a string"
  value       = tencentcloud_container_cluster_instance.this.lan_ip
}

output "wan_ip" {
  description = "returns a string"
  value       = tencentcloud_container_cluster_instance.this.wan_ip
}

output "this" {
  value = tencentcloud_container_cluster_instance.this
}
```

[top](#index)