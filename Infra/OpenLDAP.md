- Package with CLI utils for Debian: `ldap-utils`


- When connecting from another docker container, should apply docker service host `openldap` along with expose port `1389` 

- Search query example:
```bash
ldapsearch -H ldap://localhost:389 -D cn=admin,o=my,dc=local -w password -b ou=Users,o=my,dc=local -LLL "(&(objectClass=inetOrgPerson)(mail=bob@my.local))"
```

- To search query with hidden entity attributes, add `+` sign in the end of the query:
```bash
ldapsearch -H ldap://127.0.0.1:389 -D cn=admin,o=my,dc=local -w password -b ou=Users,o=my,dc=local +
```



