FROM quay.io/roboll/helmfile:helm3-v0.119.0
WORKDIR /

RUN apk add --no-cache docker \
      terraform \
      python \
      py-pip && \
      pip install awscli --upgrade --user && \
      mv /root/.local/bin/* /usr/local/bin && \
      apk -v --purge del py-pip && \
      curl -o /usr/local/bin/aws-iam-authenticator https://amazon-eks.s3.us-west-2.amazonaws.com/1.16.8/2020-04-16/bin/linux/amd64/aws-iam-authenticator && \
      chmod +x /usr/local/bin/aws-iam-authenticator

COPY coopctl /usr/local/bin/coopctl
ADD VERSION .
