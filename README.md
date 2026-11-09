# SWYNEX Monitoring and Cost Awareness
## Internship Task 3 — CloudTask

**Application:** CloudTask static website  
**Hosting:** Netlify  
**Production URL:** https://sensational-cucurucho-1bf736.netlify.app/  
**Source repository:** https://github.com/kiruba-1902/SWYNEX-Basic-Cloud-Deployment  
**Production branch:** `main`

## 1. Basic monitoring

### Public availability and functionality
1. Open the production URL in a private/incognito browser window.
2. Confirm that the site loads over HTTPS.
3. Test adding, completing and deleting a task.
4. Refresh the same browser and confirm tasks saved in that browser remain.
5. Record the date, time, result and any issue in the monitoring log.

This is a manual availability and smoke test, not continuous uptime monitoring.

### Netlify deployment status and logs
1. Sign in to Netlify and open the CloudTask project.
2. Select **Deploys**.
3. Check that the latest production deployment is **Published**.
4. Open the deployment details and inspect the deploy log if a deployment fails.
5. Check the deploy file browser for `index.html`, `style.css` and `script.js`.

### Usage monitoring
Review the Netlify project's Observability/Analytics area and account billing or usage page. Check the metrics and limits available on your plan, including requests, bandwidth and build usage. Dashboard labels and available metrics can vary by plan.

### Monitoring log template

| Date/time (IST) | Check | Result | Notes/action |
|---|---|---|---|
| YYYY-MM-DD HH:MM | Public URL / HTTPS | Pass / Fail | |
| YYYY-MM-DD HH:MM | Application smoke test | Pass / Fail | |
| YYYY-MM-DD HH:MM | Latest production deploy | Published / Failed | |
| YYYY-MM-DD HH:MM | Deploy log | Reviewed | |
| YYYY-MM-DD HH:MM | Usage and billing | Reviewed | |

## 2. Simple alerting idea

- **Deployment alert:** Enable Netlify notifications for failed deployments using the notification settings available in the account.
- **Availability alert:** Optionally configure an external uptime monitor (for example, UptimeRobot) to check the public HTTPS URL and send an email if it becomes unavailable.

### Response procedure
1. Verify the alert by opening the website.
2. Check Netlify's latest production deployment and deploy log.
3. If a recent deployment caused the issue, use Netlify's deploy controls to restore the last known-good deployment.
4. Recheck the public site and record the incident and resolution.

**Important:** These are proposed alerting steps. Do not claim alerts are active until they have been configured and tested.

## 3. Cost-awareness checklist

- [ ] Review the current Netlify plan, billing page and usage limits.
- [ ] Review bandwidth, requests and build usage periodically.
- [ ] Avoid unnecessary builds and repeated deployments.
- [ ] Compress images and remove unused assets.
- [ ] Review paid add-ons before enabling them.
- [ ] Keep the site static unless backend functionality is genuinely needed.
- [ ] Schedule a regular usage and billing review.

CloudTask is a static site and currently does not use serverless functions, a managed database or a paid backend service. Actual charges depend on the current account plan, usage and enabled add-ons; consult the Netlify account for current pricing and limits.

## 4. Security and access-control checklist

- [ ] Confirm the production site uses HTTPS.
- [ ] Never commit passwords, API keys, access tokens or private credentials to GitHub.
- [ ] Store any future secrets in hosting environment-variable settings, not source files.
- [ ] Grant GitHub/Netlify integrations and collaborators only the access they need.
- [ ] Enable multi-factor authentication on GitHub.
- [ ] Review changes before deploying to the production branch.
- [ ] Avoid collecting sensitive personal information in this demo.
- [ ] Review connected accounts and authorized users periodically.
- [ ] Understand that tasks are stored in each visitor's browser Local Storage, not a central database.

## 5. Architecture and limitations

Visitor browser → HTTPS → Netlify-hosted static HTML/CSS/JavaScript → Browser Local Storage.

Netlify deploy logs show build and publishing activity; they are not application-server logs. Browser-side errors can be inspected with browser developer tools. The application has no server-side database or API.

## 6. Evidence screenshots to add

Create an `evidence/` folder and add genuine screenshots:
1. `netlify-deploy-success.png` — production deployment marked Published.
2. `netlify-deploy-log.png` — completed deployment stages.
3. `netlify-usage-overview.png` — usage/observability screen, if available.
4. `live-site-https.png` — CloudTask opened at its public HTTPS URL.
5. `alert-settings.png` — only if notifications or uptime monitoring were actually configured.

Do not fabricate evidence or state that optional alerts are active if they are only proposed.

## Conclusion

CloudTask monitoring uses a public HTTPS check, functional smoke testing, Netlify production deployment status and deployment-log review. Failed-deployment notifications and an optional uptime monitor provide a simple alerting approach. Regular usage reviews, minimal hosting features, HTTPS, protected credentials and restricted account access support cost and security awareness.

**Prepared for:** SWYNEX Internship — Task 3
