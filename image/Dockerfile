FROM racker/precise-with-updates
MAINTAINER Phusion <info@phusion.nl>

ENV HOME /root
RUN mkdir /build
ADD . /build

# HACK: quay.io drops permissions and ownership because of using zip archives
RUN bash -c 'chmod +x /build/{*.sh,enable_insecure_key,my_init,setuser,runit/*} && chown -R root:root /build'

RUN /build/prepare.sh && \
	/build/system_services.sh && \
	/build/utilities.sh && \
	/build/cleanup.sh

CMD ["/sbin/my_init"]
