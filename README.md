# ROS2 Pre-commit

Here are some out of the box [pre-commit](https://pre-commit.com/) hooks focused on ROS2 workspaces.

Example:

```yaml
  - repo: https://github.com/minipada/ros2_pre-commit.git
    rev: main
    hooks:
      - id: ros2_ws_same_versions
        args: [--src=., --regex=dc_.*]
      - id: ros2_ws_set_metadata
        args: [--src=., --regex=dc_.*]

```

## Same version
Ensure all packages in the workspace are of the same version. This is needed for bloom releases.

`ros2_ws_same_versions`

Parameters:

| Parameter name | Description                               | Default value   |
| -------------- | ----------------------------------------- | --------------- |
| src            | Define the source of the files to inspect | None (required) |
| regex          | Packages inspected will match this regex  | None (Optional) |

## Metadata set
Ensure all metadata is set in package.xml: author, license and description.

`ros2_ws_set_metadata`

Parameters:

| Parameter name | Description                               | Default value   |
| -------------- | ----------------------------------------- | --------------- |
| src            | Define the source of the files to inspect | None (required) |
| regex          | Packages inspected will match this regex  | None (Optional) |
