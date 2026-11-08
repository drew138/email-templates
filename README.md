# email-templates

HTML templates for the emails I send myself, written in [Liquid](https://liquidjs.com/) so the
same file renders in Uptime Kuma (which uses liquidjs for SMTP notifications) and in CI.

## alert.html

| Variable | Meaning |
|---|---|
| `name` | heading |
| `status` | `✅ Up` turns the accent green; anything else is red |
| `msg` | message line |
| `hostnameOrURL` | link at the bottom |
| `heartbeatJSON.localDateTime`, `heartbeatJSON.timezone` | time row, when present |
| `details` | extra rows, a list of `label` and `value` |
| `source` | footer, `Uptime Kuma` by default |

Uptime Kuma fills `name`, `status`, `msg`, `hostnameOrURL` and `heartbeatJSON` itself. Elsewhere,
render it with:

```bash
npx -y liquidjs@10.30.1 -t @alert.html -c @context.json -o mail.html
```
