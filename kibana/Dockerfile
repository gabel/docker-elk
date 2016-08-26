FROM kibana:latest

RUN apt-get update && apt-get install -y netcat

COPY entrypoint.sh /tmp/entrypoint.sh
RUN chmod +x /tmp/entrypoint.sh

RUN which kibana

RUN wget https://download.elasticsearch.org/elastic/sense/sense-latest.tar.gz -P /tmp \
    && kibana plugin -i sense -u file:///tmp/sense-latest.tar.gz

#RUN kibana plugin --install elastic/sense

CMD ["/tmp/entrypoint.sh"]
