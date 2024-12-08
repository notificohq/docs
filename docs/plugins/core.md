# Core plugin

## Steps
### Step: `core.set_recipients`

```json
{
  "step": "core.set_recipients",
  "recipients": [
    RECIPIENT,
    RECIPIENT,
    RECIPIENT,
    ...
  ]
}
```

Where `RECIPIENT` is a recipient entity. See [Recipient](../recipient.md) for more info.

## How this works under hood
The Pipeline is forked in the runtime, preserving the current pipeline context.
The forked pipelines start from the following step. This step creates a pipeline for every recipient, resulting in `Recipients` pipelines.
