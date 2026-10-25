# Detection Rules

Started this to expand my skill set to detection engineering.

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
| type | `query` (single-event KQL/ES\|QL/etc.), `sequence` (multi-event EQL/correlation), `threshold` (count-based correlation) |
| slug | short descriptive name |

## Current rules

| Folder | Title | Type | Severity |
|---|---|---|---|
| `windows_query_encoded_commands` | Windows Encoded Commands | query | low |
| `windows_query_suspicious_scheduled_task_powershell` | Suspicious Scheduled Task PowerShell Payload | query | medium |
| `windows_sequence_nightmare_eclipse_shieldbreak` | Nightmare Eclipse ShieldBreak | sequence | critical |
| `windows_query_qilin_linked_connections` | Qilin Enabled Linked Connection (building block) | query | medium |
| `windows_query_qilin_symlink_evaluation` | Qilin Symlink Evaluation Enabled (building block) | query | medium |
| `windows_query_qilin_maxmpxct` | Qilin MxMap has high value (building block) | query (ES\|QL) | medium |
| `windows_threshold_qilin_staging` | Potential Qilin Staging Activity | threshold | high |

## Re-import into Elastic

In Kibana: **Security → Rules → Import rules**, and select the rule’s `elastic/rule.ndjson`.
