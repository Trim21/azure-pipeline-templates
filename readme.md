# a set of template for using poetry and pre-commit in azure pipeline

require poetry>=1.1.0

azure-pipeline.yaml:

```yaml
resources:
  repositories:
    - repository: trim21
      type: github
      endpoint: github
      name: Trim21/azure-pipeline-templates
      ref: refs/tags/v0.1.0
```

job:

```yaml
steps:
  - template: python/install-poetry-project.yaml@trim21
    parameters:
      python_version: "3.6"
  #   poetry_version: '1.0.5'
  #   extras: [ docs ]
  - template: python/pre-commit.yaml@trim21
```
