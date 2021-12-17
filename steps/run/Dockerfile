FROM docker.io/relaysh/bolt-step-run

RUN apt-get update && \
    apt-get install --no-install-recommends -y unzip && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# AWS cli
RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" && \
    unzip awscliv2.zip && ./aws/install && rm awscliv2.zip

# Packer
RUN curl "https://releases.hashicorp.com/packer/1.7.8/packer_1.7.8_linux_amd64.zip" -o "packer.zip" && \
    unzip packer.zip && mv packer /usr/local/bin/packer && rm packer.zip

# kubectl
RUN curl -LO "https://dl.k8s.io/release/v1.22.0/bin/linux/amd64/kubectl" && \
    chmod +x kubectl && mv kubectl /usr/local/bin/kubectl

# kOps
RUN curl -L "https://github.com/kubernetes/kops/releases/download/v1.22.2/kops-linux-amd64" -o "kops" && \
    chmod +x kops && mv kops /usr/local/bin/kops

