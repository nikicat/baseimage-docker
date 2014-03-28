FROM racker/precise-with-updates
MAINTAINER Phusion <info@phusion.nl>

ENV HOME /root
RUN mkdir /build
ADD . /build

RUN bash /build/prepare.sh && \
	bash /build/system_services.sh && \
	bash /build/utilities.sh && \
	bash /build/cleanup.sh

CMD ["/sbin/my_init"]
