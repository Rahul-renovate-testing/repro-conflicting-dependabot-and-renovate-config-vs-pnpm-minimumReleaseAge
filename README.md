# Repro for conflicting Dependabot and Renovate config vs pnpm `minimumReleaseAge`

As of 23 Sep 2025, security updates created by Dependabot and Mend Renovate bot are blocked by the pnpm [`minimumReleaseAge` setting](https://pnpm.io/settings#minimumreleaseage).

## Dependabot

Logs from GitHub Actions failing workflow run:

```
Current runner version: '2.328.0'
##[group]Runner Image Provisioner
Hosted Compute Agent
Version: 20250829.383
Commit: 27cb235aab5b0e52e153a26cd86b4742e89dac5d
Build Date: 2025-08-29T13:48:48Z
##[endgroup]
##[group]Operating System
Ubuntu
24.04.3
LTS
##[endgroup]
##[group]Runner Image
Image: ubuntu-24.04
Version: 20250907.24.1
Included Software: https://github.com/actions/runner-images/blob/ubuntu24/20250907.24/images/ubuntu/Ubuntu2404-Readme.md
Image Release: https://github.com/actions/runner-images/releases/tag/ubuntu24%2F20250907.24
##[endgroup]
##[group]GITHUB_TOKEN Permissions
Contents: read
Metadata: read
Packages: read
##[endgroup]
Secret source: None
Prepare workflow directory
Prepare all required actions
Getting action download info
Download action repository 'github/dependabot-action@main' (SHA:ddc330dfecd2dfa9dfa8529aff20dd9b0214f750)
Complete job name: Dependabot
##[group]Run mkdir -p  ./dependabot-job-1107058055-1758642067
[36;1mmkdir -p  ./dependabot-job-1107058055-1758642067[0m
shell: /usr/bin/bash -e {0}
##[endgroup]
##[group]Run github/dependabot-action@main
env:
  DEPENDABOT_DISABLE_CLEANUP: 1
  DEPENDABOT_ENABLE_CONNECTIVITY_CHECK: 0
  GITHUB_TOKEN: ***
  GITHUB_DEPENDABOT_JOB_TOKEN: ***
  GITHUB_DEPENDABOT_CRED_TOKEN: ***
  GITHUB_REGISTRIES_PROXY:
##[endgroup]
🤖 ~ starting update ~
Fetching job details
🤖 ~ Failed to parse GITHUB_REGISTRIES_PROXY environment variable ~
##[group]Pulling updater images
Pulling image ghcr.io/dependabot/dependabot-updater-npm:6229e9fbde84fc7bc67cc57333602896598c2576 (attempt 1)...
Successfully sent metric (dependabot.action.ghcr_image_pull) to remote API endpoint
Pulled image ghcr.io/dependabot/dependabot-updater-npm:6229e9fbde84fc7bc67cc57333602896598c2576
Pulling image ghcr.io/github/dependabot-update-job-proxy/dependabot-update-job-proxy:v2.0.20250826205840@sha256:b0a4c841300510255d6e647e9bcdb939d194bc644dee7962a543f637515b0f23 (attempt 1)...
Successfully sent metric (dependabot.action.ghcr_image_pull) to remote API endpoint
Pulled image ghcr.io/github/dependabot-update-job-proxy/dependabot-update-job-proxy:v2.0.20250826205840@sha256:b0a4c841300510255d6e647e9bcdb939d194bc644dee7962a543f637515b0f23
##[endgroup]
Starting update process
Created proxy container: 6aff0307c386ad050de0a45a909655d55c1b212c2dacb6fd290526c52b795dc1
Created container: e9e6bff4edea67fd37ae84e04659b4e0192a4201e0addcd20ac0b5d1197615e7
  proxy | 2025/09/23 15:41:45 proxy starting, commit: 32f72c93e3b014db177b94dcad54e96d6e241a4a
  proxy | 2025/09/23 15:41:45 Listening (:1080)
Started container e9e6bff4edea67fd37ae84e04659b4e0192a4201e0addcd20ac0b5d1197615e7
updater | Updating certificates in /etc/ssl/certs...
updater | rehash: warning: skipping ca-certificates.crt,it does not contain exactly one certificate or CRL
updater | 1 added, 0 removed; done.
Running hooks in /etc/ca-certificates/update.d...
updater | done.
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Starting job processing
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Job definition: {"job":{"command":"recreate","allowed-updates":[{"dependency-type":"direct","update-type":"all"}],"commit-message-options":{"prefix":null,"prefix-development":null,"include-scope":null},"credentials-metadata":[{"type":"git_source","host":"github.com"}],"debug":null,"dependencies":["next"],"dependency-groups":[],"dependency-group-to-refresh":null,"existing-pull-requests":[[{"dependency-name":"next","dependency-version":"15.4.7","directory":"/","pr-number":1}]],"existing-group-pull-requests":[],"experiments":{"record-ecosystem-versions":true,"record-update-job-unknown-error":true,"proxy-cached":true,"move-job-token":true,"dependency-change-validation":true,"enable-file-parser-python-local":true,"npm-fallback-version-above-v6":true,"lead-security-dependency":true,"enable-record-ecosystem-meta":true,"enable-corepack-for-npm-and-yarn":true,"enable-shared-helpers-command-timeout":true,"enable-dependabot-setting-up-cronjob":true,"enable-engine-version-detection":true,"avoid-duplicate-updates-package-json":true,"allow-refresh-for-existing-pr-dependencies":true,"allow-refresh-group-with-all-dependencies":true,"exclude-local-composer-packages":true,"enable-enhanced-error-details-for-updater":true,"gradle-lockfile-updater":true,"enable-exclude-paths-subdirectory-manifest-files":true,"group-membership-enforcement":true},"ignore-conditions":[],"lockfile-only":false,"max-updater-run-time":2700,"package-manager":"npm_and_yarn","proxy-log-response-body-on-auth-failure":true,"requirements-update-strategy":null,"reject-external-code":false,"security-advisories":[{"dependency-name":"next","patched-versions":[],"unaffected-versions":[],"affected-versions":[">= 15.0.0 <= 15.4.4",">= 0.9.9 < 14.2.31"]},{"dependency-name":"next","patched-versions":[],"unaffected-versions":[],"affected-versions":[">= 15.0.0-canary.0 < 15.4.7",">= 0.9.9 < 14.2.32"]},{"dependency-name":"next","patched-versions":[],"unaffected-versions":[],"affected-versions":[">= 15.0.4-canary.51 < 15.1.8"]},{"dependency-name":"next","patched-versions":[],"unaffected-versions":[],"affected-versions":[">= 15.3.0 < 15.3.3"]},{"dependency-name":"next","patched-versions":[],"unaffected-versions":[],"affected-versions":[">= 15.0.0 < 15.2.2",">= 13.0 < 14.2.30"]},{"dependency-name":"next","patched-versions":[],"unaffected-versions":[],"affected-versions":["< 14.2.24",">= 15.0.0 < 15.1.6"]},{"dependency-name":"next","patched-versions":[],"unaffected-versions":[],"affected-versions":["= 12.3.5","= 13.5.9","= 14.2.25","= 15.2.3"]},{"dependency-name":"next","patched-versions":[],"unaffected-versions":[],"affected-versions":[">= 13.0.0 < 13.5.9",">= 14.0.0 < 14.2.25",">= 15.0.0 < 15.2.3",">= 11.1.4 < 12.3.5"]},{"dependency-name":"next","patched-versions":[],"unaffected-versions":[],"affected-versions":[">= 13.0.0 < 13.5.8",">= 14.0.0 < 14.2.21",">= 15.0.0 < 15.1.2"]},{"dependency-name":"next","patched-versions":[],"unaffected-versions":[],"affected-versions":[">= 9.5.5 < 14.2.15"]},{"dependency-name":"next","patched-versions":[],"unaffected-versions":[],"affected-versions":[">= 10.0.0 < 14.2.7"]},{"dependency-name":"next","patched-versions":[],"unaffected-versions":[],"affected-versions":[">= 13.5.1 < 13.5.7",">= 14.0.0 < 14.2.10"]},{"dependency-name":"next","patched-versions":[],"unaffected-versions":[],"affected-versions":[">= 13.3.1 < 13.5.0"]},{"dependency-name":"next","patched-versions":[],"unaffected-versions":[],"affected-versions":[">= 13.4.0 < 14.1.1"]},{"dependency-name":"next","patched-versions":[],"unaffected-versions":[],"affected-versions":[">= 13.4.0 < 13.5.1"]},{"dependency-name":"next","patched-versions":[],"unaffected-versions":[],"affected-versions":[">= 0.9.9 < 13.4.20-canary.13"]},{"dependency-name":"next","patched-versions":[],"unaffected-versions":[],"affected-versions":["= 12.2.3"]},{"dependency-name":"next","patched-versions":[],"unaffected-versions":[],"affected-versions":[">= 10.0.0 < 12.1.0"]},{"dependency-name":"next","patched-versions":[],"unaffected-versions":[],"affected-versions":[">= 12.0.0 < 12.0.9"]},{"dependency-name":"next","patched-versions":[],"unaffected-versions":[],"affected-versions":[">= 12.0.0 < 12.0.5",">= 0.9.9 < 11.1.3"]},{"dependency-name":"next","patched-versions":[],"unaffected-versions":[],"affected-versions":[">= 10.0.0 < 11.1.1"]},{"dependency-name":"next","patched-versions":[],"unaffected-versions":[],"affected-versions":[">= 0.9.9 < 11.1.0"]},{"dependency-name":"next","patched-versions":[],"unaffected-versions":[],"affected-versions":[">= 9.5.0 < 9.5.4"]},{"dependency-name":"next","patched-versions":[],"unaffected-versions":[],"affected-versions":[">= 0.9.9 < 5.1.0"]},{"dependency-name":"next","patched-versions":[],"unaffected-versions":[],"affected-versions":["< 9.3.2"]},{"dependency-name":"next","patched-versions":[],"unaffected-versions":[],"affected-versions":[">= 7.0.0 < 7.0.2"]},{"dependency-name":"next","patched-versions":[],"unaffected-versions":[],"affected-versions":[">= 1.0.0 < 4.2.3"]},{"dependency-name":"next","patched-versions":[],"unaffected-versions":[],"affected-versions":[">= 1.0.0 < 2.4.1"]}],"security-updates-only":true,"source":{"provider":"github","repo":"karlhorky/repro-conflicting-dependabot-and-renovate-config-vs-pnpm-minimumReleaseAge","branch":null,"api-endpoint":"https://api.github.com/","hostname":"github.com","directories":["/"]},"updating-a-pull-request":true,"update-subdependencies":false,"vendor-dependencies":false,"enable-beta-ecosystems":false,"repo-private":false,"multi-ecosystem-update":false,"exclude-paths":[]}}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1089 with command: {} git config --global credential.helper '!/home/dependabot/common/lib/dependabot/../../bin/git-credential-store-immutable --file /home/dependabot/dependabot-updater/git.store' {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1089 completed with status: pid 1089 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1097 with command: {} git config --global --replace-all url.https://github.com/.insteadOf ssh://git@github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1097 completed with status: pid 1097 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1104 with command: {} git config --global --add url.https://github.com/.insteadOf ssh://git@github.com: {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1104 completed with status: pid 1104 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1111 with command: {} git config --global --add url.https://github.com/.insteadOf git@github.com: {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1111 completed with status: pid 1111 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1118 with command: {} git config --global --add url.https://github.com/.insteadOf git@github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1118 completed with status: pid 1118 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1125 with command: {} git config --global --add url.https://github.com/.insteadOf git://github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1125 completed with status: pid 1125 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1132 with command: {} git config --global --replace-all url.https://github.com/.insteadOf ssh://git@github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1132 completed with status: pid 1132 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.02 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1139 with command: {} git config --global --add url.https://github.com/.insteadOf ssh://git@github.com: {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1139 completed with status: pid 1139 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.01 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1146 with command: {} git config --global --add url.https://github.com/.insteadOf git@github.com: {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1146 completed with status: pid 1146 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1153 with command: {} git config --global --add url.https://github.com/.insteadOf git@github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1153 completed with status: pid 1153 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1160 with command: {} git config --global --add url.https://github.com/.insteadOf git://github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1160 completed with status: pid 1160 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1167 with command: {} git clone --no-tags --depth 1 --recurse-submodules --shallow-submodules https://github.com/karlhorky/repro-conflicting-dependabot-and-renovate-config-vs-pnpm-minimumReleaseAge /home/dependabot/dependabot-updater/repo {}
  proxy | 2025/09/23 15:41:48 [002] GET https://github.com:443/karlhorky/repro-conflicting-dependabot-and-renovate-config-vs-pnpm-minimumReleaseAge/info/refs?service=git-upload-pack
  proxy | 2025/09/23 15:41:48 [002] * authenticating git server request (host: github.com)
  proxy | 2025/09/23 15:41:48 [002] 200 https://github.com:443/karlhorky/repro-conflicting-dependabot-and-renovate-config-vs-pnpm-minimumReleaseAge/info/refs?service=git-upload-pack
  proxy | 2025/09/23 15:41:48 [004] POST https://github.com:443/karlhorky/repro-conflicting-dependabot-and-renovate-config-vs-pnpm-minimumReleaseAge/git-upload-pack
  proxy | 2025/09/23 15:41:48 [004] * authenticating git server request (host: github.com)
  proxy | 2025/09/23 15:41:48 [004] 200 https://github.com:443/karlhorky/repro-conflicting-dependabot-and-renovate-config-vs-pnpm-minimumReleaseAge/git-upload-pack
  proxy | 2025/09/23 15:41:48 [006] POST https://github.com:443/karlhorky/repro-conflicting-dependabot-and-renovate-config-vs-pnpm-minimumReleaseAge/git-upload-pack
  proxy | 2025/09/23 15:41:48 [006] * authenticating git server request (host: github.com)
  proxy | 2025/09/23 15:41:48 [006] 200 https://github.com:443/karlhorky/repro-conflicting-dependabot-and-renovate-config-vs-pnpm-minimumReleaseAge/git-upload-pack
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1167 completed with status: pid 1167 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.36 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1206 with command: {} git -C /home/dependabot/dependabot-updater/repo ls-files --stage {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1206 completed with status: pid 1206 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1221 with command: {} git config --global credential.helper '!/home/dependabot/common/lib/dependabot/../../bin/git-credential-store-immutable --file /home/dependabot/dependabot-updater/git.store' {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1221 completed with status: pid 1221 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1229 with command: {} git config --global --replace-all url.https://github.com/.insteadOf ssh://git@github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1229 completed with status: pid 1229 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1236 with command: {} git config --global --add url.https://github.com/.insteadOf ssh://git@github.com: {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1236 completed with status: pid 1236 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1243 with command: {} git config --global --add url.https://github.com/.insteadOf git@github.com: {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1243 completed with status: pid 1243 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1250 with command: {} git config --global --add url.https://github.com/.insteadOf git@github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1250 completed with status: pid 1250 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1257 with command: {} git config --global --add url.https://github.com/.insteadOf git://github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1257 completed with status: pid 1257 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1264 with command: {} git config --global --replace-all url.https://github.com/.insteadOf ssh://git@github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1264 completed with status: pid 1264 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1272 with command: {} git config --global --add url.https://github.com/.insteadOf ssh://git@github.com: {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1272 completed with status: pid 1272 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1279 with command: {} git config --global --add url.https://github.com/.insteadOf git@github.com: {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1279 completed with status: pid 1279 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1286 with command: {} git config --global --add url.https://github.com/.insteadOf git@github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1286 completed with status: pid 1286 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.01 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1293 with command: {} git config --global --add url.https://github.com/.insteadOf git://github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1293 completed with status: pid 1293 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1300 with command: {} git lfs pull --include .yarn,./yarn/cache {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1300 completed with status: pid 1300 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.03 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1341 with command: {} git config --global credential.helper '!/home/dependabot/common/lib/dependabot/../../bin/git-credential-store-immutable --file /home/dependabot/dependabot-updater/git.store' {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1341 completed with status: pid 1341 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.01 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1349 with command: {} git config --global --replace-all url.https://github.com/.insteadOf ssh://git@github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1349 completed with status: pid 1349 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1356 with command: {} git config --global --add url.https://github.com/.insteadOf ssh://git@github.com: {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1356 completed with status: pid 1356 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1363 with command: {} git config --global --add url.https://github.com/.insteadOf git@github.com: {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1363 completed with status: pid 1363 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1370 with command: {} git config --global --add url.https://github.com/.insteadOf git@github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1370 completed with status: pid 1370 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1377 with command: {} git config --global --add url.https://github.com/.insteadOf git://github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1377 completed with status: pid 1377 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1384 with command: {} git config --global --replace-all url.https://github.com/.insteadOf ssh://git@github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1384 completed with status: pid 1384 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1391 with command: {} git config --global --add url.https://github.com/.insteadOf ssh://git@github.com: {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1391 completed with status: pid 1391 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1398 with command: {} git config --global --add url.https://github.com/.insteadOf git@github.com: {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1398 completed with status: pid 1398 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1405 with command: {} git config --global --add url.https://github.com/.insteadOf git@github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1405 completed with status: pid 1405 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1412 with command: {} git config --global --add url.https://github.com/.insteadOf git://github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1412 completed with status: pid 1412 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1419 with command: {} git rev-parse HEAD {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1419 completed with status: pid 1419 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1434 with command: {} git config --global credential.helper '!/home/dependabot/common/lib/dependabot/../../bin/git-credential-store-immutable --file /home/dependabot/dependabot-updater/git.store' {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1434 completed with status: pid 1434 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1442 with command: {} git config --global --replace-all url.https://github.com/.insteadOf ssh://git@github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1442 completed with status: pid 1442 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1449 with command: {} git config --global --add url.https://github.com/.insteadOf ssh://git@github.com: {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1449 completed with status: pid 1449 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1456 with command: {} git config --global --add url.https://github.com/.insteadOf git@github.com: {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1456 completed with status: pid 1456 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1463 with command: {} git config --global --add url.https://github.com/.insteadOf git@github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1463 completed with status: pid 1463 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1470 with command: {} git config --global --add url.https://github.com/.insteadOf git://github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1470 completed with status: pid 1470 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.01 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1477 with command: {} git config --global --replace-all url.https://github.com/.insteadOf ssh://git@github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1477 completed with status: pid 1477 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1484 with command: {} git config --global --add url.https://github.com/.insteadOf ssh://git@github.com: {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1484 completed with status: pid 1484 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1491 with command: {} git config --global --add url.https://github.com/.insteadOf git@github.com: {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1491 completed with status: pid 1491 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1498 with command: {} git config --global --add url.https://github.com/.insteadOf git@github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1498 completed with status: pid 1498 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1505 with command: {} git config --global --add url.https://github.com/.insteadOf git://github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1505 completed with status: pid 1505 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1512 with command: {} git rev-parse HEAD {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1512 completed with status: pid 1512 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1527 with command: {} git config --global credential.helper '!/home/dependabot/common/lib/dependabot/../../bin/git-credential-store-immutable --file /home/dependabot/dependabot-updater/git.store' {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1527 completed with status: pid 1527 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1535 with command: {} git config --global --replace-all url.https://github.com/.insteadOf ssh://git@github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1535 completed with status: pid 1535 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1543 with command: {} git config --global --add url.https://github.com/.insteadOf ssh://git@github.com: {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1543 completed with status: pid 1543 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1550 with command: {} git config --global --add url.https://github.com/.insteadOf git@github.com: {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1550 completed with status: pid 1550 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1557 with command: {} git config --global --add url.https://github.com/.insteadOf git@github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1557 completed with status: pid 1557 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1564 with command: {} git config --global --add url.https://github.com/.insteadOf git://github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1564 completed with status: pid 1564 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1571 with command: {} git config --global --replace-all url.https://github.com/.insteadOf ssh://git@github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1571 completed with status: pid 1571 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1578 with command: {} git config --global --add url.https://github.com/.insteadOf ssh://git@github.com: {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1578 completed with status: pid 1578 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1585 with command: {} git config --global --add url.https://github.com/.insteadOf git@github.com: {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1585 completed with status: pid 1585 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1592 with command: {} git config --global --add url.https://github.com/.insteadOf git@github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1592 completed with status: pid 1592 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1599 with command: {} git config --global --add url.https://github.com/.insteadOf git://github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1599 completed with status: pid 1599 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1614 with command: {} git config --global credential.helper '!/home/dependabot/common/lib/dependabot/../../bin/git-credential-store-immutable --file /home/dependabot/dependabot-updater/git.store' {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1614 completed with status: pid 1614 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1622 with command: {} git config --global --replace-all url.https://github.com/.insteadOf ssh://git@github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1622 completed with status: pid 1622 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1629 with command: {} git config --global --add url.https://github.com/.insteadOf ssh://git@github.com: {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1629 completed with status: pid 1629 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1636 with command: {} git config --global --add url.https://github.com/.insteadOf git@github.com: {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1636 completed with status: pid 1636 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1643 with command: {} git config --global --add url.https://github.com/.insteadOf git@github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1643 completed with status: pid 1643 exit 0
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1650 with command: {} git config --global --add url.https://github.com/.insteadOf git://github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1650 completed with status: pid 1650 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1657 with command: {} git config --global --replace-all url.https://github.com/.insteadOf ssh://git@github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1657 completed with status: pid 1657 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1664 with command: {} git config --global --add url.https://github.com/.insteadOf ssh://git@github.com: {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1664 completed with status: pid 1664 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1671 with command: {} git config --global --add url.https://github.com/.insteadOf git@github.com: {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1671 completed with status: pid 1671 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1678 with command: {} git config --global --add url.https://github.com/.insteadOf git@github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1678 completed with status: pid 1678 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1685 with command: {} git config --global --add url.https://github.com/.insteadOf git://github.com/ {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1685 completed with status: pid 1685 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1692 with command: {} git lfs pull --include .yarn,./yarn/cache {}
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Process PID: 1692 completed with status: pid 1692 exit 0
2025/09/23 15:41:48 INFO <job_1107058055> Total execution time: 0.03 seconds
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Detected package manager: pnpm
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Resolving package manager for: pnpm
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Guessed version info "pnpm" : "9"
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Fetching version for package manager: pnpm
updater | 2025/09/23 15:41:48 INFO <job_1107058055> Started process PID: 1724 with command: {} corepack pnpm -v {}
updater | 2025/09/23 15:41:49 INFO <job_1107058055> Process PID: 1724 completed with status: pid 1724 exit 0
2025/09/23 15:41:49 INFO <job_1107058055> Total execution time: 0.37 seconds
updater | 2025/09/23 15:41:49 INFO <job_1107058055> Installed version of pnpm: 10.14.0
updater | 2025/09/23 15:41:49 INFO <job_1107058055> Installed version for pnpm: 10.14.0
updater | 2025/09/23 15:41:49 INFO <job_1107058055> Processing engine constraints for pnpm
updater | 2025/09/23 15:41:49 INFO <job_1107058055> No version requirement found for pnpm
2025/09/23 15:41:49 INFO <job_1107058055> Detected package manager: pnpm
2025/09/23 15:41:49 INFO <job_1107058055> Resolving package manager for: pnpm
2025/09/23 15:41:49 INFO <job_1107058055> Guessed version info "pnpm" : "9"
updater | 2025/09/23 15:41:49 INFO <job_1107058055> Installed version for pnpm: 10.14.0
2025/09/23 15:41:49 INFO <job_1107058055> Processing engine constraints for pnpm
2025/09/23 15:41:49 INFO <job_1107058055> No version requirement found for pnpm
updater | 2025/09/23 15:41:49 INFO <job_1107058055> Detected package manager: pnpm
updater | 2025/09/23 15:41:49 INFO <job_1107058055> Resolving package manager for: pnpm
2025/09/23 15:41:49 INFO <job_1107058055> Guessed version info "pnpm" : "9"
2025/09/23 15:41:49 INFO <job_1107058055> Installed version for pnpm: 10.14.0
updater | 2025/09/23 15:41:49 INFO <job_1107058055> Processing engine constraints for pnpm
2025/09/23 15:41:49 INFO <job_1107058055> No version requirement found for pnpm
updater | 2025/09/23 15:41:49 INFO <job_1107058055> Detected package manager: pnpm
2025/09/23 15:41:49 INFO <job_1107058055> Resolving package manager for: pnpm
updater | 2025/09/23 15:41:49 INFO <job_1107058055> Guessed version info "pnpm" : "9"
2025/09/23 15:41:49 INFO <job_1107058055> Installed version for pnpm: 10.14.0
2025/09/23 15:41:49 INFO <job_1107058055> Processing engine constraints for pnpm
2025/09/23 15:41:49 INFO <job_1107058055> No version requirement found for pnpm
updater | 2025/09/23 15:41:49 INFO <job_1107058055> Detected package manager: pnpm
updater | 2025/09/23 15:41:49 INFO <job_1107058055> Resolving package manager for: pnpm
2025/09/23 15:41:49 INFO <job_1107058055> Guessed version info "pnpm" : "9"
updater | 2025/09/23 15:41:49 INFO <job_1107058055> Installed version for pnpm: 10.14.0
2025/09/23 15:41:49 INFO <job_1107058055> Processing engine constraints for pnpm
updater | 2025/09/23 15:41:49 INFO <job_1107058055> No version requirement found for pnpm
updater | 2025/09/23 15:41:49 INFO <job_1107058055> Detected package manager: pnpm
2025/09/23 15:41:49 INFO <job_1107058055> Resolving package manager for: pnpm
2025/09/23 15:41:49 INFO <job_1107058055> Guessed version info "pnpm" : "9"
updater | 2025/09/23 15:41:49 INFO <job_1107058055> Installed version for pnpm: 10.14.0
updater | 2025/09/23 15:41:49 INFO <job_1107058055> Processing engine constraints for pnpm
2025/09/23 15:41:49 INFO <job_1107058055> No version requirement found for pnpm
updater | 2025/09/23 15:41:49 INFO <job_1107058055> Guessed version info "pnpm" : "9"
updater | 2025/09/23 15:41:49 INFO <job_1107058055> Installing "pnpm@9"
updater | 2025/09/23 15:41:49 INFO <job_1107058055> Started process PID: 1736 with command: {} corepack install pnpm@9 --global --cache-only {}
  proxy | 2025/09/23 15:41:49 [009] GET https://registry.npmjs.org:443/pnpm
  proxy | 2025/09/23 15:41:49 [010] GET https://registry.npmjs.org:443/pnpm
  proxy | 2025/09/23 15:41:49 [009] 200 https://registry.npmjs.org:443/pnpm
  proxy | 2025/09/23 15:41:49 [010] 200 https://registry.npmjs.org:443/pnpm
  proxy | 2025/09/23 15:41:49 [012] GET https://registry.npmjs.org:443/pnpm/-/pnpm-9.15.9.tgz
  proxy | 2025/09/23 15:41:49 [012] 200 https://registry.npmjs.org:443/pnpm/-/pnpm-9.15.9.tgz
  proxy | 2025/09/23 15:41:50 [014] GET https://registry.npmjs.org:443/pnpm/9.15.9
  proxy | 2025/09/23 15:41:50 [014] 200 https://registry.npmjs.org:443/pnpm/9.15.9
updater | 2025/09/23 15:41:50 INFO <job_1107058055> Process PID: 1736 completed with status: pid 1736 exit 0
2025/09/23 15:41:50 INFO <job_1107058055> Total execution time: 0.95 seconds
updater | 2025/09/23 15:41:50 INFO <job_1107058055> pnpm@9 successfully installed.
2025/09/23 15:41:50 INFO <job_1107058055> Activating currently installed version of pnpm: 9
updater | 2025/09/23 15:41:50 INFO <job_1107058055> Started process PID: 1748 with command: {} corepack prepare pnpm@9 --activate {}
updater | 2025/09/23 15:41:50 INFO <job_1107058055> Process PID: 1748 completed with status: pid 1748 exit 0
2025/09/23 15:41:50 INFO <job_1107058055> Total execution time: 0.07 seconds
updater | 2025/09/23 15:41:50 INFO <job_1107058055> Fetching version for package manager: pnpm
updater | 2025/09/23 15:41:50 INFO <job_1107058055> Started process PID: 1760 with command: {} corepack pnpm -v {}
updater | 2025/09/23 15:41:50 INFO <job_1107058055> Process PID: 1760 completed with status: pid 1760 exit 0
2025/09/23 15:41:50 INFO <job_1107058055> Total execution time: 0.41 seconds
2025/09/23 15:41:50 INFO <job_1107058055> Installed version of pnpm: 9.15.9
updater | 2025/09/23 15:41:50 INFO <job_1107058055> Detected package manager: pnpm
2025/09/23 15:41:50 INFO <job_1107058055> Resolving package manager for: pnpm
updater | 2025/09/23 15:41:50 INFO <job_1107058055> Guessed version info "pnpm" : "9"
updater | 2025/09/23 15:41:50 INFO <job_1107058055> Installed version for pnpm: 10.14.0
2025/09/23 15:41:50 INFO <job_1107058055> Processing engine constraints for pnpm
updater | 2025/09/23 15:41:50 INFO <job_1107058055> No version requirement found for pnpm
updater | 2025/09/23 15:41:50 INFO <job_1107058055> Detected package manager: pnpm
2025/09/23 15:41:50 INFO <job_1107058055> Resolving package manager for: pnpm
updater | 2025/09/23 15:41:50 INFO <job_1107058055> Guessed version info "pnpm" : "9"
updater | 2025/09/23 15:41:50 INFO <job_1107058055> Installed version for pnpm: 10.14.0
updater | 2025/09/23 15:41:50 INFO <job_1107058055> Processing engine constraints for pnpm
2025/09/23 15:41:50 INFO <job_1107058055> No version requirement found for pnpm
updater | 2025/09/23 15:41:50 INFO <job_1107058055> Detected package manager: pnpm
updater | 2025/09/23 15:41:50 INFO <job_1107058055> Resolving package manager for: pnpm
2025/09/23 15:41:50 INFO <job_1107058055> Guessed version info "pnpm" : "9"
updater | 2025/09/23 15:41:50 INFO <job_1107058055> Installed version for pnpm: 10.14.0
updater | 2025/09/23 15:41:50 INFO <job_1107058055> Processing engine constraints for pnpm
2025/09/23 15:41:50 INFO <job_1107058055> No version requirement found for pnpm
2025/09/23 15:41:50 INFO <job_1107058055> Detected package manager: pnpm
2025/09/23 15:41:50 INFO <job_1107058055> Resolving package manager for: pnpm
2025/09/23 15:41:50 INFO <job_1107058055> Guessed version info "pnpm" : "9"
2025/09/23 15:41:50 INFO <job_1107058055> Installed version for pnpm: 10.14.0
2025/09/23 15:41:50 INFO <job_1107058055> Processing engine constraints for pnpm
2025/09/23 15:41:50 INFO <job_1107058055> No version requirement found for pnpm
  proxy | 2025/09/23 15:41:50 [016] POST /update_jobs/1107058055/record_ecosystem_versions
  proxy | 2025/09/23 15:41:50 [016] 204 /update_jobs/1107058055/record_ecosystem_versions
updater | 2025/09/23 15:41:50 INFO <job_1107058055> Base commit SHA: 7aba220d600e42800967f2c304b823dd4f068d34
updater | 2025/09/23 15:41:50 INFO <job_1107058055> Finished job processing
updater | 2025/09/23 15:41:52 INFO <job_1107058055> Starting job processing
updater | 2025/09/23 15:41:52 INFO <job_1107058055> Detected package manager: pnpm
updater | 2025/09/23 15:41:52 INFO <job_1107058055> Resolving package manager for: pnpm
updater | 2025/09/23 15:41:52 INFO <job_1107058055> Guessed version info "pnpm" : "9"
updater | 2025/09/23 15:41:52 INFO <job_1107058055> Fetching version for package manager: pnpm
updater | 2025/09/23 15:41:52 INFO <job_1107058055> Started process PID: 1784 with command: {} corepack pnpm -v {}
updater | 2025/09/23 15:41:53 INFO <job_1107058055> Process PID: 1784 completed with status: pid 1784 exit 0
2025/09/23 15:41:53 INFO <job_1107058055> Total execution time: 0.41 seconds
updater | 2025/09/23 15:41:53 INFO <job_1107058055> Installed version of pnpm: 9.15.9
updater | 2025/09/23 15:41:53 INFO <job_1107058055> Installed version for pnpm: 9.15.9
updater | 2025/09/23 15:41:53 INFO <job_1107058055> Processing engine constraints for pnpm
2025/09/23 15:41:53 INFO <job_1107058055> No version requirement found for pnpm
updater | 2025/09/23 15:41:53 INFO <job_1107058055> Running node command: node -v
updater | 2025/09/23 15:41:53 INFO <job_1107058055> Started process PID: 1796 with command: {} node -v {}
updater | 2025/09/23 15:41:53 INFO <job_1107058055> Process PID: 1796 completed with status: pid 1796 exit 0
2025/09/23 15:41:53 INFO <job_1107058055> Total execution time: 0.01 seconds
updater | 2025/09/23 15:41:53 INFO <job_1107058055> Command executed successfully: node -v
updater | 2025/09/23 15:41:53 INFO <job_1107058055> Processing engine constraints for node
updater | 2025/09/23 15:41:53 INFO <job_1107058055> Started process PID: 1798 with command: node /opt/npm_and_yarn/run.js
updater | 2025/09/23 15:41:53 INFO <job_1107058055> Process PID: 1798 completed with status: pid 1798 exit 0
2025/09/23 15:41:53 INFO <job_1107058055> Total execution time: 0.17 seconds
  proxy | 2025/09/23 15:41:53 [019] POST /update_jobs/1107058055/update_dependency_list
  proxy | 2025/09/23 15:41:53 [019] 204 /update_jobs/1107058055/update_dependency_list
  proxy | 2025/09/23 15:41:53 [021] POST /update_jobs/1107058055/increment_metric
  proxy | 2025/09/23 15:41:53 [021] 204 /update_jobs/1107058055/increment_metric
updater | 2025/09/23 15:41:53 INFO <job_1107058055> Starting update job for karlhorky/repro-conflicting-dependabot-and-renovate-config-vs-pnpm-minimumReleaseAge
2025/09/23 15:41:53 INFO <job_1107058055> Checking and updating security pull requests...
updater | 2025/09/23 15:41:53 INFO <job_1107058055> Security advisory dependency: next
First dependency in list: next
updater | 2025/09/23 15:41:53 INFO <job_1107058055> Checking if next 15.1.7 needs updating
  proxy | 2025/09/23 15:41:53 [023] GET https://registry.npmjs.org/next
  proxy | 2025/09/23 15:41:53 [023] 200 https://registry.npmjs.org/next
  proxy | 2025/09/23 15:41:55 [027] HEAD https://registry.npmjs.org/next/-/next-15.5.3.tgz
  proxy | 2025/09/23 15:41:55 [027] 200 https://registry.npmjs.org/next/-/next-15.5.3.tgz
updater | 2025/09/23 15:41:55 INFO <job_1107058055> Latest version is 15.5.3
updater | 2025/09/23 15:41:55 INFO <job_1107058055> VulnerabilityAuditor: starting audit
updater | 2025/09/23 15:41:55 INFO <job_1107058055> VulnerabilityAuditor: missing lockfile
  proxy | 2025/09/23 15:41:55 [029] HEAD https://registry.npmjs.org/next/-/next-15.4.7.tgz
  proxy | 2025/09/23 15:41:55 [029] 200 https://registry.npmjs.org/next/-/next-15.4.7.tgz
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Requirements to unlock own
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Requirements update strategy bump_versions
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Updating next from 15.1.7 to 15.4.7
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Started process PID: 1817 with command: {} git reset HEAD --hard {}
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Process PID: 1817 completed with status: pid 1817 exit 0
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Total execution time: 0.01 seconds
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Started process PID: 1824 with command: {} git clean -fx {}
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Process PID: 1824 completed with status: pid 1824 exit 0
2025/09/23 15:41:56 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Started process PID: 1831 with command: node /opt/npm_and_yarn/run.js
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Process PID: 1831 completed with status: pid 1831 exit 0
2025/09/23 15:41:56 INFO <job_1107058055> Total execution time: 0.17 seconds
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Started process PID: 1851 with command: {} git config --global credential.helper '!/home/dependabot/common/lib/dependabot/../../bin/git-credential-store-immutable --file /home/dependabot/dependabot-updater/repo/git.store' {}
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Process PID: 1851 completed with status: pid 1851 exit 0
2025/09/23 15:41:56 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Started process PID: 1859 with command: {} git config --global --replace-all url.https://github.com/.insteadOf ssh://git@github.com/ {}
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Process PID: 1859 completed with status: pid 1859 exit 0
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Started process PID: 1866 with command: {} git config --global --add url.https://github.com/.insteadOf ssh://git@github.com: {}
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Process PID: 1866 completed with status: pid 1866 exit 0
2025/09/23 15:41:56 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Started process PID: 1873 with command: {} git config --global --add url.https://github.com/.insteadOf git@github.com: {}
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Process PID: 1873 completed with status: pid 1873 exit 0
2025/09/23 15:41:56 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Started process PID: 1880 with command: {} git config --global --add url.https://github.com/.insteadOf git@github.com/ {}
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Process PID: 1880 completed with status: pid 1880 exit 0
2025/09/23 15:41:56 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Started process PID: 1887 with command: {} git config --global --add url.https://github.com/.insteadOf git://github.com/ {}
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Process PID: 1887 completed with status: pid 1887 exit 0
2025/09/23 15:41:56 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Started process PID: 1894 with command: {} git config --global --replace-all url.https://github.com/.insteadOf ssh://git@github.com/ {}
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Process PID: 1894 completed with status: pid 1894 exit 0
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Started process PID: 1901 with command: {} git config --global --add url.https://github.com/.insteadOf ssh://git@github.com: {}
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Process PID: 1901 completed with status: pid 1901 exit 0
2025/09/23 15:41:56 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Started process PID: 1908 with command: {} git config --global --add url.https://github.com/.insteadOf git@github.com: {}
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Process PID: 1908 completed with status: pid 1908 exit 0
2025/09/23 15:41:56 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Started process PID: 1915 with command: {} git config --global --add url.https://github.com/.insteadOf git@github.com/ {}
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Process PID: 1915 completed with status: pid 1915 exit 0
2025/09/23 15:41:56 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Started process PID: 1922 with command: {} git config --global --add url.https://github.com/.insteadOf git://github.com/ {}
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Process PID: 1922 completed with status: pid 1922 exit 0
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Total execution time: 0.0 seconds
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Started process PID: 1929 with command: {} corepack pnpm update next@15.4.7 --lockfile-only --no-save -r {}
updater | 2025/09/23 15:41:56 INFO <job_1107058055> Process PID: 1929 completed with status: pid 1929 exit 1
2025/09/23 15:41:56 INFO <job_1107058055> Total execution time: 0.41 seconds
updater | 2025/09/23 15:41:56 ERROR <job_1107058055> Error running package manager command: corepack pnpm update next@15.4.7  --lockfile-only --no-save -r, Error:  ERROR  packages field missing or empty
For help, run: pnpm help update
  proxy | 2025/09/23 15:41:56 [031] POST /update_jobs/1107058055/record_update_job_unknown_error
  proxy | 2025/09/23 15:41:56 [031] 204 /update_jobs/1107058055/record_update_job_unknown_error
  proxy | 2025/09/23 15:41:56 [033] POST /update_jobs/1107058055/record_update_job_error
  proxy | 2025/09/23 15:41:57 [033] 204 /update_jobs/1107058055/record_update_job_error
  proxy | 2025/09/23 15:41:57 [035] POST /update_jobs/1107058055/increment_metric
  proxy | 2025/09/23 15:41:57 [035] 204 /update_jobs/1107058055/increment_metric
  proxy | 2025/09/23 15:41:57 [037] POST /update_jobs/1107058055/record_update_job_unknown_error
  proxy | 2025/09/23 15:41:57 [037] 204 /update_jobs/1107058055/record_update_job_unknown_error
updater | 2025/09/23 15:41:57 ERROR <job_1107058055> Error processing next (Dependabot::SharedHelpers::HelperSubprocessFailed)
2025/09/23 15:41:57 ERROR <job_1107058055>  ERROR  packages field missing or empty
For help, run: pnpm help update
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/common/lib/dependabot/shared_helpers.rb:514:in 'Dependabot::SharedHelpers.run_shell_command'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:179:in 'UnboundMethod#bind_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:179:in 'T::Private::Methods::CallValidation.validate_call_skip_block_type'
updater | 2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:121:in 'block in Dependabot::SharedHelpers.create_validator_slow_skip_block_type'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/npm_and_yarn/lib/dependabot/npm_and_yarn/helpers.rb:540:in 'Dependabot::NpmAndYarn::Helpers.package_manager_run_command'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:179:in 'UnboundMethod#bind_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:179:in 'T::Private::Methods::CallValidation.validate_call_skip_block_type'
updater | 2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:121:in 'block in Dependabot::NpmAndYarn::Helpers.create_validator_slow_skip_block_type'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/npm_and_yarn/lib/dependabot/npm_and_yarn/helpers.rb:380:in 'Dependabot::NpmAndYarn::Helpers.run_pnpm_command'
updater | 2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'UnboundMethod#bind_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'T::Private::Methods::CallValidation.validate_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/_methods.rb:277:in 'block in Dependabot::NpmAndYarn::Helpers._on_method_added'
updater | 2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/npm_and_yarn/lib/dependabot/npm_and_yarn/file_updater/pnpm_lockfile_updater.rb:170:in 'Dependabot::NpmAndYarn::FileUpdater::PnpmLockfileUpdater#run_pnpm_update_packages'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'UnboundMethod#bind_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'T::Private::Methods::CallValidation.validate_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/_methods.rb:277:in 'block in Dependabot::NpmAndYarn::FileUpdater::PnpmLockfileUpdater#_on_method_added'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/npm_and_yarn/lib/dependabot/npm_and_yarn/file_updater/pnpm_lockfile_updater.rb:153:in 'block (2 levels) in Dependabot::NpmAndYarn::FileUpdater::PnpmLockfileUpdater#run_pnpm_update'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/common/lib/dependabot/shared_helpers.rb:314:in 'Dependabot::SharedHelpers.with_git_configured'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'UnboundMethod#bind_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'T::Private::Methods::CallValidation.validate_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/_methods.rb:277:in 'block in Dependabot::SharedHelpers._on_method_added'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/npm_and_yarn/lib/dependabot/npm_and_yarn/file_updater/pnpm_lockfile_updater.rb:149:in 'block in Dependabot::NpmAndYarn::FileUpdater::PnpmLockfileUpdater#run_pnpm_update'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/common/lib/dependabot/shared_helpers.rb:58:in 'block in Dependabot::SharedHelpers.in_a_temporary_repo_directory'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/common/lib/dependabot/shared_helpers.rb:58:in 'Dir.chdir'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/common/lib/dependabot/shared_helpers.rb:58:in 'Dependabot::SharedHelpers.in_a_temporary_repo_directory'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'UnboundMethod#bind_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'T::Private::Methods::CallValidation.validate_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/_methods.rb:277:in 'block in Dependabot::SharedHelpers._on_method_added'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/npm_and_yarn/lib/dependabot/npm_and_yarn/file_updater/pnpm_lockfile_updater.rb:146:in 'Dependabot::NpmAndYarn::FileUpdater::PnpmLockfileUpdater#run_pnpm_update'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'UnboundMethod#bind_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'T::Private::Methods::CallValidation.validate_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/_methods.rb:277:in 'block in Dependabot::NpmAndYarn::FileUpdater::PnpmLockfileUpdater#_on_method_added'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/npm_and_yarn/lib/dependabot/npm_and_yarn/file_updater/pnpm_lockfile_updater.rb:54:in 'Dependabot::NpmAndYarn::FileUpdater::PnpmLockfileUpdater#updated_pnpm_lock_content'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'UnboundMethod#bind_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'T::Private::Methods::CallValidation.validate_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/_methods.rb:277:in 'block in Dependabot::NpmAndYarn::FileUpdater::PnpmLockfileUpdater#_on_method_added'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/npm_and_yarn/lib/dependabot/npm_and_yarn/file_updater.rb:420:in 'Dependabot::NpmAndYarn::FileUpdater#updated_pnpm_lock_content'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'UnboundMethod#bind_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'T::Private::Methods::CallValidation.validate_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/_methods.rb:277:in 'block in Dependabot::NpmAndYarn::FileUpdater#_on_method_added'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/npm_and_yarn/lib/dependabot/npm_and_yarn/file_updater.rb:327:in 'Dependabot::NpmAndYarn::FileUpdater#pnpm_lock_changed?'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'UnboundMethod#bind_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'T::Private::Methods::CallValidation.validate_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/_methods.rb:277:in 'block in Dependabot::NpmAndYarn::FileUpdater#_on_method_added'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/npm_and_yarn/lib/dependabot/npm_and_yarn/file_updater.rb:139:in 'block in Dependabot::NpmAndYarn::FileUpdater#update_pnpm_locks'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/npm_and_yarn/lib/dependabot/npm_and_yarn/file_updater.rb:138:in 'Array#each'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/npm_and_yarn/lib/dependabot/npm_and_yarn/file_updater.rb:138:in 'Dependabot::NpmAndYarn::FileUpdater#update_pnpm_locks'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'UnboundMethod#bind_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'T::Private::Methods::CallValidation.validate_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/_methods.rb:277:in 'block in Dependabot::NpmAndYarn::FileUpdater#_on_method_added'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/npm_and_yarn/lib/dependabot/npm_and_yarn/file_updater.rb:378:in 'Dependabot::NpmAndYarn::FileUpdater#updated_lockfiles'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'UnboundMethod#bind_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'T::Private::Methods::CallValidation.validate_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/_methods.rb:277:in 'block in Dependabot::NpmAndYarn::FileUpdater#_on_method_added'
updater | 2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/npm_and_yarn/lib/dependabot/npm_and_yarn/file_updater.rb:61:in 'Dependabot::NpmAndYarn::FileUpdater#updated_dependency_files'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'UnboundMethod#bind_call'
updater | 2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'T::Private::Methods::CallValidation.validate_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/_methods.rb:277:in 'block in Dependabot::NpmAndYarn::FileUpdater#_on_method_added'
updater | 2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/lib/dependabot/dependency_change_builder.rb:148:in 'Dependabot::DependencyChangeBuilder#generate_dependency_files'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'UnboundMethod#bind_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'T::Private::Methods::CallValidation.validate_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/_methods.rb:277:in 'block in Dependabot::DependencyChangeBuilder#_on_method_added'
updater | 2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/lib/dependabot/dependency_change_builder.rb:74:in 'Dependabot::DependencyChangeBuilder#run'
updater | 2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'UnboundMethod#bind_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'T::Private::Methods::CallValidation.validate_call'
updater | 2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/_methods.rb:277:in 'block in Dependabot::DependencyChangeBuilder#_on_method_added'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/lib/dependabot/dependency_change_builder.rb:44:in 'Dependabot::DependencyChangeBuilder.create_from'
updater | 2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'UnboundMethod#bind_call'
updater | 2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'T::Private::Methods::CallValidation.validate_call'
updater | 2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/_methods.rb:277:in 'block in Dependabot::DependencyChangeBuilder._on_method_added'
updater | 2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/lib/dependabot/updater/operations/refresh_security_update_pull_request.rb:190:in 'Dependabot::Updater::Operations::RefreshSecurityUpdatePullRequest#check_and_update_pull_request'
updater | 2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'UnboundMethod#bind_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'T::Private::Methods::CallValidation.validate_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/_methods.rb:277:in 'block in Dependabot::Updater::Operations::RefreshSecurityUpdatePullRequest#_on_method_added'
updater | 2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/lib/dependabot/updater/operations/refresh_security_update_pull_request.rb:61:in 'Dependabot::Updater::Operations::RefreshSecurityUpdatePullRequest#perform'
updater | 2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'UnboundMethod#bind_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'T::Private::Methods::CallValidation.validate_call'
updater | 2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/_methods.rb:277:in 'block in Dependabot::Updater::Operations::RefreshSecurityUpdatePullRequest#_on_method_added'
updater | 2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/lib/dependabot/updater.rb:56:in 'Dependabot::Updater#run'
updater | 2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'UnboundMethod#bind_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'T::Private::Methods::CallValidation.validate_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/_methods.rb:277:in 'block in Dependabot::Updater#_on_method_added'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/lib/dependabot/update_files_command.rb:51:in 'block in Dependabot::UpdateFilesCommand#perform_job'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/opentelemetry-api-1.5.0/lib/opentelemetry/trace/tracer.rb:37:in 'block in OpenTelemetry::Trace::Tracer#in_span'
updater | 2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/opentelemetry-api-1.5.0/lib/opentelemetry/trace.rb:70:in 'block in OpenTelemetry::Trace#with_span'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/opentelemetry-api-1.5.0/lib/opentelemetry/context.rb:88:in 'OpenTelemetry::Context.with_value'
updater | 2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/opentelemetry-api-1.5.0/lib/opentelemetry/trace.rb:70:in 'OpenTelemetry::Trace#with_span'
updater | 2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/opentelemetry-api-1.5.0/lib/opentelemetry/trace/tracer.rb:37:in 'OpenTelemetry::Trace::Tracer#in_span'
updater | 2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/lib/dependabot/update_files_command.rb:24:in 'Dependabot::UpdateFilesCommand#perform_job'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'UnboundMethod#bind_call'
updater | 2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'T::Private::Methods::CallValidation.validate_call'
updater | 2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/_methods.rb:277:in 'block in Dependabot::UpdateFilesCommand#_on_method_added'
updater | 2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/lib/dependabot/base_command.rb:42:in 'Dependabot::BaseCommand#run'
updater | 2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'UnboundMethod#bind_call'
updater | 2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/call_validation.rb:282:in 'T::Private::Methods::CallValidation.validate_call'
2025/09/23 15:41:57 ERROR <job_1107058055> /home/dependabot/dependabot-updater/vendor/ruby/3.4.0/gems/sorbet-runtime-0.6.12544/lib/types/private/methods/_methods.rb:277:in 'block in Dependabot::BaseCommand#_on_method_added'
2025/09/23 15:41:57 ERROR <job_1107058055> bin/update_files.rb:44:in '<main>'
  proxy | 2025/09/23 15:41:57 [039] POST /update_jobs/1107058055/record_ecosystem_meta
  proxy | 2025/09/23 15:41:57 [039] 204 /update_jobs/1107058055/record_ecosystem_meta
  proxy | 2025/09/23 15:41:57 [041] PATCH /update_jobs/1107058055/mark_as_processed
  proxy | 2025/09/23 15:41:57 [041] 204 /update_jobs/1107058055/mark_as_processed
updater | 2025/09/23 15:41:57 INFO <job_1107058055> Finished job processing
updater | 2025/09/23 15:41:57 INFO Results:
Dependabot encountered '1' error(s) during execution, please check the logs for more details.
+--------------------------------------------+
|       Dependencies failed to update        |
+------------+---------------+---------------+
| Dependency | Error Type    | Error Details |
+------------+---------------+---------------+
| next       | unknown_error | null          |
+------------+---------------+---------------+
Failure running container e9e6bff4edea67fd37ae84e04659b4e0192a4201e0addcd20ac0b5d1197615e7: Error: Command failed with exit code 1: /bin/sh -c $DEPENDABOT_HOME/dependabot-updater/bin/run update_files
Cleaned up container e9e6bff4edea67fd37ae84e04659b4e0192a4201e0addcd20ac0b5d1197615e7
  proxy | 2025/09/23 15:41:57 0/19 calls cached (0%)
2025/09/23 15:41:57 Posting metrics to remote API endpoint
##[error]Dependabot encountered an error performing the update

Error: The updater encountered one or more errors.

For more information see: https://github.com/karlhorky/repro-conflicting-dependabot-and-renovate-config-vs-pnpm-minimumReleaseAge/network/updates/1107058055 (write access to the repository is required to view the log)
🤖 ~ finished: error reported to Dependabot ~
Post job cleanup.
Cleaning up orphan processes
```

## Renovate bot

Logs from Renovate bot failing update run:

```

```
