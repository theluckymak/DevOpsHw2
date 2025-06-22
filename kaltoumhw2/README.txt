mohamed amine kaltoum
Этот Dockerfile создаёт пользовательский образ на основе Ubuntu  с установленными Apache и MySQL.
В нём используются все требуемые инструкции: FROM, MAINTAINER, RUN, CMD, WORKDIR, ENV, ADD, COPY, VOLUME, USER, EXPOSE.
Apache обслуживает статический сайт из папки website.
MySQL сохраняет данные в Docker-томе.
Слои образа были просмотрены с помощью команды:
docker image history --no-trunc kaltoum_k_image_2025-06-22
