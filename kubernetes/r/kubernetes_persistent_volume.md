# kubernetes_persistent_volume

[back](../kubernetes.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    kubernetes = ">= 2.0.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "kubernetes_persistent_volume" {
  source = "./modules/kubernetes/r/kubernetes_persistent_volume"


  metadata = [{
    annotations      = {}
    generation       = null
    labels           = {}
    name             = null
    resource_version = null
    self_link        = null
    uid              = null
  }]

  spec = [{
    access_modes  = []
    capacity      = {}
    mount_options = []
    node_affinity = [{
      required = [{
        node_selector_term = [{
          match_expressions = [{
            key      = null
            operator = null
            values   = []
          }]
          match_fields = [{
            key      = null
            operator = null
            values   = []
          }]
        }]
      }]
    }]
    persistent_volume_reclaim_policy = null
    persistent_volume_source = [{
      aws_elastic_block_store = [{
        fs_type   = null
        partition = null
        read_only = null
        volume_id = null
      }]
      azure_disk = [{
        caching_mode  = null
        data_disk_uri = null
        disk_name     = null
        fs_type       = null
        kind          = null
        read_only     = null
      }]
      azure_file = [{
        read_only   = null
        secret_name = null
        share_name  = null
      }]
      ceph_fs = [{
        monitors    = []
        path        = null
        read_only   = null
        secret_file = null
        secret_ref = [{
          name      = null
          namespace = null
        }]
        user = null
      }]
      cinder = [{
        fs_type   = null
        read_only = null
        volume_id = null
      }]
      csi = [{
        controller_expand_secret_ref = [{
          name      = null
          namespace = null
        }]
        controller_publish_secret_ref = [{
          name      = null
          namespace = null
        }]
        driver  = null
        fs_type = null
        node_publish_secret_ref = [{
          name      = null
          namespace = null
        }]
        node_stage_secret_ref = [{
          name      = null
          namespace = null
        }]
        read_only         = null
        volume_attributes = {}
        volume_handle     = null
      }]
      fc = [{
        fs_type      = null
        lun          = null
        read_only    = null
        target_ww_ns = []
      }]
      flex_volume = [{
        driver    = null
        fs_type   = null
        options   = {}
        read_only = null
        secret_ref = [{
          name      = null
          namespace = null
        }]
      }]
      flocker = [{
        dataset_name = null
        dataset_uuid = null
      }]
      gce_persistent_disk = [{
        fs_type   = null
        partition = null
        pd_name   = null
        read_only = null
      }]
      glusterfs = [{
        endpoints_name = null
        path           = null
        read_only      = null
      }]
      host_path = [{
        path = null
        type = null
      }]
      iscsi = [{
        fs_type         = null
        iqn             = null
        iscsi_interface = null
        lun             = null
        read_only       = null
        target_portal   = null
      }]
      local = [{
        path = null
      }]
      nfs = [{
        path      = null
        read_only = null
        server    = null
      }]
      photon_persistent_disk = [{
        fs_type = null
        pd_id   = null
      }]
      quobyte = [{
        group     = null
        read_only = null
        registry  = null
        user      = null
        volume    = null
      }]
      rbd = [{
        ceph_monitors = []
        fs_type       = null
        keyring       = null
        rados_user    = null
        rbd_image     = null
        rbd_pool      = null
        read_only     = null
        secret_ref = [{
          name      = null
          namespace = null
        }]
      }]
      vsphere_volume = [{
        fs_type     = null
        volume_path = null
      }]
    }]
    storage_class_name = null
    volume_mode        = null
  }]

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "metadata" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      annotations      = map(string)
      generation       = number
      labels           = map(string)
      name             = string
      resource_version = string
      self_link        = string
      uid              = string
    }
  ))
}

variable "spec" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      access_modes  = set(string)
      capacity      = map(string)
      mount_options = set(string)
      node_affinity = list(object(
        {
          required = list(object(
            {
              node_selector_term = list(object(
                {
                  match_expressions = list(object(
                    {
                      key      = string
                      operator = string
                      values   = set(string)
                    }
                  ))
                  match_fields = list(object(
                    {
                      key      = string
                      operator = string
                      values   = set(string)
                    }
                  ))
                }
              ))
            }
          ))
        }
      ))
      persistent_volume_reclaim_policy = string
      persistent_volume_source = list(object(
        {
          aws_elastic_block_store = list(object(
            {
              fs_type   = string
              partition = number
              read_only = bool
              volume_id = string
            }
          ))
          azure_disk = list(object(
            {
              caching_mode  = string
              data_disk_uri = string
              disk_name     = string
              fs_type       = string
              kind          = string
              read_only     = bool
            }
          ))
          azure_file = list(object(
            {
              read_only   = bool
              secret_name = string
              share_name  = string
            }
          ))
          ceph_fs = list(object(
            {
              monitors    = set(string)
              path        = string
              read_only   = bool
              secret_file = string
              secret_ref = list(object(
                {
                  name      = string
                  namespace = string
                }
              ))
              user = string
            }
          ))
          cinder = list(object(
            {
              fs_type   = string
              read_only = bool
              volume_id = string
            }
          ))
          csi = list(object(
            {
              controller_expand_secret_ref = list(object(
                {
                  name      = string
                  namespace = string
                }
              ))
              controller_publish_secret_ref = list(object(
                {
                  name      = string
                  namespace = string
                }
              ))
              driver  = string
              fs_type = string
              node_publish_secret_ref = list(object(
                {
                  name      = string
                  namespace = string
                }
              ))
              node_stage_secret_ref = list(object(
                {
                  name      = string
                  namespace = string
                }
              ))
              read_only         = bool
              volume_attributes = map(string)
              volume_handle     = string
            }
          ))
          fc = list(object(
            {
              fs_type      = string
              lun          = number
              read_only    = bool
              target_ww_ns = set(string)
            }
          ))
          flex_volume = list(object(
            {
              driver    = string
              fs_type   = string
              options   = map(string)
              read_only = bool
              secret_ref = list(object(
                {
                  name      = string
                  namespace = string
                }
              ))
            }
          ))
          flocker = list(object(
            {
              dataset_name = string
              dataset_uuid = string
            }
          ))
          gce_persistent_disk = list(object(
            {
              fs_type   = string
              partition = number
              pd_name   = string
              read_only = bool
            }
          ))
          glusterfs = list(object(
            {
              endpoints_name = string
              path           = string
              read_only      = bool
            }
          ))
          host_path = list(object(
            {
              path = string
              type = string
            }
          ))
          iscsi = list(object(
            {
              fs_type         = string
              iqn             = string
              iscsi_interface = string
              lun             = number
              read_only       = bool
              target_portal   = string
            }
          ))
          local = list(object(
            {
              path = string
            }
          ))
          nfs = list(object(
            {
              path      = string
              read_only = bool
              server    = string
            }
          ))
          photon_persistent_disk = list(object(
            {
              fs_type = string
              pd_id   = string
            }
          ))
          quobyte = list(object(
            {
              group     = string
              read_only = bool
              registry  = string
              user      = string
              volume    = string
            }
          ))
          rbd = list(object(
            {
              ceph_monitors = set(string)
              fs_type       = string
              keyring       = string
              rados_user    = string
              rbd_image     = string
              rbd_pool      = string
              read_only     = bool
              secret_ref = list(object(
                {
                  name      = string
                  namespace = string
                }
              ))
            }
          ))
          vsphere_volume = list(object(
            {
              fs_type     = string
              volume_path = string
            }
          ))
        }
      ))
      storage_class_name = string
      volume_mode        = string
    }
  ))
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "kubernetes_persistent_volume" "this" {

  dynamic "metadata" {
    for_each = var.metadata
    content {
      # annotations - (optional) is a type of map of string
      annotations = metadata.value["annotations"]
      # labels - (optional) is a type of map of string
      labels = metadata.value["labels"]
      # name - (optional) is a type of string
      name = metadata.value["name"]
    }
  }

  dynamic "spec" {
    for_each = var.spec
    content {
      # access_modes - (required) is a type of set of string
      access_modes = spec.value["access_modes"]
      # capacity - (required) is a type of map of string
      capacity = spec.value["capacity"]
      # mount_options - (optional) is a type of set of string
      mount_options = spec.value["mount_options"]
      # persistent_volume_reclaim_policy - (optional) is a type of string
      persistent_volume_reclaim_policy = spec.value["persistent_volume_reclaim_policy"]
      # storage_class_name - (optional) is a type of string
      storage_class_name = spec.value["storage_class_name"]
      # volume_mode - (optional) is a type of string
      volume_mode = spec.value["volume_mode"]

      dynamic "node_affinity" {
        for_each = spec.value.node_affinity
        content {

          dynamic "required" {
            for_each = node_affinity.value.required
            content {

              dynamic "node_selector_term" {
                for_each = required.value.node_selector_term
                content {

                  dynamic "match_expressions" {
                    for_each = node_selector_term.value.match_expressions
                    content {
                      # key - (required) is a type of string
                      key = match_expressions.value["key"]
                      # operator - (required) is a type of string
                      operator = match_expressions.value["operator"]
                      # values - (optional) is a type of set of string
                      values = match_expressions.value["values"]
                    }
                  }

                  dynamic "match_fields" {
                    for_each = node_selector_term.value.match_fields
                    content {
                      # key - (required) is a type of string
                      key = match_fields.value["key"]
                      # operator - (required) is a type of string
                      operator = match_fields.value["operator"]
                      # values - (optional) is a type of set of string
                      values = match_fields.value["values"]
                    }
                  }

                }
              }

            }
          }

        }
      }

      dynamic "persistent_volume_source" {
        for_each = spec.value.persistent_volume_source
        content {

          dynamic "aws_elastic_block_store" {
            for_each = persistent_volume_source.value.aws_elastic_block_store
            content {
              # fs_type - (optional) is a type of string
              fs_type = aws_elastic_block_store.value["fs_type"]
              # partition - (optional) is a type of number
              partition = aws_elastic_block_store.value["partition"]
              # read_only - (optional) is a type of bool
              read_only = aws_elastic_block_store.value["read_only"]
              # volume_id - (required) is a type of string
              volume_id = aws_elastic_block_store.value["volume_id"]
            }
          }

          dynamic "azure_disk" {
            for_each = persistent_volume_source.value.azure_disk
            content {
              # caching_mode - (required) is a type of string
              caching_mode = azure_disk.value["caching_mode"]
              # data_disk_uri - (required) is a type of string
              data_disk_uri = azure_disk.value["data_disk_uri"]
              # disk_name - (required) is a type of string
              disk_name = azure_disk.value["disk_name"]
              # fs_type - (optional) is a type of string
              fs_type = azure_disk.value["fs_type"]
              # kind - (optional) is a type of string
              kind = azure_disk.value["kind"]
              # read_only - (optional) is a type of bool
              read_only = azure_disk.value["read_only"]
            }
          }

          dynamic "azure_file" {
            for_each = persistent_volume_source.value.azure_file
            content {
              # read_only - (optional) is a type of bool
              read_only = azure_file.value["read_only"]
              # secret_name - (required) is a type of string
              secret_name = azure_file.value["secret_name"]
              # share_name - (required) is a type of string
              share_name = azure_file.value["share_name"]
            }
          }

          dynamic "ceph_fs" {
            for_each = persistent_volume_source.value.ceph_fs
            content {
              # monitors - (required) is a type of set of string
              monitors = ceph_fs.value["monitors"]
              # path - (optional) is a type of string
              path = ceph_fs.value["path"]
              # read_only - (optional) is a type of bool
              read_only = ceph_fs.value["read_only"]
              # secret_file - (optional) is a type of string
              secret_file = ceph_fs.value["secret_file"]
              # user - (optional) is a type of string
              user = ceph_fs.value["user"]

              dynamic "secret_ref" {
                for_each = ceph_fs.value.secret_ref
                content {
                  # name - (optional) is a type of string
                  name = secret_ref.value["name"]
                  # namespace - (optional) is a type of string
                  namespace = secret_ref.value["namespace"]
                }
              }

            }
          }

          dynamic "cinder" {
            for_each = persistent_volume_source.value.cinder
            content {
              # fs_type - (optional) is a type of string
              fs_type = cinder.value["fs_type"]
              # read_only - (optional) is a type of bool
              read_only = cinder.value["read_only"]
              # volume_id - (required) is a type of string
              volume_id = cinder.value["volume_id"]
            }
          }

          dynamic "csi" {
            for_each = persistent_volume_source.value.csi
            content {
              # driver - (required) is a type of string
              driver = csi.value["driver"]
              # fs_type - (optional) is a type of string
              fs_type = csi.value["fs_type"]
              # read_only - (optional) is a type of bool
              read_only = csi.value["read_only"]
              # volume_attributes - (optional) is a type of map of string
              volume_attributes = csi.value["volume_attributes"]
              # volume_handle - (required) is a type of string
              volume_handle = csi.value["volume_handle"]

              dynamic "controller_expand_secret_ref" {
                for_each = csi.value.controller_expand_secret_ref
                content {
                  # name - (optional) is a type of string
                  name = controller_expand_secret_ref.value["name"]
                  # namespace - (optional) is a type of string
                  namespace = controller_expand_secret_ref.value["namespace"]
                }
              }

              dynamic "controller_publish_secret_ref" {
                for_each = csi.value.controller_publish_secret_ref
                content {
                  # name - (optional) is a type of string
                  name = controller_publish_secret_ref.value["name"]
                  # namespace - (optional) is a type of string
                  namespace = controller_publish_secret_ref.value["namespace"]
                }
              }

              dynamic "node_publish_secret_ref" {
                for_each = csi.value.node_publish_secret_ref
                content {
                  # name - (optional) is a type of string
                  name = node_publish_secret_ref.value["name"]
                  # namespace - (optional) is a type of string
                  namespace = node_publish_secret_ref.value["namespace"]
                }
              }

              dynamic "node_stage_secret_ref" {
                for_each = csi.value.node_stage_secret_ref
                content {
                  # name - (optional) is a type of string
                  name = node_stage_secret_ref.value["name"]
                  # namespace - (optional) is a type of string
                  namespace = node_stage_secret_ref.value["namespace"]
                }
              }

            }
          }

          dynamic "fc" {
            for_each = persistent_volume_source.value.fc
            content {
              # fs_type - (optional) is a type of string
              fs_type = fc.value["fs_type"]
              # lun - (required) is a type of number
              lun = fc.value["lun"]
              # read_only - (optional) is a type of bool
              read_only = fc.value["read_only"]
              # target_ww_ns - (required) is a type of set of string
              target_ww_ns = fc.value["target_ww_ns"]
            }
          }

          dynamic "flex_volume" {
            for_each = persistent_volume_source.value.flex_volume
            content {
              # driver - (required) is a type of string
              driver = flex_volume.value["driver"]
              # fs_type - (optional) is a type of string
              fs_type = flex_volume.value["fs_type"]
              # options - (optional) is a type of map of string
              options = flex_volume.value["options"]
              # read_only - (optional) is a type of bool
              read_only = flex_volume.value["read_only"]

              dynamic "secret_ref" {
                for_each = flex_volume.value.secret_ref
                content {
                  # name - (optional) is a type of string
                  name = secret_ref.value["name"]
                  # namespace - (optional) is a type of string
                  namespace = secret_ref.value["namespace"]
                }
              }

            }
          }

          dynamic "flocker" {
            for_each = persistent_volume_source.value.flocker
            content {
              # dataset_name - (optional) is a type of string
              dataset_name = flocker.value["dataset_name"]
              # dataset_uuid - (optional) is a type of string
              dataset_uuid = flocker.value["dataset_uuid"]
            }
          }

          dynamic "gce_persistent_disk" {
            for_each = persistent_volume_source.value.gce_persistent_disk
            content {
              # fs_type - (optional) is a type of string
              fs_type = gce_persistent_disk.value["fs_type"]
              # partition - (optional) is a type of number
              partition = gce_persistent_disk.value["partition"]
              # pd_name - (required) is a type of string
              pd_name = gce_persistent_disk.value["pd_name"]
              # read_only - (optional) is a type of bool
              read_only = gce_persistent_disk.value["read_only"]
            }
          }

          dynamic "glusterfs" {
            for_each = persistent_volume_source.value.glusterfs
            content {
              # endpoints_name - (required) is a type of string
              endpoints_name = glusterfs.value["endpoints_name"]
              # path - (required) is a type of string
              path = glusterfs.value["path"]
              # read_only - (optional) is a type of bool
              read_only = glusterfs.value["read_only"]
            }
          }

          dynamic "host_path" {
            for_each = persistent_volume_source.value.host_path
            content {
              # path - (optional) is a type of string
              path = host_path.value["path"]
              # type - (optional) is a type of string
              type = host_path.value["type"]
            }
          }

          dynamic "iscsi" {
            for_each = persistent_volume_source.value.iscsi
            content {
              # fs_type - (optional) is a type of string
              fs_type = iscsi.value["fs_type"]
              # iqn - (required) is a type of string
              iqn = iscsi.value["iqn"]
              # iscsi_interface - (optional) is a type of string
              iscsi_interface = iscsi.value["iscsi_interface"]
              # lun - (optional) is a type of number
              lun = iscsi.value["lun"]
              # read_only - (optional) is a type of bool
              read_only = iscsi.value["read_only"]
              # target_portal - (required) is a type of string
              target_portal = iscsi.value["target_portal"]
            }
          }

          dynamic "local" {
            for_each = persistent_volume_source.value.local
            content {
              # path - (optional) is a type of string
              path = local.value["path"]
            }
          }

          dynamic "nfs" {
            for_each = persistent_volume_source.value.nfs
            content {
              # path - (required) is a type of string
              path = nfs.value["path"]
              # read_only - (optional) is a type of bool
              read_only = nfs.value["read_only"]
              # server - (required) is a type of string
              server = nfs.value["server"]
            }
          }

          dynamic "photon_persistent_disk" {
            for_each = persistent_volume_source.value.photon_persistent_disk
            content {
              # fs_type - (optional) is a type of string
              fs_type = photon_persistent_disk.value["fs_type"]
              # pd_id - (required) is a type of string
              pd_id = photon_persistent_disk.value["pd_id"]
            }
          }

          dynamic "quobyte" {
            for_each = persistent_volume_source.value.quobyte
            content {
              # group - (optional) is a type of string
              group = quobyte.value["group"]
              # read_only - (optional) is a type of bool
              read_only = quobyte.value["read_only"]
              # registry - (required) is a type of string
              registry = quobyte.value["registry"]
              # user - (optional) is a type of string
              user = quobyte.value["user"]
              # volume - (required) is a type of string
              volume = quobyte.value["volume"]
            }
          }

          dynamic "rbd" {
            for_each = persistent_volume_source.value.rbd
            content {
              # ceph_monitors - (required) is a type of set of string
              ceph_monitors = rbd.value["ceph_monitors"]
              # fs_type - (optional) is a type of string
              fs_type = rbd.value["fs_type"]
              # keyring - (optional) is a type of string
              keyring = rbd.value["keyring"]
              # rados_user - (optional) is a type of string
              rados_user = rbd.value["rados_user"]
              # rbd_image - (required) is a type of string
              rbd_image = rbd.value["rbd_image"]
              # rbd_pool - (optional) is a type of string
              rbd_pool = rbd.value["rbd_pool"]
              # read_only - (optional) is a type of bool
              read_only = rbd.value["read_only"]

              dynamic "secret_ref" {
                for_each = rbd.value.secret_ref
                content {
                  # name - (optional) is a type of string
                  name = secret_ref.value["name"]
                  # namespace - (optional) is a type of string
                  namespace = secret_ref.value["namespace"]
                }
              }

            }
          }

          dynamic "vsphere_volume" {
            for_each = persistent_volume_source.value.vsphere_volume
            content {
              # fs_type - (optional) is a type of string
              fs_type = vsphere_volume.value["fs_type"]
              # volume_path - (required) is a type of string
              volume_path = vsphere_volume.value["volume_path"]
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
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = kubernetes_persistent_volume.this.id
}

output "this" {
  value = kubernetes_persistent_volume.this
}
```

[top](#index)