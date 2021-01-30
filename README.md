# DwilliamsSpinnakerPluginRepository
Plugin repository for Spinnaker plugins by dwilliams.

Add the following to the orca profiles section, or to the `orca-local.yml` file, to enable the SimpleScriptPlugin:

```
spinnaker:
  extensibility:
    plugins:
      DwilliamsSpinnakerPlugins.SimpleScriptPlugin:
        enabled: true
        version: 0.0.2
        extensions:
          dwilliamsSpinnakerPlugins.simpleScriptPlugin:
            enabled: true
    repositories:
      dwilliams-spinnaker-plugins:
        url: https://raw.githubusercontent.com/dwilliams-spinnaker-plugins/DwilliamsSpinnakerPluginRepository/main/repositories.json
```
