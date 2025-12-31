# [infra] - Merge Policy & Branch Protection Setup

**Jira Key**: [SAL-17](https://techsharif.atlassian.net/browse/SAL-17)
**Type**: Task
**Status**: To Do
**Priority**: High
**Assignee**: Unassigned
**Labels**: [infra, git, branch-protection, phase1]
**Component**: Infrastructure
**Epic**: [SAL-1](https://techsharif.atlassian.net/browse/SAL-1)
**Created**: 2025-12-20
**Last Updated**: 2025-12-20

## Description

Set up merge policies and branch protection rules for the repository. This includes configuring branch protection, requiring code reviews, enforcing CI/CD pipeline success, and establishing a clear branching strategy.

Proper merge policies ensure code quality and prevent broken code from being merged into main branches.

## Acceptance Criteria

- [ ] Branch protection rules configured for main/master branch
- [ ] Require pull request reviews (minimum 1 approver)
- [ ] Require CI/CD pipeline to pass before merge
- [ ] Require branches to be up to date before merge
- [ ] Prevent force pushes to protected branches
- [ ] Prevent deletion of protected branches
- [ ] Branching strategy documented (Git Flow, GitHub Flow, etc.)
- [ ] Pull request template created
- [ ] Code review guidelines documented
- [ ] Merge commit strategy defined (merge, squash, rebase)
- [ ] Conventional commits enforced (if applicable)

## Technical Details

### Branch Protection Rules
- **Main/Master Branch**:
  - Require pull request reviews
  - Require status checks to pass
  - Require branches to be up to date
  - Require conversation resolution
  - Restrict who can push
  - Prevent force pushes
  - Prevent branch deletion

### Branching Strategy
- **Main/Master**: Production-ready code
- **Develop**: Integration branch for features
- **Feature branches**: Feature development (feature/SAL-XXX-description)
- **Hotfix branches**: Critical bug fixes (hotfix/description)
- **Release branches**: Release preparation (release/v1.0.0)

### Pull Request Requirements
- Description template
- Link to related Jira ticket
- Checklist of requirements
- Screenshots (if applicable)
- Test coverage information

### Code Review Guidelines
- Minimum 1 approver required
- Reviewers should check:
  - Code quality
  - Test coverage
  - Documentation
  - Security considerations
  - Performance implications

## Related Items

- **Epic**: [SAL-1](https://techsharif.atlassian.net/browse/SAL-1) - Backend Foundation & Infrastructure
- **Depends On**: SAL-14 (Repository Setup), SAL-15 (Pipeline Setup)
- **Related**: SAL-15 (CI/CD Pipeline)

## Notes

- Use conventional commits format (feat:, fix:, refactor:, etc.)
- Require at least one code review before merge
- Enforce CI/CD pipeline success
- Document the branching strategy clearly
- Consider using branch naming conventions (feature/SAL-XXX-description)
- Set up pull request templates for consistency

## History

- 2025-12-20: Task created

