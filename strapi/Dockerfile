ARG BASE_VERSION
FROM strapi/base:${BASE_VERSION}

ARG STRAPI_VERSION
RUN yarn global add strapi@${STRAPI_VERSION}

WORKDIR /srv/app

VOLUME /srv/app

COPY server.json /srv/app/config/production/
COPY server.json /srv/app/config/development/

COPY docker-entrypoint.sh /usr/local/bin/
ENTRYPOINT ["docker-entrypoint.sh"]

ENV NODE_ENV=development

CMD ["strapi", "develop"]
