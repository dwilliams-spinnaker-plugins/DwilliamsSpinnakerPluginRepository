# DwilliamsSpinnakerPluginRepository
Plugin repository for Spinnaker plugins by dwilliams.

Add the following to the orca profiles section, or to the `orca-local.yml` file, to enable the SimpleScriptPlugin:

```
spinnaker:
  extensibility:
    plugins:
      DwilliamsSpinnakerPlugins.SimpleScriptPlugin:
        enabled: true
        version: 0.0.8
        extensions:
          dwilliamsSpinnakerPlugins.simpleScriptPlugin:
            enabled: true
    repositories:
      dwilliams-spinnaker-plugins:
        url: https://raw.githubusercontent.com/dwilliams-spinnaker-plugins/DwilliamsSpinnakerPluginRepository/main/repositories.json
```

To use the SimpleScriptPlugin before a stage UI is created, add a stage to the pipeline and copy one of the following
JSON snippets to the "Edit Stage as JSON" box:

Script from text in stage:
```
{
  "name": "Simple Script Stage using Text",
  "refId": "1",
  "requisiteStageRefIds": [],
  "script": "print('This is javascript')",
  "skipExpressionEvaluation": false,
  "source": "text",
  "type": "simpleScript"
}
```

Script from artifact (S3 for example):
```
{
  "name": "Simple Script Stage using Artifact",
  "refId": "2",
  "requisiteStageRefIds": [],
  "scriptArtifact": {
    "artifactAccount": "<s3-account>",
    "id": "<uuid4>",
    "reference": "<s3-uri>",
    "type": "s3/object"
  },
  "skipExpressionEvaluation": false,
  "source": "artifact",
  "type": "simpleScript"
}
```
