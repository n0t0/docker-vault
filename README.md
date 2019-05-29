WIN

- AUDIT --> every request and response from Vault 
- unseal 3 keys shares --> managers / KM (shamir's secret sharing)
- dynamic secrets / static secrets
- leases and revocation
- CLI, HTTP API, UI --> work with secrets
- ENCRYPTION
- backend storage
- custome lease period


How apps get secrets?
How are they updated?
How are they revoked?

### Install

$ mkdir -p vault/{config,data,logs,policies}

### Auth Methods - configure a AppRole

$ vault auth enable approle

$ vault write auth/approle/role/<application-role> \
    secret_id_ttl=10m \
    token_num_uses=10 \
    token_ttl=20m \
    token_max_ttl=30m \
    secret_id_num_uses=40

$ vault read auth/approle/role/<application-role>/role-id

