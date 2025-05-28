# Install Role

## Repository
Develop role as a single projet and publish it in a git repository.

Ansible can download role from source or a release.

## Release
```
tar cvzf pythonapi-role.tar.gz apipython/
```
Publish release somewhere.

## Install custom role
Describe source with a requirements.yml

```
ansible-galaxy role install -r requirements.yml
```

## Install role from community
```
ansible-galaxy role install semihamurcu.db
```

