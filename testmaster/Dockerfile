FROM ubuntu:bionic

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \
    munin && \
    mkdir -p /var/run/munin && chown -R munin:munin /var/run/munin
    # otherwise I get "Failed to create rundir (/var/run/munin): Permission denied at /usr/share/munin/munin-update line 39."

ADD ./munin.conf /etc/munin/munin.conf

RUN /bin/echo -e "#!/bin/bash\nsleep 5\nsu - munin --shell=/bin/bash -c \"/usr/share/munin/munin-update --nofork --debug\"\nsleep Inf" > /start.sh && chmod a+x /start.sh

CMD [ "/start.sh" ]
