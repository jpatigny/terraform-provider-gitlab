# gitlab\_branch

This resource allows you to create and manage branches for a gitlab project.

## Example Usage

```hcl
resource "gitlab_branch" "example" {
  name = "branch-name"
  project = "12345"
  ref = "existing-branch"
}
```

## Argument Reference

The following arguments are supported:

* `name` - (Required) The name of the branch.

* `project` - (Required) The full path of the group.

* `ref` - (Optional) The ref you branch from. Defaults to `master`

## Attributes Reference

The resource exports the following attributes:

* `web_url` - The url of the created branch (https)
* `default` - Bool, true if branch is the default branch for the project
* `can_push` - Bool, true if you can push to the branch
* `merged` - Bool, true if the branch has been merged into it's parent
* `commit` - The list of group members.
  * `id` - The unique id assigned to the commit by gitlab.
  * `short_id` - The short id assigned to the commit by gitlab
  * `author_email` - The email of the author.
  * `author_name` - The name of the author.
  * `authored_date` - The date which the commit was authored
  * `commited_date` - The date at which the commit was pushed.
  * `committer_email` - The email of the user that committed.
  * `commiter_name` - The name of the user that committed.
  * `title` - The title of the commit
  * `message` - The commit message
  * `parent_ids` - The id of the parents of the commit