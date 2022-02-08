### ACL Policy:
```sh
path "secret/*" {
  capabilities = ["create","read","update","delete"]
}
```
### Create a new Role with associated policy:
```sh
vault write auth/approle/role/<ROLE NAME> token_policies="<POLICY>"
```
### Fetch Information About Role:
```sh
vault read auth/approle/role/<ROLE NAME>
```
### Fetch the Role ID
```sh
vault read auth/approle/role/<ROLE NAME>/role-id
```
### Fetch the Role ID
```sh
vault write -f auth/approle/role/<ROLE NAME>/secret-id
```
### Authenticate with AppRole
```sh
vault write auth/approle/login role_id="<ROLE-ID>" secret_id="<YSECRET-ID>"
```
