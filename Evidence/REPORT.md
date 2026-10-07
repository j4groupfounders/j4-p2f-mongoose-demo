# p2-16-mongoose-demo — GREEN
Migration: **Express 4.19.2 → 5.2.1**.
Why meaningful: Express 5 changes route parsing, request/response APIs and promise-error handling; existing authenticated multipart CRUD tests exercise middleware compatibility.
Source: https://github.com/madhums/node-express-mongoose-demo @ 8a134ab5deeef553d6de51d91d4ed8ee378acace.
Preregistered jointly before any upgrade branch: https://github.com/j4groupfounders/j4-upgrades-harness/commit/1ce93ac5399d6b1ee6d45e716efd7da315ec20f2.
Frozen baseline SHA f5263f1db34818e323dbdd84457e345485416ecc; CI https://github.com/j4groupfounders/j4-p2f-mongoose-demo/actions/runs/37663887022.

## Verdict
All five protocol criteria pass.
Project baseline: 11 TAP assertions, 0 unchanged upstream skips. Same named inventory on accepted upgrade; no tests deleted or newly skipped.
Upgrade evidence: https://github.com/j4groupfounders/j4-p2f-mongoose-demo/actions/runs/37664425086.
Seed evidence: https://github.com/j4groupfounders/j4-p2f-mongoose-demo/actions/runs/37664680500.
Independent faults: project tests 4/5; combined 5/5; infrastructure-clean=True. Required >=4/5 combined AND combined miss rate <=half project miss rate. Infrastructure failures never count.
7 workflow runs (cap 12 including screening); 8.55 actual job-minutes. Seed matrix is five fresh-checkout jobs, not one shared mutation loop. Explicit bash -eo pipefail. Public standard Linux Actions only.
Zero human app/test/config edits. No paid APIs/services/model API calls or customer/upstream contact. Codex session token cost unavailable, not represented as zero measured cost.

## Migration and classified behavior
Express major dependency/lock migration; no app/test logic edits.
HTTP classification: Expected-framework / kept: Express 5 removes the hyperlink from the HTML redirect body at /articles/new. Same 302 status/content type/Location. Exact package response.js sources and strict single-route before/after rows in j4-framework-changes.json; no blanket stripping.

## Limits and baseline repairs
See PREREG.md in the harness for fixed surfaces, immutable faults and exact baseline dependency/inventory evidence.
Unauthenticated HTTP characterization only; authenticated CRUD is covered by existing Laravel/Express tests, not a frozen differential replay. No broad route/line-coverage claim. Deliberately measured seeded sample, not production certification.
Laravel 10 destination is historical/EOL; not a supported production recommendation. Petclinic is the app used in p2-08 but a different historical major migration; its J4 source fork is detached from the GitHub network, with full source ancestry preserved.
Express baseline required inert OAuth constructor values and explicit test-mode listener. Laravel baseline required PHP 8.1 for old Carbon and removal of dev-latest advisory meta-package, not runtime/test removal; one unavailable Composer version caused an infrastructure failure. Petclinic's milestone/snapshot repositories removed; style/alternate build/database variants not part of default Maven acceptance.

## Seed outcomes
- 0: blank article title accepted — project=True, HTTP=False, combined=True, infrastructure=False; 
- 1: blank signup email accepted — project=True, HTTP=False, combined=True, infrastructure=False; 
- 2: blank signup name accepted — project=True, HTTP=False, combined=True, infrastructure=False; 
- 3: unauthenticated redirect destination wrong — project=True, HTTP=True, combined=True, infrastructure=False; 
- 4: missing route returns success — project=False, HTTP=True, combined=True, infrastructure=False; 

## All CI runs
- https://github.com/j4groupfounders/j4-p2f-mongoose-demo/actions/runs/37662679875 — j4/p2f-baseline, failure, 0.65 job-min, SHA 63e9c61e43c6ddbb8ef85d33b5f2d5c66b6e0f3e.
- https://github.com/j4groupfounders/j4-p2f-mongoose-demo/actions/runs/37663022699 — j4/p2f-baseline, failure, 2.12 job-min, SHA 6d1371f78c0dd65c2ef4daf3baff8b67ecf6495f.
- https://github.com/j4groupfounders/j4-p2f-mongoose-demo/actions/runs/37663472062 — j4/p2f-baseline, success, 0.67 job-min, SHA 5eee68ddbb5fde7223706e6409f8f63b464af7be.
- https://github.com/j4groupfounders/j4-p2f-mongoose-demo/actions/runs/37663887022 — j4/p2f-baseline, success, 0.67 job-min, SHA f5263f1db34818e323dbdd84457e345485416ecc.
- https://github.com/j4groupfounders/j4-p2f-mongoose-demo/actions/runs/37664104073 — j4/p2f-upgrade, failure, 0.68 job-min, SHA 57380688de76ff8a4d3d4ab2f3e187f90092630e.
- https://github.com/j4groupfounders/j4-p2f-mongoose-demo/actions/runs/37664425086 — j4/p2f-upgrade, success, 0.57 job-min, SHA 268bc5b585300bf6edf1bfa697acf985381a09dd.
- https://github.com/j4groupfounders/j4-p2f-mongoose-demo/actions/runs/37664680500 — j4/p2f-seeds, success, 3.20 job-min, SHA 24e27761d6d9567b708102d40e291a776c682ce8.

## Upgrade diff scope

.github/workflows/j4-p2f.yml |    5 +
 j4-framework-changes.json    |   27 +
 j4_verify.py                 |    7 +-
 package-lock.json            | 1675 +++++++++++++++++++++++++++++-------------
 package.json                 |    2 +-
 5 files changed, 1215 insertions(+), 501 deletions(-)
