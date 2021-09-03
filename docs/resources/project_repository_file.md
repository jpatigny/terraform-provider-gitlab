# gitlab\_project\_repository_file

This resource allows you to create and manage files for your GitLab projects.
For further information on variables, consult the [gitlab
documentation](https://docs.gitlab.com/ee/api/repository_files.html#repository-files-api).

## Example Usage

```hcl
resource "gitlab_project_repository_file" "example" {
   project               = "12345"
   path                  = "project_variable_key"
   branch                = "project_variable_value"
   content               = 
   commit_message        =
   delete_commit_message = 
}
```

```hcl
resource "gitlab_project_variable" "example" {
   project               = "12345"
   path                  = "project_variable_key"
   branch                = "project_variable_value"
   content               = 
   delete_commit_message = 
}
```


## Argument Reference

The following arguments are supported:

* `project` - (Required, string) The name or id of the project to add the hook to.

* `key` - (Required, string) The name of the variable.

* `value` - (Required, string) The value of the variable.

* `variable_type` - (Optional, string)  The type of a variable. Available types are: env_var (default) and file.

* `protected` - (Optional, boolean) If set to `true`, the variable will be passed only to pipelines running on protected branches and tags. Defaults to `false`.

* `masked` - (Optional, boolean) If set to `true`, the variable will be masked if it would have been written to the logs. Defaults to `false`.

* `environment_scope` -  (Optional, string) The environment_scope of the variable. Defaults to `*`.

## Import

GitLab project variables can be imported using an id made up of `project:key:environment_scope`, e.g.

```
$ terraform import gitlab_project_variable.example '12345:project_variable_key:*'
```
