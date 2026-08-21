# Detection Rules

Started this to expand my skill set from just analyzing logs to detection engineering.

## Layout

Folder names encode **platform**, **rule type**, then a short slug:

```text
rules/
  <platform>_<type>_<slug>/
    meta.yml
    elastic/
      rule.yml            # readable Elastic rule
      rule.ndjson         # Kibana-importable export
```

| Segment | Examples |
|---|---|
| platform | `windows`, `linux`, `cloud`, `network` |
| type | `query` (single-event KQL/ES\|QL/etc.), `sequence` (multi-event EQL/correlation) |
| slug | short descriptive name |

Examples: `windows_query_encoded_commands`, `windows_sequence_nightmare_eclipse_shieldbreak`.

## Current rules

| Folder | Title | Type | Severity |
|---|---|---|---|
| `windows_query_encoded_commands` | Windows Encoded Commands | query | low |
| `windows_query_suspicious_scheduled_task_powershell` | Suspicious Scheduled Task PowerShell Payload | query | medium |
| `windows_sequence_nightmare_eclipse_shieldbreak` | Nightmare Eclipse ShieldBreak | sequence | critical |

## Re-import into Elastic

In Kibana: **Security → Rules → Import rules**, and select the rule’s `elastic/rule.ndjson`.
