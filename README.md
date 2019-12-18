# Cloud Foundry Container Runtime
A [BOSH](http://bosh.io/) release for [Kubernetes](http://kubernetes.io).  Formerly named **kubo**.

- **Slack**: #cfcr on https://slack.cloudfoundry.org
- **Pivotal Tracker**: https://www.pivotaltracker.com/n/projects/2093412
- **The original CFCR readme file**: https://github.com/cloudfoundry-incubator/kubo-release/tree/v0.34.0


<!-- vscode-markdown-toc-config
	numbering=true
	autoSave=true
	/vscode-markdown-toc-config -->
<!-- /vscode-markdown-toc -->

## <a name='UsagePaasta'></a>Usage for PaaS-TA Container Service

For applying release to PaaS-TA Container Service, please create release by apply the version and syncronize with that service configuration.
This is a customized kubo-release version for PaaS-TA Container Service Project based on kubo-release(ver 0.34.0).

`bosh create-release --force --tarball ./releases/kubo-release-0.34.1.tgz --name kubo --version 0.34.1`

### List of files changed in this version(for PaaS-TA Container Service).

##### 1. Added files for specific jobs as route settup, agent install and etc.
- jobs/kube-apiserver/templates/bin/pre-start.erb
- jobs/kubelet/templates/bin/post-deploy.erb
- jobs/kubelet/templates/bin/pre-start.erb
- jobs/prometheus/templates/bin/prometheus/install-helm.sh
- jobs/prometheus/templates/bin/post-deploy.erb
- jobs/prometheus/templates/bin/post-deploy.erb.bak
- jobs/prometheus/monit
- jobs/prometheus/spec

##### 2. Modified files for specific jobs for corresponding to infrastructure environments.
- jobs/kube-apiserver/templates/config/bpm.yml.erb
- jobs/kube-apiserver/spec
- jobs/kube-controller-manager/templates/config/cloud-provider.ini.erb
- jobs/kube-controller-manager/templates/config/openstack-ca.crt.erb
- jobs/kube-controller-manager/templates/config/service_key.json.erb
- jobs/kube-proxy/templates/bin/kube_proxy_ctl.erb
- jobs/kubelet/templates/bin/kubelet_ctl.erb
- jobs/kubelet/templates/bin/post-start.erb
- jobs/kubelet/templates/config/cloud-provider.ini.erb
- jobs/kubelet/templates/config/openstack-ca.crt.erb
- jobs/kubelet/templates/config/service_key.json.erb
