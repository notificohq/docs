# Templates

Templates are used to transform machine-readable event into a human-readable message, sent to a recipient.
We use [minijinja](https://github.com/mitsuhiko/minijinja) library for rendering templates.

A template consists of several fields, that are transformed using a templating engine (e.g., minijinja).
The list of fields, needed for a specific template is determined by a channel.

## File-backed template
Template information is stored in a TOML file, describing template fields.

### Inline template:
```toml
[template]
body = { content = "You have {{ beans_count }} magic beans" }
```

In this example, the `body` field contains an inline template with a content field that includes a variable (`beans_count`).

### Template in a Separate File
To define a template in a separate file, use the file field in the TOML file. The file field contains the path to the template file.

```toml
[template]
body = { file = "body.html" }
```

In this example, the body field contains a template defined in a separate file named body.html.

## Using Templates in Pipelines
Once the templates are defined, you can reference them in your pipelines by specifying the template name in `templates.load` step.
