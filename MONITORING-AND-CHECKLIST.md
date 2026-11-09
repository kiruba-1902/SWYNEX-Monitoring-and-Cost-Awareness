# Monitoring Runbook and Checklist

| Check | Where | Healthy result |
|---|---|---|
| Public website | Incognito browser | Page loads using HTTPS |
| App smoke test | Add, complete and delete tasks | Actions work |
| Production deployment | Netlify → CloudTask → Deploys | Latest production deploy is Published |
| Deployment log | Open latest deploy | Build and deploy stages complete |
| Published files | Netlify deploy file browser | `index.html`, `style.css`, `script.js` present |
| Usage | Netlify usage/observability and billing | Usage reviewed against current plan |

## Alert plan
- Configure Netlify notifications for failed deploys if available.
- Optionally configure an uptime monitor to check https://sensational-cucurucho-1bf736.netlify.app/ and email on failure.
- Verify alert → inspect deploy status/log → restore last known-good deploy if needed → retest → record resolution.

Alerts are proposals until configured and tested.

## Cost checklist
- [ ] Review plan, billing and usage limits.
- [ ] Review bandwidth, requests and build usage.
- [ ] Avoid unnecessary deployments.
- [ ] Keep images/assets small.
- [ ] Avoid unnecessary paid add-ons.

## Security checklist
- [ ] Use HTTPS.
- [ ] Never commit credentials or secrets.
- [ ] Use environment variables for future secrets.
- [ ] Enable GitHub multi-factor authentication.
- [ ] Limit collaborator and integration permissions.
- [ ] Review production changes before deployment.
- [ ] Avoid collecting sensitive information.
- [ ] Remember task data is browser-local.

## Monitoring record
| Date/time (IST) | Check | Pass/fail | Notes |
|---|---|---|---|
| | HTTPS availability | | |
| | Task add/complete/delete | | |
| | Production deploy status | | |
| | Deploy log | | |
| | Usage review | | |

**Scope:** This is a static site. Deploy logs are not application-server logs.
