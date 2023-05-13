Reproducer for renovate and GitLab 15.11  added support for "inputs":
- https://docs.gitlab.com/ee/ci/yaml/includes.html#define-inputs-for-configuration-added-with-include-beta

Reproducer for:
- https://github.com/renovatebot/renovate/discussions/22113

Clone the repo:
- `git clone https://gist.github.com/glensc/fc15ab8a8df5db16ed71d28b7ca5a39a renovate-discussion-22113`
or
- `git clone https://github.com/glensc/renovate-discussion-22113`

run `renovate glensc/renovate-discussion-22113 --dry-run` or `yarn test` in the cloned repo

```
 WARN: cli config dryRun property has been changed to full
 INFO: Repository started (repository=glensc/renovate-discussion-22113)
       "renovateVersion": "35.81.0"
 WARN: Error extracting GitLab CI dependencies (repository=glensc/renovate-discussion-22113)
       "err": {
         "name": "YAMLException",
         "reason": "expected a single document in the stream, but found more",
         "message": "expected a single document in the stream, but found more",
         "stack": "YAMLException: expected a single document in the stream, but found more\n    at load (/Users/glen/scm/tmp/renovate/renovate-22113/node_modules/js-yaml/lib/loader.js:1722:9)\n    at Object.extractAllPackageFiles (/Users/glen/scm/tmp/renovate/renovate-22113/node_modules/renovate/lib/modules/manager/gitlabci/extract.ts:143:17)\n    at extractAllPackageFiles (/Users/glen/scm/tmp/renovate/renovate-22113/node_modules/renovate/lib/modules/manager/index.ts:50:17)\n    at getManagerPackageFiles (/Users/glen/scm/tmp/renovate/renovate-22113/node_modules/renovate/lib/workers/repository/extract/manager-files.ts:33:29)\n    at /Users/glen/scm/tmp/renovate/renovate-22113/node_modules/renovate/lib/workers/repository/extract/index.ts:59:28\n    at async Promise.all (index 0)\n    at extractAllDependencies (/Users/glen/scm/tmp/renovate/renovate-22113/node_modules/renovate/lib/workers/repository/extract/index.ts:56:26)\n    at extract (/Users/glen/scm/tmp/renovate/renovate-22113/node_modules/renovate/lib/workers/repository/process/extract-update.ts:140:28)\n    at extractDependencies (/Users/glen/scm/tmp/renovate/renovate-22113/node_modules/renovate/lib/workers/repository/process/index.ts:139:26)\n    at Object.renovateRepository (/Users/glen/scm/tmp/renovate/renovate-22113/node_modules/renovate/lib/workers/repository/index.ts:61:9)\n    at attributes.repository (/Users/glen/scm/tmp/renovate/renovate-22113/node_modules/renovate/lib/workers/global/index.ts:184:11)\n    at start (/Users/glen/scm/tmp/renovate/renovate-22113/node_modules/renovate/lib/workers/global/index.ts:169:7)\n    at /Users/glen/scm/tmp/renovate/renovate-22113/node_modules/renovate/lib/renovate.ts:18:22"
       },
       "file": "renovate.gitlab-ci.yml"
 INFO: Dependency extraction complete (repository=glensc/renovate-discussion-22113, baseBranch=main)
       "stats": {
         "managers": {"npm": {"fileCount": 1, "depCount": 1}},
         "total": {"fileCount": 1, "depCount": 1}
       }
 INFO: DRY-RUN: Would ensure Dependency Dashboard (repository=glensc/renovate-discussion-22113)
       "title": "Dependency Dashboard"
 INFO: DRY-RUN: Would save repository cache. (repository=glensc/renovate-discussion-22113)
 INFO: Repository finished (repository=glensc/renovate-discussion-22113)
       "cloned": true,
       "durationMs": 19366
```
