Copyright © 2022, Oracle and/or its affiliates.
All rights reserved. Licensed under the Universal Permissive License (UPL), Version 1.0 as shown at https://oss.oracle.com/licenses/upl.

# Instruction

## OCI-CLI Image

- The pre-built OCI-CLI image can be pull from: 

```
iad.ocir.io/idb6enfdcxbl/a2c-repo:cliv10
```

- If you want to cutomize the image to add in your prefered tools, you can edit the dockerfile and rebuild the image

```
FROM quay.io/eclipse/che-python-3.8:7.37.2

USER root

RUN apt update \
&& apt install connect-proxy -y \
&& apt install curl -y \
&& curl -fsSL https://deb.nodesource.com/setup_16.x | bash - \
&& apt install nodejs -y \
&& apt install wget -y \
&& apt install jq -y \
&& apt install zip -y \
&& apt install git -y \
&& apt install graphviz -y \
&& apt install groff -y \
&& apt install less -y \
&& apt install tree -y \
&& mkdir ~/bin \
&& curl -O https://download.docker.com/linux/static/stable/x86_64/docker-20.10.9.tgz \
&& tar -xvf docker-20.10.9.tgz \
&& mv docker/* /usr/local/bin/ \
&& wget https://releases.hashicorp.com/terraform/1.2.4/terraform_1.2.4_linux_amd64.zip \
&& unzip terraform_1.2.4_linux_amd64.zip \
&& mv terraform /usr/local/bin/ \
&& curl -LSs https://raw.githubusercontent.com/fnproject/cli/master/install | sh \
&& chmod -R 777 /home/user/.fn/* \
&& wget https://objectstorage.us-ashburn-1.oraclecloud.com/n/orasenatdpltoci01/b/A2C-Plugin/o/aliyun-cli-linux-3.0.94-amd64.tgz \
&& tar -xvf aliyun-cli-linux-3.0.94-amd64.tgz \
&& mv aliyun /usr/local/bin/ \
&& curl -O https://dl.google.com/dl/cloudsdk/channels/rapid/downloads/google-cloud-sdk-360.0.0-linux-x86_64.tar.gz \
&& tar -xvf google-cloud-sdk-360.0.0-linux-x86_64.tar.gz \
&& mv -v google-cloud-sdk/* /usr/local/bin/ \
&& chmod 555 /root


RUN pip3 install oci
RUN pip3 install oci-cli
RUN pip3 install azure-cli
RUN pip3 install awscli
RUN pip3 install fdk
RUN pip3 install requests

CMD tail -f /dev/null

```


## OKIT Image

- The pre-built OKIT image can be pull from: 

```
iad.ocir.io/idb6enfdcxbl/a2c-repo:okitv47.0
```

## CD3 Image


- The pre-built CD3 image can be pull from: 

```
iad.ocir.io/idb6enfdcxbl/a2c-repo:cd3v2'
```


