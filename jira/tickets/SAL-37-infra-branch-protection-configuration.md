# [infra] - Branch Protection Rules Configuration

**Jira Key**: [SAL-37](https://techsharif.atlassian.net/browse/SAL-37)
**Type**: Task
**Status**: To Do
**Priority**: High
**Assignee**: Unassigned
**Labels**: [infra, git, branch-protection, phase1]
**Component**: Infrastructure
**Epic**: [SAL-1](https://techsharif.atlassian.net/browse/SAL-1)
**Created**: 2026-01-03
**Last Updated**: 2026-01-03

## Description

Configure branch protection rules in GitHub repository settings to enforce code quality and prevent broken code from being merged. The documentation and guidelines are already in place (SAL-17), but the actual GitHub repository settings need to be configured manually.

This is a manual configuration task that must be performed by a repository administrator with appropriate permissions.

## Acceptance Criteria

- [ ] Branch protection rules configured for `main` branch
- [ ] Branch protection rules configured for `master` branch (if exists)
- [ ] Branch protection rules configured for `develop` branch
- [ ] Require pull request reviews enabled (minimum 1 approver)
- [ ] Require status checks to pass enabled (CI pipeline - "test" job)
- [ ] Require branches to be up to date before merging enabled
- [ ] Require conversation resolution before merging enabled
- [ ] Prevent force pushes to protected branches enabled
- [ ] Prevent deletion of protected branches enabled
- [ ] Branch protection status documented in README.md
- [ ] Configuration verified and tested

## Technical Details

### Branch Protection Rules to Configure

For each protected branch (`main`, `master`, `develop`):

1. **Require a pull request before merging**
   - Require approvals: 1
   - Dismiss stale pull request approvals when new commits are pushed: Yes (optional)

2. **Require status checks to pass before merging**
   - Select: `test` (from CI workflow)
   - Require branches to be up to date before merging: Yes

3. **Require conversation resolution before merging**
   - Enabled: Yes

4. **Restrict who can push to matching branches**
   - Optional: Can restrict to specific teams/users

5. **Do not allow bypassing the above settings**
   - Optional: For additional security

6. **Do not allow force pushes**
   - Enabled: Yes

7. **Do not allow deletions**
   - Enabled: Yes

### Setup Instructions

1. Navigate to GitHub repository
2. Go to **Settings** → **Branches**
3. Click **Add rule** or edit existing rule
4. Enter branch name pattern: `main`, `master`, or `develop`
5. Enable all required protection rules (listed above)
6. Click **Create** or **Save changes**
7. Repeat for each branch that needs protection

### Free Plan Limitations

GitHub free plan allows:
- ✅ Require 1 reviewer (sufficient for most cases)
- ✅ All other protection rules listed above

GitHub free plan does NOT allow:
- ❌ Require multiple reviewers (beyond 1)
- ❌ Require linear history
- ❌ Require signed commits
- ❌ Lock branch

These limitations are acceptable for the project.

## Related Items

- **Epic**: [SAL-1](https://techsharif.atlassian.net/browse/SAL-1) - Backend Foundation & Infrastructure
- **Parent Ticket**: [SAL-17](https://techsharif.atlassian.net/browse/SAL-17) - Merge Policy & Branch Protection Setup
- **Depends On**: 
  - SAL-17 (Merge Policy & Branch Protection Setup) - documentation must be complete
  - SAL-15 (CI/CD Pipeline Setup) - CI pipeline must be working (for status checks)
- **Blocks**: None (can be done in parallel with other work)

## Notes

- This is a **manual configuration task** - cannot be automated via code
- Requires repository admin permissions
- Documentation is already complete in README.md (Branch Protection section)
- Setup instructions are documented in README.md
- Once configured, update the checklist in README.md:
  ```markdown
  - [x] Branch protection rules configured
  - [x] Status checks required
  - [x] PR reviews required
  - [x] Force pushes prevented
  ```
- Test the configuration by:
  - Creating a test PR
  - Verifying CI must pass before merge
  - Verifying PR review is required
  - Attempting to force push (should be blocked)
- Consider documenting who has admin access and who configured the rules

## History

- 2026-01-03: Task created to track branch protection configuration work

