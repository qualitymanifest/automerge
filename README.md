# automerge

### SECRETS
- `AUTOMERGE_TOKEN`: A GitHub personal access token (PAT). This is needed in order for recursive merge to work, e.g. merging into 1.0.0 merges into 1.1.0, triggering another merge of 1.1.0 into 1.2.0, etc. See [here](https://docs.github.com/en/actions/writing-workflows/choosing-when-your-workflow-runs/triggering-a-workflow#triggering-a-workflow-from-a-workflow)
    - This should be a fine-grained PAT, scoped to this repository
    - PAT should be set to never expire
    - Under "Permissions" -> "Repository permissions", set:
        - "Contents": "Read and write"
        - "Secrets": "Read-only"
        - "Variables": "Read-only"

### VARIABLES
- `SKIP_AUTOMERGE_GTE_VERSION`: If present, don't try to auto-merge into a release branch where the version is greater than this version
    - Example: 2.0.0