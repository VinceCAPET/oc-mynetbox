FROM python-s2i

USER 0

#This system is not registered with an entitlement server. You can use subscription-manager to register.
#RUN yum -y install graphviz && yum clean all -y
#RUN yum install -y redis

RUN mv $STI_SCRIPTS_PATH/assemble $STI_SCRIPTS_PATH/assemble-base
COPY s2i/assemble.sh $STI_SCRIPTS_PATH/assemble
COPY s2i/run.sh $STI_SCRIPTS_PATH/run
RUN chmod +x $STI_SCRIPTS_PATH/*

COPY netbox/settings.py /opt/app-root/etc/
COPY netbox/openshift_urls.py /opt/app-root/etc/
COPY netbox/openshift_middleware.py /opt/app-root/etc/
COPY netbox/openshift_auth.py /opt/app-root/etc/

USER 1001

