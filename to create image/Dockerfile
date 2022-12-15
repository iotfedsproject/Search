FROM openjdk:8-jre-alpine

WORKDIR /home

ENV componentName "Search"
ENV componentVersion 3.0.13

#RUN apk --no-cache add \
	#git \
	#unzip \
	#wget \
	#bash \
	#&& echo "Downloading $componentName $componentVersion" \
	#&& wget "https://jitpack.io/com/github/symbiote-h2020/$componentName/$componentVersion/$componentName-$componentVersion-run.jar"

EXPOSE 8120

COPY ./Search-0.1.0-SNAPSHOT-run.jar Search-0.1.0-SNAPSHOT-run.jar
CMD java $JAVA_HTTP_PROXY $JAVA_HTTPS_PROXY $JAVA_NON_PROXY_HOSTS -DSPRING_BOOT_WAIT_FOR_SERVICES=symbiote-coreinterface:8100  -Xmx1024m -Duser.home=/home -Dspring.output.ansi.enabled=NEVER -jar $(ls *.jar)
