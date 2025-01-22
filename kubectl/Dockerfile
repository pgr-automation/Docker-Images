# Use an official lightweight image as the base
FROM alpine:3.18

# Set environment variables
ENV KUBECTL_VERSION=v1.28.0

# Install kubectl and necessary dependencies
RUN apk add --no-cache curl bash && \
    curl -LO "https://dl.k8s.io/release/${KUBECTL_VERSION}/bin/linux/amd64/kubectl" && \
    chmod +x kubectl && \
    mv kubectl /usr/local/bin/

# Set a working directory
WORKDIR /root
RUN mkdir .kube
ADD ./config /root/.kube/config

# Allow bash shell entry
CMD ["sh"]

