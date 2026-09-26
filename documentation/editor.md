# SharedComponentTemplate resource plugin

Registers the `SharedComponentTemplate` pipeline type (icon + type GUID). There is no
compiler and no standalone editor binary — assets are authored from the scene editor.

## Layout

| Path | Role |
|---|---|
| `Plugin.config/resource_pipeline.config.txt` | TypeName, TypeGUID, icon |
| `icon.png` | Resource browser icon |
| `documentation/editor.md` | This file |

## Runtime / schema

`xecs::shared_component_template` in xECSV2 owns the descriptor property object and
`type_guid_v` (string hash of `"SharedComponentTemplate"`). Keep
`PipelinePlugin/TypeGUID/Value` in sync with that constant.

## Editor (V1)

Save-as-template from a SHARE header and drop-to-instantiate live in
`plugins/xscene.plugin` so they can use scene commands and the entity inspector.
This plugin only registers the resource type so descriptors and the asset browser
recognize it.
