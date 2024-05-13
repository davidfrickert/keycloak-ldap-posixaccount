# keycloak-ldap-posixaccount

This is a Keycloak extension to support creating LDAP Users of class `posixAccount`. This class requires `uidNumber`, `gidNumber` and `homeDirectory` attributes set. Also, the class `posixAccount` must be set as Keycloak does not do it by default.

## Usage

Package the jar by running the following makefile command:

```bash
make clean_build
# or 
make build
```

Alteratively, maven can be used directly as well:
```bash
mvn package
```

Next, copy the jar file from the `target` directory to the `/opt/keycloak/providers/` directory and restart Keycloak. You can then add a mapper in the LDAP user federation of the type `keycloak-ldap-posixaccount` and configure the first UID to use for new users.