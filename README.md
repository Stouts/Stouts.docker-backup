Stouts.docker-backup
====================

Ansible role to backup docker volumes

#### Variables

```yaml
docker_backup_enabled: true                     # Is the role enabled
docker_backup_image: blacklabelops/volumerize   # Backup image
docker_backup_target: "file:///backup"          # Backup target (AWS, Google, Dropbox)
docker_backup_name: backup
docker_backup_env: {}
docker_backup_volumes: []
docker_backup_restore: []

docker_backup_aws_access_key: ""
docker_backup_aws_secret_access_key: ""

docker_backup_google_drive_id: ""
docker_backup_google_drive_secret: ""

docker_backup_dropbox_access_token: ""
```

#### Usage

Add `Stouts.docker-backup` to your roles and set vars in your playbook file.

Example:

```yaml

- hosts: all

  roles:
    - Stouts.docker-backup

  vars:  # Example for AWS
    docker_backup_volumes: [db-data, app-data]
    docker_backup_target: "s3://..."
    docker_backup_aws_access_key: "..."
    docker_backup_aws_secret_access_key: "..."
```

#### License

Licensed under the MIT License. See the LICENSE file for details.

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Stouts/Stouts.docker-backup/issues)!

