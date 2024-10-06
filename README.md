# .github Repository for Containerly

This repository serves as a centralized location for community health files and configurations that apply to all repositories within the **[Your Organization Name]** GitHub organization.

By maintaining these files in the `.github` repository, we ensure consistency across all projects and make it easier to manage organization-wide policies and templates.

## Contents

- **[CODE_OF_CONDUCT.md](./CODE_OF_CONDUCT.md)**: Our commitment to an open and welcoming environment.
- **[CONTRIBUTING.md](./CONTRIBUTING.md)**: Guidelines for contributing to our projects.
- **[SUPPORT.md](./SUPPORT.md)**: Resources for getting help and support.
- **[ISSUE_TEMPLATE](./ISSUE_TEMPLATE/)**: Templates for reporting bugs and requesting features.
  - `bug_report.md`
  - `feature_request.md`
  - `config.yml`
- **[PULL_REQUEST_TEMPLATE.md](./PULL_REQUEST_TEMPLATE.md)**: Template for submitting pull requests.
- **[FUNDING.yml](./FUNDING.yml)**: Configuration for GitHub Sponsors and other funding platforms.
- **[SECURITY.md](./SECURITY.md)**: Instructions for reporting security vulnerabilities.
- **[workflows](./workflows/)**: Shared GitHub Actions workflows.
  - `ci.yml`
  - `release.yml`
- **[profile/README.md](./profile/README.md)**: The organization profile that appears on our GitHub organization page.

## Purpose

Centralizing these files helps us:

- **Promote Consistency**: Ensure all repositories follow the same guidelines and standards.
- **Simplify Management**: Update policies and templates in one place.
- **Enhance Collaboration**: Provide clear instructions to contributors, fostering a welcoming community.

## How It Works

- **Community Health Files**: GitHub automatically uses the files in the `.github` repository for any repository in the organization that does not have its own corresponding file.
- **Issue and PR Templates**: These templates are available to all repositories, streamlining the process of reporting issues and submitting pull requests.
- **GitHub Actions Workflows**: Shared workflows can be referenced in individual repositories to maintain consistent CI/CD processes.

## Contribution

We welcome contributions to improve our community guidelines and templates. To suggest changes:

1. Fork this repository.
2. Create a new branch: `git checkout -b feature/improve-guidelines`.
3. Make your changes and commit them: `git commit -m 'Improve contribution guidelines'`.
4. Push to the branch: `git push origin feature/improve-guidelines`.
5. Open a pull request.

## License

This repository and its contents are licensed under the [MIT License](./LICENSE).

## Contact

For questions or suggestions, please open an issue or reach out to us at [contact@your-organization.com](mailto:contact@your-organization.com).

---

**Note**: Replace placeholders like `[Your Organization Name]` and contact information with your actual organization details.

