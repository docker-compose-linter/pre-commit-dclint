# pre-commit-dclint

Mirror of dclint package for pre-commit.

- For `pre-commit`: see https://github.com/pre-commit/pre-commit
- For `dclint`: see https://github.com/zavoloklom/docker-compose-linter

This repository provides both a Node.js and Docker-based `pre-commit` hook to validate and enforce best practices
automatically before committing.

## Usage (Node.js)

Add the following to your `.pre-commit-config.yaml`:

```yaml
repos:
  - repo: https://github.com/docker-compose-linter/pre-commit-dclint
    rev: v3.1.0  # Matches the dclint version, use the sha or tag you want to point at
    hooks:
      - id: dclint
        # Optional: regex override for compose files
        files: ^(docker-)?compose\.ya?ml
        # Optional: enable autofix on commit
        args: [ --fix ]  
```

## Usage (Docker)

If you prefer not to install Node.js, you can run dclint via Docker:

```yaml
repos:
  - repo: https://github.com/docker-compose-linter/pre-commit-dclint
    rev: v3.1.0 # Matches the dclint version, use the sha or tag you want to point at
    hooks:
      - id: dclint-docker
        # Optional: regex override for compose files
        files: ^(docker-)?compose\.ya?ml$
        # Optional: enable autofix on commit
        args: [ --fix ]
```

## CLI Arguments

For a full list of supported CLI arguments, see
the [official documentation](https://github.com/zavoloklom/docker-compose-linter/blob/main/docs/cli.md).

Note that the `-r` (or `--recursive`) flag does not influence how pre-commit selects files to run hooks on. Instead,
pre-commit uses the `files:` regex to determine which files should trigger the hook. This regex is applied to all
changed file paths before the hook is invoked. If a file doesn’t match the pattern, the hook won’t run at all —
regardless of whether `--recursive` is used internally.

In this setup, the `files:` regex is already configured to match nested `compose.yaml` files, so pre-commit can
correctly detect relevant changes and invoke the hook only when needed.

## Versioning

This mirror is automatically updated to match the latest dclint version published on npm and docker registry.

Version synchronization is maintained via GitHub Actions on a weekly schedule.

## License

This project is licensed under the MIT License. See the [LICENSE](./LICENSE) file for more information.

## Contacts and Support

If you find this repository helpful, kindly consider showing your appreciation by giving it a star ⭐.

If you have any questions or suggestions, feel free to reach out:

- **Email**: [s.kupletsky@gmail.com](mailto:s.kupletsky@gmail.com)
- **Х/Twitter**: [zavoloklom](https://x.com/zavoloklom)
- **Instagram**: [zavoloklom](https://www.instagram.com/zavoloklom/)
- **GitHub**: [zavoloklom](https://github.com/zavoloklom)

Also, you can support this project with a one-time donation or becoming a sponsor:

[![PayPal](https://img.shields.io/badge/PayPal-00457C?style=for-the-badge&logo=paypal&logoColor=white)](https://www.paypal.com/donate/?hosted_button_id=J8KS3RUFKSHDL)
[![Patreon](https://img.shields.io/badge/Patreon-F96854?style=for-the-badge&logo=patreon&logoColor=white)](https://www.patreon.com/c/zavoloklom)
[![GitHub Sponsors](https://img.shields.io/badge/GitHub%20Sponsors-171515?style=for-the-badge&logo=github&logoColor=white)](https://github.com/sponsors/docker-compose-linter)
[![Open Collective](https://img.shields.io/badge/Open%20Collective-3385FF?style=for-the-badge&logo=opencollective&logoColor=white)](https://opencollective.com/dclint)
