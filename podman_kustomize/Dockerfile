FROM mattermost/podman:1.8.0 AS downloader

WORKDIR /downloads

RUN curl -s "https://raw.githubusercontent.com/kubernetes-sigs/kustomize/master/hack/install_kustomize.sh"  | bash
############ [Production] #####################
### Runtime
FROM downloader AS production

ENV TZ=Asia/Seoul
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
COPY --from=downloader /downloads/kustomize /usr/local/bin/kustomize


#FROM mattermost/podman:1.8.0

# WORKDIR /downloads

#RUN curl -s "https://raw.githubusercontent.com/kubernetes-sigs/kustomize/master/hack/install_kustomize.sh"  | bash

#ENV TZ=Asia/Seoul
#RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

#COPY kustomize /usr/local/bin/kustomize
