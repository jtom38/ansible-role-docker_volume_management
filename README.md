# docker_volume_backup

This role helps with making backups of your docker volumes for you.

## Requirements

This role makes use of the docker cli tool.  It will install it for ubuntu currently with apt.

## Variables

``` yaml

# Required
# Defines what container to look for to copy the mount points for the backup job.
container_name: string

# Required
# Defines the mount point from within the container that we are going to make a backup of.
mount_point: string

# Required
# Defines where on the host device we are going to place the tar file.
backup_location: string

# Required
# Defines the name of the tar file.  
tar_file: string

```

## Examples

``` yaml

- include_role:
    name: docker_volume_backup
  vars:
    container_name: 'ubuntu'
    mount_point: '/data'
    backup_location: '~/backup'
    tar_file: ubuntuData.tar

```
