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
  # annotations - (optional) is a type of map of string
  annotations = var.annotations
  # auth_certificate_authority - (optional) is a type of string
  auth_certificate_authority = var.auth_certificate_authority
  # auth_key - (optional) is a type of string
  auth_key = var.auth_key
  # cloud_credential_id - (optional) is a type of string
  cloud_credential_id = var.cloud_credential_id
  # description - (optional) is a type of string
  description = var.description
  # driver_id - (optional) is a type of string
  driver_id = var.driver_id
  # engine_env - (optional) is a type of map of string
  engine_env = var.engine_env
  # engine_insecure_registry - (optional) is a type of list of string
  engine_insecure_registry = var.engine_insecure_registry
  # engine_install_url - (optional) is a type of string
  engine_install_url = var.engine_install_url
  # engine_label - (optional) is a type of map of string
  engine_label = var.engine_label
  # engine_opt - (optional) is a type of map of string
  engine_opt = var.engine_opt
  # engine_registry_mirror - (optional) is a type of list of string
  engine_registry_mirror = var.engine_registry_mirror
  # engine_storage_driver - (optional) is a type of string
  engine_storage_driver = var.engine_storage_driver
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (required) is a type of string
  name = var.name
  # use_internal_ip_address - (optional) is a type of bool
  use_internal_ip_address = var.use_internal_ip_address

  dynamic "amazonec2_config" {
    for_each = var.amazonec2_config
    content {
      # access_key - (optional) is a type of string
      access_key = amazonec2_config.value["access_key"]
      # ami - (required) is a type of string
      ami = amazonec2_config.value["ami"]
      # block_duration_minutes - (optional) is a type of string
      block_duration_minutes = amazonec2_config.value["block_duration_minutes"]
      # device_name - (optional) is a type of string
      device_name = amazonec2_config.value["device_name"]
      # encrypt_ebs_volume - (optional) is a type of bool
      encrypt_ebs_volume = amazonec2_config.value["encrypt_ebs_volume"]
      # endpoint - (optional) is a type of string
      endpoint = amazonec2_config.value["endpoint"]
      # iam_instance_profile - (optional) is a type of string
      iam_instance_profile = amazonec2_config.value["iam_instance_profile"]
      # insecure_transport - (optional) is a type of bool
      insecure_transport = amazonec2_config.value["insecure_transport"]
      # instance_type - (optional) is a type of string
      instance_type = amazonec2_config.value["instance_type"]
      # keypair_name - (optional) is a type of string
      keypair_name = amazonec2_config.value["keypair_name"]
      # kms_key - (optional) is a type of string
      kms_key = amazonec2_config.value["kms_key"]
      # monitoring - (optional) is a type of bool
      monitoring = amazonec2_config.value["monitoring"]
      # open_port - (optional) is a type of list of string
      open_port = amazonec2_config.value["open_port"]
      # private_address_only - (optional) is a type of bool
      private_address_only = amazonec2_config.value["private_address_only"]
      # region - (required) is a type of string
      region = amazonec2_config.value["region"]
      # request_spot_instance - (optional) is a type of bool
      request_spot_instance = amazonec2_config.value["request_spot_instance"]
      # retries - (optional) is a type of string
      retries = amazonec2_config.value["retries"]
      # root_size - (optional) is a type of string
      root_size = amazonec2_config.value["root_size"]
      # secret_key - (optional) is a type of string
      secret_key = amazonec2_config.value["secret_key"]
      # security_group - (required) is a type of list of string
      security_group = amazonec2_config.value["security_group"]
      # security_group_readonly - (optional) is a type of bool
      security_group_readonly = amazonec2_config.value["security_group_readonly"]
      # session_token - (optional) is a type of string
      session_token = amazonec2_config.value["session_token"]
      # spot_price - (optional) is a type of string
      spot_price = amazonec2_config.value["spot_price"]
      # ssh_keypath - (optional) is a type of string
      ssh_keypath = amazonec2_config.value["ssh_keypath"]
      # ssh_user - (optional) is a type of string
      ssh_user = amazonec2_config.value["ssh_user"]
      # subnet_id - (required) is a type of string
      subnet_id = amazonec2_config.value["subnet_id"]
      # tags - (optional) is a type of string
      tags = amazonec2_config.value["tags"]
      # use_ebs_optimized_instance - (optional) is a type of bool
      use_ebs_optimized_instance = amazonec2_config.value["use_ebs_optimized_instance"]
      # use_private_address - (optional) is a type of bool
      use_private_address = amazonec2_config.value["use_private_address"]
      # userdata - (optional) is a type of string
      userdata = amazonec2_config.value["userdata"]
      # volume_type - (optional) is a type of string
      volume_type = amazonec2_config.value["volume_type"]
      # vpc_id - (required) is a type of string
      vpc_id = amazonec2_config.value["vpc_id"]
      # zone - (required) is a type of string
      zone = amazonec2_config.value["zone"]
    }
  }

  dynamic "azure_config" {
    for_each = var.azure_config
    content {
      # availability_set - (optional) is a type of string
      availability_set = azure_config.value["availability_set"]
      # client_id - (optional) is a type of string
      client_id = azure_config.value["client_id"]
      # client_secret - (optional) is a type of string
      client_secret = azure_config.value["client_secret"]
      # custom_data - (optional) is a type of string
      custom_data = azure_config.value["custom_data"]
      # disk_size - (optional) is a type of string
      disk_size = azure_config.value["disk_size"]
      # dns - (optional) is a type of string
      dns = azure_config.value["dns"]
      # docker_port - (optional) is a type of string
      docker_port = azure_config.value["docker_port"]
      # environment - (optional) is a type of string
      environment = azure_config.value["environment"]
      # fault_domain_count - (optional) is a type of string
      fault_domain_count = azure_config.value["fault_domain_count"]
      # image - (optional) is a type of string
      image = azure_config.value["image"]
      # location - (optional) is a type of string
      location = azure_config.value["location"]
      # managed_disks - (optional) is a type of bool
      managed_disks = azure_config.value["managed_disks"]
      # no_public_ip - (optional) is a type of bool
      no_public_ip = azure_config.value["no_public_ip"]
      # nsg - (optional) is a type of string
      nsg = azure_config.value["nsg"]
      # open_port - (optional) is a type of list of string
      open_port = azure_config.value["open_port"]
      # private_ip_address - (optional) is a type of string
      private_ip_address = azure_config.value["private_ip_address"]
      # resource_group - (optional) is a type of string
      resource_group = azure_config.value["resource_group"]
      # size - (optional) is a type of string
      size = azure_config.value["size"]
      # ssh_user - (optional) is a type of string
      ssh_user = azure_config.value["ssh_user"]
      # static_public_ip - (optional) is a type of bool
      static_public_ip = azure_config.value["static_public_ip"]
      # storage_type - (optional) is a type of string
      storage_type = azure_config.value["storage_type"]
      # subnet - (optional) is a type of string
      subnet = azure_config.value["subnet"]
      # subnet_prefix - (optional) is a type of string
      subnet_prefix = azure_config.value["subnet_prefix"]
      # subscription_id - (optional) is a type of string
      subscription_id = azure_config.value["subscription_id"]
      # update_domain_count - (optional) is a type of string
      update_domain_count = azure_config.value["update_domain_count"]
      # use_private_ip - (optional) is a type of bool
      use_private_ip = azure_config.value["use_private_ip"]
      # vnet - (optional) is a type of string
      vnet = azure_config.value["vnet"]
    }
  }

  dynamic "digitalocean_config" {
    for_each = var.digitalocean_config
    content {
      # access_token - (optional) is a type of string
      access_token = digitalocean_config.value["access_token"]
      # backups - (optional) is a type of bool
      backups = digitalocean_config.value["backups"]
      # image - (optional) is a type of string
      image = digitalocean_config.value["image"]
      # ipv6 - (optional) is a type of bool
      ipv6 = digitalocean_config.value["ipv6"]
      # monitoring - (optional) is a type of bool
      monitoring = digitalocean_config.value["monitoring"]
      # private_networking - (optional) is a type of bool
      private_networking = digitalocean_config.value["private_networking"]
      # region - (optional) is a type of string
      region = digitalocean_config.value["region"]
      # size - (optional) is a type of string
      size = digitalocean_config.value["size"]
      # ssh_key_fingerprint - (optional) is a type of string
      ssh_key_fingerprint = digitalocean_config.value["ssh_key_fingerprint"]
      # ssh_key_path - (optional) is a type of string
      ssh_key_path = digitalocean_config.value["ssh_key_path"]
      # ssh_port - (optional) is a type of string
      ssh_port = digitalocean_config.value["ssh_port"]
      # ssh_user - (optional) is a type of string
      ssh_user = digitalocean_config.value["ssh_user"]
      # tags - (optional) is a type of string
      tags = digitalocean_config.value["tags"]
      # userdata - (optional) is a type of string
      userdata = digitalocean_config.value["userdata"]
    }
  }

  dynamic "hetzner_config" {
    for_each = var.hetzner_config
    content {
      # api_token - (required) is a type of string
      api_token = hetzner_config.value["api_token"]
      # image - (optional) is a type of string
      image = hetzner_config.value["image"]
      # networks - (optional) is a type of string
      networks = hetzner_config.value["networks"]
      # server_location - (optional) is a type of string
      server_location = hetzner_config.value["server_location"]
      # server_type - (optional) is a type of string
      server_type = hetzner_config.value["server_type"]
      # use_private_network - (optional) is a type of bool
      use_private_network = hetzner_config.value["use_private_network"]
      # userdata - (optional) is a type of string
      userdata = hetzner_config.value["userdata"]
      # volumes - (optional) is a type of string
      volumes = hetzner_config.value["volumes"]
    }
  }

  dynamic "linode_config" {
    for_each = var.linode_config
    content {
      # authorized_users - (optional) is a type of string
      authorized_users = linode_config.value["authorized_users"]
      # create_private_ip - (optional) is a type of bool
      create_private_ip = linode_config.value["create_private_ip"]
      # docker_port - (optional) is a type of string
      docker_port = linode_config.value["docker_port"]
      # image - (optional) is a type of string
      image = linode_config.value["image"]
      # instance_type - (optional) is a type of string
      instance_type = linode_config.value["instance_type"]
      # label - (optional) is a type of string
      label = linode_config.value["label"]
      # region - (optional) is a type of string
      region = linode_config.value["region"]
      # root_pass - (optional) is a type of string
      root_pass = linode_config.value["root_pass"]
      # ssh_port - (optional) is a type of string
      ssh_port = linode_config.value["ssh_port"]
      # ssh_user - (optional) is a type of string
      ssh_user = linode_config.value["ssh_user"]
      # stackscript - (optional) is a type of string
      stackscript = linode_config.value["stackscript"]
      # stackscript_data - (optional) is a type of string
      stackscript_data = linode_config.value["stackscript_data"]
      # swap_size - (optional) is a type of string
      swap_size = linode_config.value["swap_size"]
      # tags - (optional) is a type of string
      tags = linode_config.value["tags"]
      # token - (optional) is a type of string
      token = linode_config.value["token"]
      # ua_prefix - (optional) is a type of string
      ua_prefix = linode_config.value["ua_prefix"]
    }
  }

  dynamic "node_taints" {
    for_each = var.node_taints
    content {
      # effect - (optional) is a type of string
      effect = node_taints.value["effect"]
      # key - (required) is a type of string
      key = node_taints.value["key"]
      # time_added - (optional) is a type of string
      time_added = node_taints.value["time_added"]
      # value - (required) is a type of string
      value = node_taints.value["value"]
    }
  }

  dynamic "opennebula_config" {
    for_each = var.opennebula_config
    content {
      # b2d_size - (optional) is a type of string
      b2d_size = opennebula_config.value["b2d_size"]
      # cpu - (optional) is a type of string
      cpu = opennebula_config.value["cpu"]
      # dev_prefix - (optional) is a type of string
      dev_prefix = opennebula_config.value["dev_prefix"]
      # disable_vnc - (optional) is a type of bool
      disable_vnc = opennebula_config.value["disable_vnc"]
      # disk_resize - (optional) is a type of string
      disk_resize = opennebula_config.value["disk_resize"]
      # image_id - (optional) is a type of string
      image_id = opennebula_config.value["image_id"]
      # image_name - (optional) is a type of string
      image_name = opennebula_config.value["image_name"]
      # image_owner - (optional) is a type of string
      image_owner = opennebula_config.value["image_owner"]
      # memory - (optional) is a type of string
      memory = opennebula_config.value["memory"]
      # network_id - (optional) is a type of string
      network_id = opennebula_config.value["network_id"]
      # network_name - (optional) is a type of string
      network_name = opennebula_config.value["network_name"]
      # network_owner - (optional) is a type of string
      network_owner = opennebula_config.value["network_owner"]
      # password - (required) is a type of string
      password = opennebula_config.value["password"]
      # ssh_user - (optional) is a type of string
      ssh_user = opennebula_config.value["ssh_user"]
      # template_id - (optional) is a type of string
      template_id = opennebula_config.value["template_id"]
      # template_name - (optional) is a type of string
      template_name = opennebula_config.value["template_name"]
      # user - (required) is a type of string
      user = opennebula_config.value["user"]
      # vcpu - (optional) is a type of string
      vcpu = opennebula_config.value["vcpu"]
      # xml_rpc_url - (required) is a type of string
      xml_rpc_url = opennebula_config.value["xml_rpc_url"]
    }
  }

  dynamic "openstack_config" {
    for_each = var.openstack_config
    content {
      # active_timeout - (optional) is a type of string
      active_timeout = openstack_config.value["active_timeout"]
      # application_credential_id - (optional) is a type of string
      application_credential_id = openstack_config.value["application_credential_id"]
      # application_credential_name - (optional) is a type of string
      application_credential_name = openstack_config.value["application_credential_name"]
      # application_credential_secret - (optional) is a type of string
      application_credential_secret = openstack_config.value["application_credential_secret"]
      # auth_url - (required) is a type of string
      auth_url = openstack_config.value["auth_url"]
      # availability_zone - (required) is a type of string
      availability_zone = openstack_config.value["availability_zone"]
      # boot_from_volume - (optional) is a type of bool
      boot_from_volume = openstack_config.value["boot_from_volume"]
      # cacert - (optional) is a type of string
      cacert = openstack_config.value["cacert"]
      # config_drive - (optional) is a type of bool
      config_drive = openstack_config.value["config_drive"]
      # domain_id - (optional) is a type of string
      domain_id = openstack_config.value["domain_id"]
      # domain_name - (optional) is a type of string
      domain_name = openstack_config.value["domain_name"]
      # endpoint_type - (optional) is a type of string
      endpoint_type = openstack_config.value["endpoint_type"]
      # flavor_id - (optional) is a type of string
      flavor_id = openstack_config.value["flavor_id"]
      # flavor_name - (optional) is a type of string
      flavor_name = openstack_config.value["flavor_name"]
      # floating_ip_pool - (optional) is a type of string
      floating_ip_pool = openstack_config.value["floating_ip_pool"]
      # image_id - (optional) is a type of string
      image_id = openstack_config.value["image_id"]
      # image_name - (optional) is a type of string
      image_name = openstack_config.value["image_name"]
      # insecure - (optional) is a type of bool
      insecure = openstack_config.value["insecure"]
      # ip_version - (optional) is a type of string
      ip_version = openstack_config.value["ip_version"]
      # keypair_name - (optional) is a type of string
      keypair_name = openstack_config.value["keypair_name"]
      # net_id - (optional) is a type of string
      net_id = openstack_config.value["net_id"]
      # net_name - (optional) is a type of string
      net_name = openstack_config.value["net_name"]
      # nova_network - (optional) is a type of bool
      nova_network = openstack_config.value["nova_network"]
      # password - (optional) is a type of string
      password = openstack_config.value["password"]
      # private_key_file - (optional) is a type of string
      private_key_file = openstack_config.value["private_key_file"]
      # region - (required) is a type of string
      region = openstack_config.value["region"]
      # sec_groups - (optional) is a type of string
      sec_groups = openstack_config.value["sec_groups"]
      # ssh_port - (optional) is a type of string
      ssh_port = openstack_config.value["ssh_port"]
      # ssh_user - (optional) is a type of string
      ssh_user = openstack_config.value["ssh_user"]
      # tenant_id - (optional) is a type of string
      tenant_id = openstack_config.value["tenant_id"]
      # tenant_name - (optional) is a type of string
      tenant_name = openstack_config.value["tenant_name"]
      # user_data_file - (optional) is a type of string
      user_data_file = openstack_config.value["user_data_file"]
      # username - (optional) is a type of string
      username = openstack_config.value["username"]
      # volume_device_path - (optional) is a type of string
      volume_device_path = openstack_config.value["volume_device_path"]
      # volume_id - (optional) is a type of string
      volume_id = openstack_config.value["volume_id"]
      # volume_name - (optional) is a type of string
      volume_name = openstack_config.value["volume_name"]
      # volume_size - (optional) is a type of string
      volume_size = openstack_config.value["volume_size"]
      # volume_type - (optional) is a type of string
      volume_type = openstack_config.value["volume_type"]
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

  dynamic "vsphere_config" {
    for_each = var.vsphere_config
    content {
      # boot2docker_url - (optional) is a type of string
      boot2docker_url = vsphere_config.value["boot2docker_url"]
      # cfgparam - (optional) is a type of list of string
      cfgparam = vsphere_config.value["cfgparam"]
      # clone_from - (optional) is a type of string
      clone_from = vsphere_config.value["clone_from"]
      # cloud_config - (optional) is a type of string
      cloud_config = vsphere_config.value["cloud_config"]
      # cloudinit - (optional) is a type of string
      cloudinit = vsphere_config.value["cloudinit"]
      # content_library - (optional) is a type of string
      content_library = vsphere_config.value["content_library"]
      # cpu_count - (optional) is a type of string
      cpu_count = vsphere_config.value["cpu_count"]
      # creation_type - (optional) is a type of string
      creation_type = vsphere_config.value["creation_type"]
      # custom_attributes - (optional) is a type of list of string
      custom_attributes = vsphere_config.value["custom_attributes"]
      # datacenter - (optional) is a type of string
      datacenter = vsphere_config.value["datacenter"]
      # datastore - (optional) is a type of string
      datastore = vsphere_config.value["datastore"]
      # datastore_cluster - (optional) is a type of string
      datastore_cluster = vsphere_config.value["datastore_cluster"]
      # disk_size - (optional) is a type of string
      disk_size = vsphere_config.value["disk_size"]
      # folder - (optional) is a type of string
      folder = vsphere_config.value["folder"]
      # hostsystem - (optional) is a type of string
      hostsystem = vsphere_config.value["hostsystem"]
      # memory_size - (optional) is a type of string
      memory_size = vsphere_config.value["memory_size"]
      # network - (optional) is a type of list of string
      network = vsphere_config.value["network"]
      # password - (optional) is a type of string
      password = vsphere_config.value["password"]
      # pool - (optional) is a type of string
      pool = vsphere_config.value["pool"]
      # ssh_password - (optional) is a type of string
      ssh_password = vsphere_config.value["ssh_password"]
      # ssh_port - (optional) is a type of string
      ssh_port = vsphere_config.value["ssh_port"]
      # ssh_user - (optional) is a type of string
      ssh_user = vsphere_config.value["ssh_user"]
      # ssh_user_group - (optional) is a type of string
      ssh_user_group = vsphere_config.value["ssh_user_group"]
      # tags - (optional) is a type of list of string
      tags = vsphere_config.value["tags"]
      # username - (optional) is a type of string
      username = vsphere_config.value["username"]
      # vapp_ip_allocation_policy - (optional) is a type of string
      vapp_ip_allocation_policy = vsphere_config.value["vapp_ip_allocation_policy"]
      # vapp_ip_protocol - (optional) is a type of string
      vapp_ip_protocol = vsphere_config.value["vapp_ip_protocol"]
      # vapp_property - (optional) is a type of list of string
      vapp_property = vsphere_config.value["vapp_property"]
      # vapp_transport - (optional) is a type of string
      vapp_transport = vsphere_config.value["vapp_transport"]
      # vcenter - (optional) is a type of string
      vcenter = vsphere_config.value["vcenter"]
      # vcenter_port - (optional) is a type of string
      vcenter_port = vsphere_config.value["vcenter_port"]
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