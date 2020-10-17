# playbook-k8s

## Usage

```bash
ansible-playbook main.yml --diff --ask-vault-pass
```

## Dependencies

This playbook requires the community collection "kubernetes". [Link](https://github.com/ansible-collections/community.kubernetes)

```bash
ansible-galaxy collection install -r requirements.yml
```

## Variables

### Encrypt secrets.yml

```bash
ansible-vault encrypt vars/secrets.yml
```

### Decrypt secrets.yml

```bash
ansible-vault decrypt vars/secrets.yml
```

### Secrets

```yaml
---
# traefik
traefik_pilot_token: # Token from pilot.traefik.io
cf_api_key: # API Key for Cloudflare

# minio
minio_secretkey: # Minio secret key

# kube-prometheus-stack
slack_url: https://hooks.slack.com/services/ # Slack url for alertmanager notifications

# gitlab
gitlab_runner_token: # GitLab Runner token
gitlab_sso_idp_cert: # Keycloak IDP cert
gitlab_sso_certificate: # Keycloak SAML cert
gitlab_sso_private_key: # Keycloak SAML private key
gitlab_mail_password: # SMTP password for mail delivery

# argocd
argocd_repo_password: # Password for Argo CD deployment repo
argocd_sso_client_secret: # Keycloak OIDC client secret for argocd

# k8up
k8up_restic_password: # Password for restic repository
```

### Other Variables

Change the file `vars/main.yml` accordingly.
