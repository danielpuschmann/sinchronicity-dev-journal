#Common Issues

## business-ecosystem-logic-proxy
##### Problem: Deploying the docker compose reults in Error:  The specified product id is not indexed undefined
Current workaround:
Retry docker-compose down & docker-compose up -d until error no longer appears
Suspected issue: race condition when creating the indexes. 



## Marketplace portal
##### Problem: The user making the request and the specified owner are not the same user
Suggested Solution:
Check that `docker/compose/proxy_conf/config.js` is consistent regarding ports 
and https/http

---

##### Problem: The server has failed validating the product specification
Suggested Solution:
Verify WILMA is configured correctly and running. If using https for idm, use port
 `443` instead of `3000` in the configuration

---

##### Image upload/use url for image in data source specification does not work
Add this line to  entrypoint.sh in the charging backend:
`Chmod -R 777 media`

---

##### When users sign in, they get the following error: `There was an unexpected error that prevented the system from fulfilling the request. The error will be handled by the administrators. Sorry for the inconvenience.`

Use stable keyrock/keystone docker image, not latest

---
