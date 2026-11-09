# email-templates

HTML email templates written in [Liquid](https://liquidjs.com/).

## alert.html

Every variable except `name`, `status` and `msg` is optional.

| Variable | Meaning |
|---|---|
| `name` | heading, unless `heading` is set |
| `heading` | heading |
| `status` | status row |
| `ok` | `true` makes the accent green, `false` red; without it, a `status` containing `Up` is green |
| `details` | extra rows, a list of `"label: value"` strings |
| `msg` | last row |
| `msg_label` | label of the last row, `message` by default |
| `link` | link at the bottom, `hostnameOrURL` when unset |
| `source` | footer, `Automated alert` by default |
| `source_url`, `source_url_label` | link in the footer |

`details` holds strings because Liquid cannot build a list of objects, so a template that sets
its own variables before this one can still add rows.

Render it with:

```bash
npx -y liquidjs@10.30.1 -t @alert.html -c @context.json -o mail.html
```
