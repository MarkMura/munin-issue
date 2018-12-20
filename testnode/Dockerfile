FROM ubuntu:bionic

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \
    munin-node

ADD ./munin-node.conf /etc/munin/munin-node.conf

RUN /bin/echo -e "#!/bin/bash\nservice munin-node start\nsleep Inf" > /start.sh && chmod a+x /start.sh

CMD [ "/start.sh" ]
