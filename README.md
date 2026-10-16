# Antimatter GitLab Plugin

[![Build Status](https://img.shields.io/circleci/project/github/antimatterchat/antimatter-plugin-gitlab/master.svg)](https://circleci.com/gh/antimatterchat/antimatter-plugin-gitlab)
[![Code Coverage](https://img.shields.io/codecov/c/github/antimatterchat/antimatter-plugin-gitlab/master.svg)](https://codecov.io/gh/antimatterchat/antimatter-plugin-gitlab)
[![Release](https://img.shields.io/github/v/release/antimatterchat/antimatter-plugin-gitlab)](https://github.com/antimatterchat/antimatter-plugin-gitlab/releases/latest)
[![HW](https://img.shields.io/github/issues/antimatterchat/antimatter-plugin-gitlab/Up%20For%20Grabs?color=dark%20green&label=Help%20Wanted)](https://github.com/antimatterchat/antimatter-plugin-gitlab/issues?q=is%3Aissue+is%3Aopen+sort%3Aupdated-desc+label%3A%22Up+For+Grabs%22+label%3A%22Help+Wanted%22)

A GitLab plugin for Antimatter. This plugin supports a two-way integration between Antimatter and GitLab. This plugin supports Software-as-a-Service (SaaS) or on-premises versions of GitLab.

![GitLab Plugin screenshot](https://user-images.githubusercontent.com/13119842/69115984-96b3ff80-0a58-11ea-92a3-9176b6b05a89.png)

Originally developed by [Romain Maneschi](https://github.com/manland). This project is a fork of the [antimatter-plugin-github](https://github.com/antimatterchat/antimatter-plugin-github). Thanks to all contributors of it.

See the [Antimatter Product Documentation](https://antimatter.chat/docs/admins/apps.html#integrations) for details on installing, configuring, enabling, and using this Antimatter integration.

## Feature summary of GitLab to Antimatter notifications

### Channel subscriptions

Notify your team of the latest updates by sending notifications from your GitLab group or repository to Antimatter channels. When team members log in the first time to Antimatter each day, they can get a post letting them know what issues and merge requests need their attention. They can also get a refresh of new events by selecting **Refresh** from every webhook configured in GitLab.

You can specify which events trigger a notification. They can see:

- issues - includes new and closed issues
- merges - includes new and closed merge requests
- pushes - includes pushes
- issue_comments - includes new issue comments
- merge_request_comments - include new merge-request comments
- pipeline - include pipeline
- tag - include tag creation
- pull_reviews - includes merge request reviews
- merge_request_assigns - includes merge request assignment and unassignment notifications
- label:"<labelname>" - must include "merges" or "issues" in feature list when using a label
- Defaults to "merges,issues,tag"

### Personal notifications: GitLab bot

Each user in Antimatter is connected with their own personal GitLab account. Users can get a direct message in Antimatter when someone mentions them, requests their review, comments on, or modifies one of their merge requests/issues, or assigns them on GitLab.

### Sidebar buttons

Team members can stay up-to-date with how many reviews, todos, assigned issues, and assigned merge requests they have by using buttons in the Antimatter sidebar.

## Feedback and support

Found a bug in the GitLab plugin, or missing a feature? Please [open an
issue](https://github.com/AntimatterChat/community/issues/new/choose) in the [Antimatter community
repository](https://github.com/AntimatterChat/community), where the feedback for every part of
Antimatter is gathered. Questions and ideas are welcome in its
[Discussions](https://github.com/AntimatterChat/community/discussions). Please report security
problems privately, as explained in the [security
policy](https://github.com/AntimatterChat/.github/blob/main/SECURITY.md).

## Development
  
This plugin contains both a server and web app portion. Read our documentation about the [Developer Workflow](https://antimatter.chat/docs/developers/apps.html) and [Developer Setup](https://antimatter.chat/docs/developers/building.html) for more information about developing and extending plugins.
  
### Releasing new versions

The version of a plugin is determined at compile time, automatically populating a `version` field in the [plugin manifest](plugin.json):
* If the current commit matches a tag, the version will match after stripping any leading `v`, e.g. `1.3.1`.
* Otherwise, the version will combine the nearest tag with `git rev-parse --short HEAD`, e.g. `1.3.1+d06e53e1`.
* If there is no version tag, an empty version will be combined with the short hash, e.g. `0.0.0+76081421`.

To disable this behaviour, manually populate and maintain the `version` field.

## How to Release

To trigger a release, follow these steps:

1. **For Patch Release:** Run the following command:
    ```
    make patch
    ```
   This will release a patch change.

2. **For Minor Release:** Run the following command:
    ```
    make minor
    ```
   This will release a minor change.

3. **For Major Release:** Run the following command:
    ```
    make major
    ```
   This will release a major change.

4. **For Patch Release Candidate (RC):** Run the following command:
    ```
    make patch-rc
    ```
   This will release a patch release candidate.

5. **For Minor Release Candidate (RC):** Run the following command:
    ```
    make minor-rc
    ```
   This will release a minor release candidate.

6. **For Major Release Candidate (RC):** Run the following command:
    ```
    make major-rc
    ```
   This will release a major release candidate.

