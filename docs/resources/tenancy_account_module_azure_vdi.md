---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "volocloud_tenancy_account_module_azure_vdi Resource - volocloud"
subcategory: ""
description: |-
  Tenancy Account Module Azure VDI resource configuration main schema.
hide:
  - toc
---

# volocloud_tenancy_account_module_azure_vdi (Resource)

Tenancy Account Module Azure VDI resource configuration main schema.



<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `configuration` (Attributes) (Required) Provides configuration required to setup Azure Virtual Desktop VDI solution. (see [below for nested schema](#nestedatt--configuration))
- `name` (String) (Required) Name of the Azure Virtual Desktop environment.
- `volo_tenancy_account_id` (String) (Required) Volocloud Tenancy Account ID.
- `volo_tenancy_id` (String) (Required) Volocloud Tenancy ID.

### Read-Only

- `id` (String) (Computed) ID of the resource computed from the account_id, tenancy_id, tenancy_account_id and tenancy_account_module_azure_vdi_id separated by : .
- `last_updated` (String) (Computed) Timestamp when create/update have ran.
- `volo_account_id` (String) (Computed) Volocloud Account ID associated with this tenancy_account.
- `volo_tenancy_account_module_azure_vdi_id` (String) (Computed) Volocloud Tenancy Account Module Azure VDI ID.

<a id="nestedatt--configuration"></a>
### Nested Schema for `configuration`

Optional:

- `personal` (Attributes) (Optional) Configuration for an AVD Personal Host Pool. Conflicts with `pooled` type. (see [below for nested schema](#nestedatt--configuration--personal))
- `pooled` (Attributes) (Optional) Configuration for an AVD Personal Host Pool. Conflicts with `personal` type. (see [below for nested schema](#nestedatt--configuration--pooled))

<a id="nestedatt--configuration--personal"></a>
### Nested Schema for `configuration.personal`

Required:

- `abbreviation` (String) (Required) This abbreviation will be used to uniquily identify Session Host VMs created by this resource and joined in the same AD.
- `deployment_template` (String) (Required) Provides the deployment template for the host pool, based on which AVD resources are created. Can be one: `marketplace` or `statistical_computing`. Defaults to `marketplace`.
- `number_of_session_hosts` (Number) (Required) How many Session Host VMs should be deployed in the host pool.

Optional:

- `operating_system` (String) (Optional) Windows version to use for the Session Host VMs. Can be one of: `windows_10` or `windows_11`.Defaults to `windows_11`.
- `password_rotation_days` (Number) (Optional) Privides the Session Host VMs local admin password rotation in days. Can be a number between `0` and `365` days. If `0` is provided, the password never rotates. Defaults to `90` days.
- `sku` (String) (Optional) Provide the Session Host VMs SKU to be used for the Host Pool. Can be one of: `Standard_D2ads_v5`, `Standard_D4ads_v5`, `Standard_E2ads_v5` or `Standard_E4ads_v5`. Defaults to `Standard_D2ads_v5`.
- `tags` (Map of String) (Optional) Key-value map of resource tags for all the host pool resources.

Read-Only:

- `ad_join_type` (String) (Optional) Provide the AD that will be used to join the Session Host VMs. Can be one of: `microsoft_entra_domain_services` or `microsoft_entra_id`. Defaults to `microsoft_entra_domain_services`.


<a id="nestedatt--configuration--pooled"></a>
### Nested Schema for `configuration.pooled`

Required:

- `abbreviation` (String) (Required) This abbreviation will be used to uniquily identify Session Host VMs created by this resource and joined in the same AD.
- `deployment_template` (String) (Required) Provides the deployment template for the host pool, based on which AVD resources are created. Can be one: `marketplace` or `statistical_computing`. Defaults to `marketplace`.
- `number_of_session_hosts` (Number) (Required) How many Session Host VMs should be deployed in the host pool.

Optional:

- `operating_system` (String) (Optional) Windows version to use for the Session Host VMs. Can be one of: `windows_10_multi` or `windows_11_multi`.Defaults to `windows_11_multi`.
- `password_rotation_days` (Number) (Optional) Privides the Session Host VMs local admin password rotation in days. Can be a number between `0` and `365` days. If `0` is provided, the password never rotates. Defaults to `90` days.
- `sku` (String) (Optional) Provide the Session Host VMs SKU to be used for the Host Pool. Can be one of: `Standard_D2ads_v5`, `Standard_D4ads_v5`, `Standard_E2ads_v5` or `Standard_E4ads_v5`. Defaults to `Standard_D2ads_v5`.
- `tags` (Map of String) (Optional) Key-value map of resource tags for all the host pool resources.

Read-Only:

- `ad_join_type` (String) (Optional) Provide the AD that will be used to join the Session Host VMs. Can be one of: `microsoft_entra_domain_services` or `microsoft_entra_id`. Defaults to `microsoft_entra_domain_services`.
