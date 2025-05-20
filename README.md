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
    rev: v2.2.1  # Matches the dclint version, use the sha or tag you want to point at
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
  rev: v2.2.1 # Matches the dclint version, use the sha or tag you want to point at
  hooks:
    - id: dclint-docker
      # Optional: regex override for compose files
      files: ^(docker-)?compose\.ya?ml$
      # Optional: enable autofix on commit
      args: [--fix]
```

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

Also, you can support this project with a donation:

[![PayPal](https://img.shields.io/badge/PayPal-00457C?style=for-the-badge&logo=paypal&logoColor=white)](https://www.paypal.com/donate/?hosted_button_id=ZKLT8EJ4KWA6L)
[![BuyMeACoffee](https://img.shields.io/badge/Buy%20Me%20a%20Coffee-ffdd00?style=for-the-badge&logo=buy-me-a-coffee&logoColor=black)](https://www.buymeacoffee.com/zavoloklom)

