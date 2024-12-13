Thanks Jason, Sharlene, Oliver & Preacta for that awesome meetup. I was thinking to myself it would be useful to try and capture some of the questions that were asked during. So, in no particular order....

During discussions about multi-cluster management, several key points emerged:

Someone from Redhat initiated a discussion about multi-cluster service management and [Argo](https://argoproj.github.io/) integration accross multiple large clusters. In general the conversation covered various multi-cloud/multi-cluster solutions:

- The [Cluster API](https://cluster-api.sigs.k8s.io/) (part of CNCF's Cluster Lifecycle SIG) has implementations across major cloud providers:
  - [AWS Cluster API](https://cluster-api-aws.sigs.k8s.io/)
  - [Google GCP Cluster API](https://github.com/kubernetes-sigs/cluster-api-provider-gcp)
  - [Microsoft Azure Cluster API](https://capz.sigs.k8s.io/)
  - [Redhat OpenShift Cluster API](https://github.com/openshift/cluster-api-provider-openshift)

- ByteDance (TikTok's parent company) recently contributed [KubeAdmiral](https://github.com/kubewharf/kubeadmiral), their open-source multi-cluster solution, as mentioned in [CNCF blog posts](https://www.cncf.io/blog/2023/08/08/kubeadmiral-a-reliable-multi-cluster-solution/).

Regarding [Argo Rollouts](https://argoproj.github.io/argo-rollouts/), two main topics were discussed:

1. Complex pre/post evaluation rules:
   - Question focused on handling complex evaluations involving multiple data points converging to a single metric/decision
   - Solution identified: [Prometheus Recording Rules](https://prometheus.io/docs/prometheus/latest/configuration/recording_rules/) can handle complex PromQL queries that need to be expressed as single query calls

2. Traffic shifting and progressive rollouts:
   - [CNCF OpenFeature](https://openfeature.dev/) project was tangentally referenced in this context

On metrics collection, discussion covered Argo components' observability:
- Argo emits standard cloud-native service metrics
- Notable trend: [Prometheus](https://prometheus.io/) and similar tools are increasingly adopting [OpenTelemetry](https://opentelemetry.io/) standards