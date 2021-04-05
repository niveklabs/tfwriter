# rancher2_node_template

[back](../rancher2.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    rancher2 = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "rancher2_node_template" {
  source = "./modules/rancher2/r/rancher2_node_template"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # auth_certificate_authority - (optional) is a type of string
  auth_certificate_authority = null
  # auth_key - (optional) is a type of string
  auth_key = null
  # cloud_credential_id - (optional) is a type of string
  cloud_credential_id = null
  # description - (optional) is a type of string
  description = null
  # driver_id - (optional) is a type of string
  driver_id = null
  # engine_env - (optional) is a type of map of string
  engine_env = {}
  # engine_insecure_registry - (optional) is a type of list of string
  engine_insecure_registry = []
  # engine_install_url - (optional) is a type of string
  engine_install_url = null
  # engine_label - (optional) is a type of map of string
  engine_label = {}
  # engine_opt - (optional) is a type of map of string
  engine_opt = {}
  # engine_registry_mirror - (optional) is a type of list of string
  engine_registry_mirror = []
  # engine_storage_driver - (optional) is a type of string
  engine_storage_driver = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # use_internal_ip_address - (optional) is a type of bool
  use_internal_ip_address = null

  amazonec2_config = [{
    access_key                 = null
    ami                        = null
    block_duration_minutes     = null
    device_name                = null
    encrypt_ebs_volume         = null
    endpoint                   = null
    iam_instance_profile       = null
    insecure_transport         = null
    instance_type              = null
    keypair_name               = null
    kms_key                    = null
    monitoring                 = null
    open_port                  = []
    private_address_only       = null
    region                     = null
    request_spot_instance      = null
    retries                    = null
    root_size                  = null
    secret_key                 = null
    security_group             = []
    security_group_readonly    = null
    session_token              = null
    spot_price                 = null
    ssh_keypath                = null
    ssh_user                   = null
    subnet_id                  = null
    tags                       = null
    use_ebs_optimized_instance = null
    use_private_address        = null
    userdata                   = null
    volume_type                = null
    vpc_id                     = null
    zone                       = null
  }]

  azure_config = [{
    availability_set    = null
    client_id           = null
    client_secret       = null
    custom_data         = null
    disk_size           = null
    dns                 = null
    docker_port         = null
    environment         = null
    fault_domain_count  = null
    image               = null
    location            = null
    managed_disks       = null
    no_public_ip        = null
    nsg                 = null
    open_port           = []
    private_ip_address  = null
    resource_group      = null
    size                = null
    ssh_user            = null
    static_public_ip    = null
    storage_type        = null
    subnet              = null
    subnet_prefix       = null
    subscription_id     = null
    update_domain_count = null
    use_private_ip      = null
    vnet                = null
  }]

  digitalocean_config = [{
    access_token        = null
    backups             = null
    image               = null
    ipv6                = null
    monitoring          = null
    private_networking  = null
    region              = null
    size                = null
    ssh_key_fingerprint = null
    ssh_key_path        = null
    ssh_port            = null
    ssh_user            = null
    tags                = null
    userdata            = null
  }]

  hetzner_config = [{
    api_token           = null
    image               = null
    networks            = null
    server_location     = null
    server_type         = null
    use_private_network = null
    userdata            = null
    volumes             = null
  }]

  linode_config = [{
    authorized_users  = null
    create_private_ip = null
    docker_port       = null
    image             = null
    instance_type     = null
    label             = null
    region            = null
    root_pass         = null
    ssh_port          = null
    ssh_user          = null
    stackscript       = null
    stackscript_data  = null
    swap_size         = null
    tags              = null
    token             = null
    ua_prefix         = null
  }]

  node_taints = [{
    effect     = null
    key        = null
    time_added = null
    value      = null
  }]

  opennebula_config = [{
    b2d_size      = null
    cpu           = null
    dev_prefix    = null
    disable_vnc   = null
    disk_resize   = null
    image_id      = null
    image_name    = null
    image_owner   = null
    memory        = null
    network_id    = null
    network_name  = null
    network_owner = null
    password      = null
    ssh_user      = null
    template_id   = null
    template_name = null
    user          = null
    vcpu          = null
    xml_rpc_url   = null
  }]

  openstack_config = [{
    active_timeout                = null
    application_credential_id     = null
    application_credential_name   = null
    application_credential_secret = null
    auth_url                      = null
    availability_zone             = null
    boot_from_volume              = null
    cacert                        = null
    config_drive                  = null
    domain_id                     = null
    domain_name                   = null
    endpoint_type                 = null
    flavor_id                     = null
    flavor_name                   = null
    floating_ip_pool              = null
    image_id                      = null
    image_name                    = null
    insecure                      = null
    ip_version                    = null
    keypair_name                  = null
    net_id                        = null
    net_name                      = null
    nova_network                  = null
    password                      = null
    private_key_file              = null
    region                        = null
    sec_groups                    = null
    ssh_port                      = null
    ssh_user                      = null
    tenant_id                     = null
    tenant_name                   = null
    user_data_file                = null
    username                      = null
    volume_device_path            = null
    volume_id                     = null
    volume_name                   = null
    volume_size                   = null
    volume_type                   = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]

  vsphere_config = [{
    boot2docker_url           = null
    cfgparam                  = []
    clone_from                = null
    cloud_config              = null
    cloudinit                 = null
    content_library           = null
    cpu_count                 = null
    creation_type             = null
    custom_attributes         = []
    datacenter                = null
    datastore                 = null
    datastore_cluster         = null
    disk_size                 = null
    folder                    = null
    hostsystem                = null
    memory_size               = null
    network                   = []
    password                  = null
    pool                      = null
    ssh_password              = null
    ssh_port                  = null
    ssh_user                  = null
    ssh_user_group            = null
    tags                      = []
    username                  = null
    vapp_ip_allocation_policy = null
    vapp_ip_protocol          = null
    vapp_property             = []
    vapp_transport            = null
    vcenter                   = null
    vcenter_port              = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "annotations" {
  description = "(optional) - Annotations of the resource"
  type        = map(string)
  default     = null
}

variable "auth_certificate_authority" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cloud_credential_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "driver_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "engine_env" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "engine_insecure_registry" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "engine_install_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "engine_label" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "engine_opt" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "engine_registry_mirror" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "engine_storage_driver" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - Labels of the resource"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "use_internal_ip_address" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "amazonec2_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      access_key                 = string
      ami                        = string
      block_duration_minutes     = string
      device_name                = string
      encrypt_ebs_volume         = bool
      endpoint                   = string
      iam_instance_profile       = string
      insecure_transport         = bool
      instance_type              = string
      keypair_name               = string
      kms_key                    = string
      monitoring                 = bool
      open_port                  = list(string)
      private_address_only       = bool
      region                     = string
      request_spot_instance      = bool
      retries                    = string
      root_size                  = string
      secret_key                 = string
      security_group             = list(string)
      security_group_readonly    = bool
      session_token              = string
      spot_price                 = string
      ssh_keypath                = string
      ssh_user                   = string
      subnet_id                  = string
      tags                       = string
      use_ebs_optimized_instance = bool
      use_private_address        = bool
      userdata                   = string
      volume_type                = string
      vpc_id                     = string
      zone                       = string
    }
  ))
  default = []
}

variable "azure_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      availability_set    = string
      client_id           = string
      client_secret       = string
      custom_data         = string
      disk_size           = string
      dns                 = string
      docker_port         = string
      environment         = string
      fault_domain_count  = string
      image               = string
      location            = string
      managed_disks       = bool
      no_public_ip        = bool
      nsg                 = string
      open_port           = list(string)
      private_ip_address  = string
      resource_group      = string
      size                = string
      ssh_user            = string
      static_public_ip    = bool
      storage_type        = string
      subnet              = string
      subnet_prefix       = string
      subscription_id     = string
      update_domain_count = string
      use_private_ip      = bool
      vnet                = string
    }
  ))
  default = []
}

variable "digitalocean_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      access_token        = string
      backups             = bool
      image               = string
      ipv6                = bool
      monitoring          = bool
      private_networking  = bool
      region              = string
      size                = string
      ssh_key_fingerprint = string
      ssh_key_path        = string
      ssh_port            = string
      ssh_user            = string
      tags                = string
      userdata            = string
    }
  ))
  default = []
}

variable "hetzner_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      api_token           = string
      image               = string
      networks            = string
      server_location     = string
      server_type         = string
      use_private_network = bool
      userdata            = string
      volumes             = string
    }
  ))
  default = []
}

variable "linode_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      authorized_users  = string
      create_private_ip = bool
      docker_port       = string
      image             = string
      instance_type     = string
      label             = string
      region            = string
      root_pass         = string
      ssh_port          = string
      ssh_user          = string
      stackscript       = string
      stackscript_data  = string
      swap_size         = string
      tags              = string
      token             = string
      ua_prefix         = string
    }
  ))
  default = []
}

variable "node_taints" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      effect     = string
      key        = string
      time_added = string
      value      = string
    }
  ))
  default = []
}

variable "opennebula_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      b2d_size      = string
      cpu           = string
      dev_prefix    = string
      disable_vnc   = bool
      disk_resize   = string
      image_id      = string
      image_name    = string
      image_owner   = string
      memory        = string
      network_id    = string
      network_name  = string
      network_owner = string
      password      = string
      ssh_user      = string
      template_id   = string
      template_name = string
      user          = string
      vcpu          = string
      xml_rpc_url   = string
    }
  ))
  default = []
}

variable "openstack_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      active_timeout                = string
      application_credential_id     = string
      application_credential_name   = string
      application_credential_secret = string
      auth_url                      = string
      availability_zone             = string
      boot_from_volume              = bool
      cacert                        = string
      config_drive                  = bool
      domain_id                     = string
      domain_name                   = string
      endpoint_type                 = string
      flavor_id                     = string
      flavor_name                   = string
      floating_ip_pool              = string
      image_id                      = string
      image_name                    = string
      insecure                      = bool
      ip_version                    = string
      keypair_name                  = string
      net_id                        = string
      net_name                      = string
      nova_network                  = bool
      password                      = string
      private_key_file              = string
      region                        = string
      sec_groups                    = string
      ssh_port                      = string
      ssh_user                      = string
      tenant_id                     = string
      tenant_name                   = string
      user_data_file                = string
      username                      = string
      volume_device_path            = string
      volume_id                     = string
      volume_name                   = string
      volume_size                   = string
      volume_type                   = string
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

variable "vsphere_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      boot2docker_url           = string
      cfgparam                  = list(string)
      clone_from                = string
      cloud_config              = string
      cloudinit                 = string
      content_library           = string
      cpu_count                 = string
      creation_type             = string
      custom_attributes         = list(string)
      datacenter                = string
      datastore                 = string
      datastore_cluster         = string
      disk_size                 = string
      folder                    = string
      hostsystem                = string
      memory_size               = string
      network                   = list(string)
      password                  = string
      pool                      = string
      ssh_password              = string
      ssh_port                  = string
      ssh_user                  = string
      ssh_user_group            = string
      tags                      = list(string)
      username                  = string
      vapp_ip_allocation_policy = string
      vapp_ip_protocol          = string
      vapp_property             = list(string)
      vapp_transport            = string
      vcenter                   = string
      vcenter_port              = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "rancher2_node_template" "this" {
  annotations                = var.annotations
  auth_certificate_authority = var.auth_certificate_authority
  auth_key                   = var.auth_key
  cloud_credential_id        = var.cloud_credential_id
  description                = var.description
  driver_id                  = var.driver_id
  engine_env                 = var.engine_env
  engine_insecure_registry   = var.engine_insecure_registry
  engine_install_url         = var.engine_install_url
  engine_label               = var.engine_label
  engine_opt                 = var.engine_opt
  engine_registry_mirror     = var.engine_registry_mirror
  engine_storage_driver      = var.engine_storage_driver
  labels                     = var.labels
  name                       = var.name
  use_internal_ip_address    = var.use_internal_ip_address

  dynamic "amazonec2_config" {
    for_each = var.amazonec2_config
    content {
      access_key                 = amazonec2_config.value["access_key"]
      ami                        = amazonec2_config.value["ami"]
      block_duration_minutes     = amazonec2_config.value["block_duration_minutes"]
      device_name                = amazonec2_config.value["device_name"]
      encrypt_ebs_volume         = amazonec2_config.value["encrypt_ebs_volume"]
      endpoint                   = amazonec2_config.value["endpoint"]
      iam_instance_profile       = amazonec2_config.value["iam_instance_profile"]
      insecure_transport         = amazonec2_config.value["insecure_transport"]
      instance_type              = amazonec2_config.value["instance_type"]
      keypair_name               = amazonec2_config.value["keypair_name"]
      kms_key                    = amazonec2_config.value["kms_key"]
      monitoring                 = amazonec2_config.value["monitoring"]
      open_port                  = amazonec2_config.value["open_port"]
      private_address_only       = amazonec2_config.value["private_address_only"]
      region                     = amazonec2_config.value["region"]
      request_spot_instance      = amazonec2_config.value["request_spot_instance"]
      retries                    = amazonec2_config.value["retries"]
      root_size                  = amazonec2_config.value["root_size"]
      secret_key                 = amazonec2_config.value["secret_key"]
      security_group             = amazonec2_config.value["security_group"]
      security_group_readonly    = amazonec2_config.value["security_group_readonly"]
      session_token              = amazonec2_config.value["session_token"]
      spot_price                 = amazonec2_config.value["spot_price"]
      ssh_keypath                = amazonec2_config.value["ssh_keypath"]
      ssh_user                   = amazonec2_config.value["ssh_user"]
      subnet_id                  = amazonec2_config.value["subnet_id"]
      tags                       = amazonec2_config.value["tags"]
      use_ebs_optimized_instance = amazonec2_config.value["use_ebs_optimized_instance"]
      use_private_address        = amazonec2_config.value["use_private_address"]
      userdata                   = amazonec2_config.value["userdata"]
      volume_type                = amazonec2_config.value["volume_type"]
      vpc_id                     = amazonec2_config.value["vpc_id"]
      zone                       = amazonec2_config.value["zone"]
    }
  }

  dynamic "azure_config" {
    for_each = var.azure_config
    content {
      availability_set    = azure_config.value["availability_set"]
      client_id           = azure_config.value["client_id"]
      client_secret       = azure_config.value["client_secret"]
      custom_data         = azure_config.value["custom_data"]
      disk_size           = azure_config.value["disk_size"]
      dns                 = azure_config.value["dns"]
      docker_port         = azure_config.value["docker_port"]
      environment         = azure_config.value["environment"]
      fault_domain_count  = azure_config.value["fault_domain_count"]
      image               = azure_config.value["image"]
      location            = azure_config.value["location"]
      managed_disks       = azure_config.value["managed_disks"]
      no_public_ip        = azure_config.value["no_public_ip"]
      nsg                 = azure_config.value["nsg"]
      open_port           = azure_config.value["open_port"]
      private_ip_address  = azure_config.value["private_ip_address"]
      resource_group      = azure_config.value["resource_group"]
      size                = azure_config.value["size"]
      ssh_user            = azure_config.value["ssh_user"]
      static_public_ip    = azure_config.value["static_public_ip"]
      storage_type        = azure_config.value["storage_type"]
      subnet              = azure_config.value["subnet"]
      subnet_prefix       = azure_config.value["subnet_prefix"]
      subscription_id     = azure_config.value["subscription_id"]
      update_domain_count = azure_config.value["update_domain_count"]
      use_private_ip      = azure_config.value["use_private_ip"]
      vnet                = azure_config.value["vnet"]
    }
  }

  dynamic "digitalocean_config" {
    for_each = var.digitalocean_config
    content {
      access_token        = digitalocean_config.value["access_token"]
      backups             = digitalocean_config.value["backups"]
      image               = digitalocean_config.value["image"]
      ipv6                = digitalocean_config.value["ipv6"]
      monitoring          = digitalocean_config.value["monitoring"]
      private_networking  = digitalocean_config.value["private_networking"]
      region              = digitalocean_config.value["region"]
      size                = digitalocean_config.value["size"]
      ssh_key_fingerprint = digitalocean_config.value["ssh_key_fingerprint"]
      ssh_key_path        = digitalocean_config.value["ssh_key_path"]
      ssh_port            = digitalocean_config.value["ssh_port"]
      ssh_user            = digitalocean_config.value["ssh_user"]
      tags                = digitalocean_config.value["tags"]
      userdata            = digitalocean_config.value["userdata"]
    }
  }

  dynamic "hetzner_config" {
    for_each = var.hetzner_config
    content {
      api_token           = hetzner_config.value["api_token"]
      image               = hetzner_config.value["image"]
      networks            = hetzner_config.value["networks"]
      server_location     = hetzner_config.value["server_location"]
      server_type         = hetzner_config.value["server_type"]
      use_private_network = hetzner_config.value["use_private_network"]
      userdata            = hetzner_config.value["userdata"]
      volumes             = hetzner_config.value["volumes"]
    }
  }

  dynamic "linode_config" {
    for_each = var.linode_config
    content {
      authorized_users  = linode_config.value["authorized_users"]
      create_private_ip = linode_config.value["create_private_ip"]
      docker_port       = linode_config.value["docker_port"]
      image             = linode_config.value["image"]
      instance_type     = linode_config.value["instance_type"]
      label             = linode_config.value["label"]
      region            = linode_config.value["region"]
      root_pass         = linode_config.value["root_pass"]
      ssh_port          = linode_config.value["ssh_port"]
      ssh_user          = linode_config.value["ssh_user"]
      stackscript       = linode_config.value["stackscript"]
      stackscript_data  = linode_config.value["stackscript_data"]
      swap_size         = linode_config.value["swap_size"]
      tags              = linode_config.value["tags"]
      token             = linode_config.value["token"]
      ua_prefix         = linode_config.value["ua_prefix"]
    }
  }

  dynamic "node_taints" {
    for_each = var.node_taints
    content {
      effect     = node_taints.value["effect"]
      key        = node_taints.value["key"]
      time_added = node_taints.value["time_added"]
      value      = node_taints.value["value"]
    }
  }

  dynamic "opennebula_config" {
    for_each = var.opennebula_config
    content {
      b2d_size      = opennebula_config.value["b2d_size"]
      cpu           = opennebula_config.value["cpu"]
      dev_prefix    = opennebula_config.value["dev_prefix"]
      disable_vnc   = opennebula_config.value["disable_vnc"]
      disk_resize   = opennebula_config.value["disk_resize"]
      image_id      = opennebula_config.value["image_id"]
      image_name    = opennebula_config.value["image_name"]
      image_owner   = opennebula_config.value["image_owner"]
      memory        = opennebula_config.value["memory"]
      network_id    = opennebula_config.value["network_id"]
      network_name  = opennebula_config.value["network_name"]
      network_owner = opennebula_config.value["network_owner"]
      password      = opennebula_config.value["password"]
      ssh_user      = opennebula_config.value["ssh_user"]
      template_id   = opennebula_config.value["template_id"]
      template_name = opennebula_config.value["template_name"]
      user          = opennebula_config.value["user"]
      vcpu          = opennebula_config.value["vcpu"]
      xml_rpc_url   = opennebula_config.value["xml_rpc_url"]
    }
  }

  dynamic "openstack_config" {
    for_each = var.openstack_config
    content {
      active_timeout                = openstack_config.value["active_timeout"]
      application_credential_id     = openstack_config.value["application_credential_id"]
      application_credential_name   = openstack_config.value["application_credential_name"]
      application_credential_secret = openstack_config.value["application_credential_secret"]
      auth_url                      = openstack_config.value["auth_url"]
      availability_zone             = openstack_config.value["availability_zone"]
      boot_from_volume              = openstack_config.value["boot_from_volume"]
      cacert                        = openstack_config.value["cacert"]
      config_drive                  = openstack_config.value["config_drive"]
      domain_id                     = openstack_config.value["domain_id"]
      domain_name                   = openstack_config.value["domain_name"]
      endpoint_type                 = openstack_config.value["endpoint_type"]
      flavor_id                     = openstack_config.value["flavor_id"]
      flavor_name                   = openstack_config.value["flavor_name"]
      floating_ip_pool              = openstack_config.value["floating_ip_pool"]
      image_id                      = openstack_config.value["image_id"]
      image_name                    = openstack_config.value["image_name"]
      insecure                      = openstack_config.value["insecure"]
      ip_version                    = openstack_config.value["ip_version"]
      keypair_name                  = openstack_config.value["keypair_name"]
      net_id                        = openstack_config.value["net_id"]
      net_name                      = openstack_config.value["net_name"]
      nova_network                  = openstack_config.value["nova_network"]
      password                      = openstack_config.value["password"]
      private_key_file              = openstack_config.value["private_key_file"]
      region                        = openstack_config.value["region"]
      sec_groups                    = openstack_config.value["sec_groups"]
      ssh_port                      = openstack_config.value["ssh_port"]
      ssh_user                      = openstack_config.value["ssh_user"]
      tenant_id                     = openstack_config.value["tenant_id"]
      tenant_name                   = openstack_config.value["tenant_name"]
      user_data_file                = openstack_config.value["user_data_file"]
      username                      = openstack_config.value["username"]
      volume_device_path            = openstack_config.value["volume_device_path"]
      volume_id                     = openstack_config.value["volume_id"]
      volume_name                   = openstack_config.value["volume_name"]
      volume_size                   = openstack_config.value["volume_size"]
      volume_type                   = openstack_config.value["volume_type"]
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

  dynamic "vsphere_config" {
    for_each = var.vsphere_config
    content {
      boot2docker_url           = vsphere_config.value["boot2docker_url"]
      cfgparam                  = vsphere_config.value["cfgparam"]
      clone_from                = vsphere_config.value["clone_from"]
      cloud_config              = vsphere_config.value["cloud_config"]
      cloudinit                 = vsphere_config.value["cloudinit"]
      content_library           = vsphere_config.value["content_library"]
      cpu_count                 = vsphere_config.value["cpu_count"]
      creation_type             = vsphere_config.value["creation_type"]
      custom_attributes         = vsphere_config.value["custom_attributes"]
      datacenter                = vsphere_config.value["datacenter"]
      datastore                 = vsphere_config.value["datastore"]
      datastore_cluster         = vsphere_config.value["datastore_cluster"]
      disk_size                 = vsphere_config.value["disk_size"]
      folder                    = vsphere_config.value["folder"]
      hostsystem                = vsphere_config.value["hostsystem"]
      memory_size               = vsphere_config.value["memory_size"]
      network                   = vsphere_config.value["network"]
      password                  = vsphere_config.value["password"]
      pool                      = vsphere_config.value["pool"]
      ssh_password              = vsphere_config.value["ssh_password"]
      ssh_port                  = vsphere_config.value["ssh_port"]
      ssh_user                  = vsphere_config.value["ssh_user"]
      ssh_user_group            = vsphere_config.value["ssh_user_group"]
      tags                      = vsphere_config.value["tags"]
      username                  = vsphere_config.value["username"]
      vapp_ip_allocation_policy = vsphere_config.value["vapp_ip_allocation_policy"]
      vapp_ip_protocol          = vsphere_config.value["vapp_ip_protocol"]
      vapp_property             = vsphere_config.value["vapp_property"]
      vapp_transport            = vsphere_config.value["vapp_transport"]
      vcenter                   = vsphere_config.value["vcenter"]
      vcenter_port              = vsphere_config.value["vcenter_port"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = rancher2_node_template.this.annotations
}

output "driver" {
  description = "returns a string"
  value       = rancher2_node_template.this.driver
}

output "driver_id" {
  description = "returns a string"
  value       = rancher2_node_template.this.driver_id
}

output "id" {
  description = "returns a string"
  value       = rancher2_node_template.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_node_template.this.labels
}

output "this" {
  value = rancher2_node_template.this
}
```

[top](#index)