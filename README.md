# email-templates

HTML email templates written in [Liquid](https://liquidjs.com/).

## alert.html

| Variable | Meaning |
|---|---|
| `name` | heading |
| `status` | `✅ Up` turns the accent green; anything else is red |
| `msg` | message line |
| `hostnameOrURL` | link at the bottom |
| `heartbeatJSON.localDateTime`, `heartbeatJSON.timezone` | time row, when present |
| `details` | extra rows, a list of `label` and `value` |
| `source` | footer |

Render it with:

```bash
npx -y liquidjs@10.30.1 -t @alert.html -c @context.json -o mail.html
```
