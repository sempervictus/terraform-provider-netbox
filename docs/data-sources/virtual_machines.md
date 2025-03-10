---
# generated by https://github.com/fbreckle/terraform-plugin-docs
page_title: "netbox_virtual_machines Data Source - terraform-provider-netbox"
subcategory: "Virtualization"
description: |-
  
---

# netbox_virtual_machines (Data Source)



## Example Usage

```terraform
// Assumes vmw-cluster-01 exists as a cluster in Netbox
data "netbox_cluster" "vmw_cluster_01" {
  name = "vmw-cluster-01"
}

data "netbox_virtual_machines" "base_vm" {
  name_regex = "myvm-1"
  filter {
    name  = "cluster_id"
    value = data.netbox_cluster.vmw_cluster_01.id
  }
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Optional

- `filter` (Block Set) (see [below for nested schema](#nestedblock--filter))
- `limit` (Number)
- `name_regex` (String)

### Read-Only

- `id` (String) The ID of this resource.
- `vms` (List of Object) (see [below for nested schema](#nestedatt--vms))

<a id="nestedblock--filter"></a>
### Nested Schema for `filter`

Required:

- `name` (String)
- `value` (String)


<a id="nestedatt--vms"></a>
### Nested Schema for `vms`

Read-Only:

- `cluster_id` (Number)
- `comments` (String)
- `config_context` (String)
- `custom_fields` (Map of String)
- `description` (String)
- `device_id` (Number)
- `device_name` (String)
- `disk_size_mb` (Number)
- `local_context_data` (String)
- `memory_mb` (Number)
- `name` (String)
- `platform_id` (Number)
- `platform_slug` (String)
- `primary_ip` (String)
- `primary_ip4` (String)
- `primary_ip6` (String)
- `role_id` (Number)
- `site_id` (Number)
- `status` (String)
- `tag_ids` (List of Number)
- `tenant_id` (Number)
- `vcpus` (Number)
- `vm_id` (Number)


