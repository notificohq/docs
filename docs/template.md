# Template

Templates are used to transform machine-readable event into a human-readable message, sent to a recipient.
We use [minijinja](https://github.com/mitsuhiko/minijinja) library for rendering templates.

A template consists of several fields, that are transformed using a templating engine (e.g., minijinja).
The list of fields, needed for a specific template is determined by a channel.

## Using Templates in Pipelines
Once the templates are defined, you can reference them in your pipelines by specifying the template names in `templates.load` step.

### Example:

```json
{
  "step": "templates.load",
  "templates": ["template1", "template2"]
}
```

This step will render two templates, which will result in two messages.
