# git-auto-tagger

Tag commits based on the commit message. Useful if you rebase often and don't want to manually clean up tags every time.

I'm using this for a workshop I run. Attendees check out code at phases and I rebase often to keep the history clean.

> **WARNING**: This will delete any existing local and remote tags.
> Make sure **all** the tags you want to keep are in the YAML file.

## Requirements

Ruby 3.1.2

## Usage

1. Add a `.tags.yml` file to your project
1. Run `./auto-tag.sh` from your project's directory

## `.tags.yml` format

```yaml
- tag: TAG_NAME
  commit: COMMIT_MESSAGE
  message: OPTIONAL_TAG_ANNOTATION
```

For example:

```yaml
- tag: 0.1.0
  commit: Set version to 0.1.0
- tag: 0.2.0
  commit: Bump minor version
  message: Add dynamic indexing
```

1. Finds the 'Set version to 0.1.0' commit and sets the tag to '0.1.0'.
1. Finds the 'Bump minor version' commit and sets the tag to '0.2.0' with a message."
