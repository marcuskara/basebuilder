#Grails 3.x platform
Deploy:
```bash
grails clean
grails package
```

Start:
```bash
java -Dgrails.env=prod -jar build/libs/current-${GRAILS_APP_VERSION}.jar --server.host=0.0.0.0 --server.port=${PORT}
```

NB. ${GRAILS_APP_VERSION} is set based on gradle properties
