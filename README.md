# k8s-pod-availability-alert

**Overview**
This project demonstrates production-grade pod monitoring using Prometheus and Kubernetes metrics. It establishes a reliable alerting pipeline to track workload health and minimize service downtime.

**Technical Stack**
Orchestration: Kubernetes (Kind)
Monitoring: Prometheus Operator
Metrics: kube-state-metrics

**Alerting Logic**
The system monitors pod readiness and triggers an alert if a pod remains NotReady for over one minute. By utilizing a for condition in the alert rule, I have reduced alert noise and filtered out transient issues that do not require manual intervention.

**Testing Procedure**
Deploy: kubectl apply -f manifests/hello-app.yaml
Simulate Failure: kubectl scale deployment hello-app --replicas=0
Verify: Monitor the Prometheus UI to confirm the alert transitions to a firing state.

**Key SRE Concepts**
PromQL: Targeted metric querying.
Noise Reduction: Preventing alert fatigue through duration thresholds.
Observability: Implementing actionable monitoring for cluster health.
