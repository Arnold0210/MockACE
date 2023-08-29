# MockACE
Ejercicio de versionamiento y CI/CD utilizando contenedores.


Para levantar el docker compose ejecutar el siguiente comando:

docker compose up -d
-------------------------------------
Para bajar imagenes de ACE de MQ ingresar al [Registry de IBM](https://www.ibm.com/docs/en/app-connect/containers_cd?topic=obtaining-app-connect-enterprise-server-image-from-cloud-container-registry) para ver la versión

Para poder descargar la versión de servidor se debe loguear al Registry de IBM
docker docker login cp.icr.io -u cp -p myEntitlementKey
docker pull imageLocation
-------------------------------------
Imagen de ACE usada en el laboratorio:

docker run --name aceserver -p 7600:7600 -p 7800:7800 -p 7843:7843 --env LICENSE=accept --env ACE_SERVER_NAME=ACESERVER cp.icr.io/cp/appc/ace-server-prod@sha256:246828d9f89c4ed3a6719cd3e4b71b1dec382f848c9bf9c28156f78fa05bc4e7

Imagen de MQ usada en el laboratorio:
[mqserver:V0](https://hub.docker.com/layers/arnold9810/mqserver/V0/images/sha256-3558442d36a9fe730a1f832eba45e122829f5ab6b36cc3bb88eed29e65d0a02e?context=explore)

docker run --env LICENSE=accept --env MQ_QMGR_NAME=[MQDEV]--volume [VMQ]:/mnt/mqm --publish 1414:1414 --publish 9443:9443 --detach --env MQ_APP_PASSWORD=[password] --env MQ_ADMIN_PASSWORD=[password] --name mqdev arnold9810/mqserver:V0