FROM registry.access.redhat.com/ubi8/ubi-minimal

MAINTAINER `team-validated-patterns@redhat.com`

USER root

RUN microdnf install --disableplugin=subscription-manager --nodocs jq tar gzip -y && \
    curl -LfO https://mirror.openshift.com/pub/openshift-v4/clients/ocp/stable/openshift-client-linux.tar.gz && \
    tar xvf openshift-client-linux.tar.gz -C /usr/local/bin/ && \
    chmod 755 /usr/local/bin/oc && \
    rm -rf openshift-client-linux.tar.gz && \
    microdnf clean all && \
    rm -rf /var/run/cache

USER 1001
