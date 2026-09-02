# gel

A Helm chart for deploying the Gel graph database.

**Homepage:** <https://github.com/giantswarm/gel-app>

## Source Code

* <https://github.com/edgedb/edgedb>
* <https://github.com/Japan7/nanak8s/tree/main/charts/edgedb>

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| name | string | `"gel"` |  |
| serviceType | string | `"managed"` |  |
| replicaCount | int | `1` |  |
| image.registry | string | `"gsoci.azurecr.io"` |  |
| image.name | string | `"giantswarm/gel"` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.tag | string | `""` |  |
| imagePullSecrets | list | `[]` |  |
| nameOverride | string | `""` |  |
| fullnameOverride | string | `""` |  |
| gel.args[0] | string | `"--enable-backend-adaptive-ha"` |  |
| gel.backend.secretName | string | `"gel-postgres-superuser"` |  |
| gel.container.port | int | `5656` |  |
| gel.container.portName | string | `"gel"` |  |
| gel.security.tls.enabled | bool | `true` |  |
| gel.security.tls.issuerName | string | `"selfsigned-giantswarm"` |  |
| gel.security.tls.secretName | string | `"gel-tls"` |  |
| gel.security.serverPassword.secretName | string | `"gel-server-password"` |  |
| postgres.cnpg.enabled | bool | `true` |  |
| postgres.cnpg.instances | int | `2` |  |
| postgres.cnpg.storage.size | string | `"1Gi"` |  |
| postgres.cnpg.monitoring.podMonitor.enabled | bool | `true` |  |
| postgres.cnpg.monitoring.podMonitor.labels | object | `{}` |  |
| postgres.cnpg.imageCatalogRef.major | int | `16` |  |
| postgres.cnpg.imageCatalogRef.name | string | `"gs-postgresql"` |  |
| postgres.cnpg.switchoverDelay | int | `60` |  |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.annotations | object | `{}` |  |
| serviceAccount.name | string | `""` |  |
| monitoring.serviceMonitor.enabled | bool | `true` |  |
| monitoring.podLogs.enabled | bool | `true` |  |
| monitoring.podLogs.tenant | string | `"giantswarm"` |  |
| monitoring.podLogs.labels | object | `{}` |  |
| monitoring.podLogs.annotations | object | `{}` |  |
| monitoring.podLogs.relabelings | list | `[]` |  |
| podAnnotations | object | `{}` |  |
| podSecurityContext.runAsGroup | int | `1000` |  |
| podSecurityContext.runAsNonRoot | bool | `true` |  |
| podSecurityContext.runAsUser | int | `1000` |  |
| podSecurityContext.seccompProfile.type | string | `"RuntimeDefault"` |  |
| securityContext.allowPrivilegeEscalation | bool | `false` |  |
| securityContext.capabilities.drop[0] | string | `"ALL"` |  |
| securityContext.privileged | bool | `false` |  |
| securityContext.runAsNonRoot | bool | `true` |  |
| securityContext.seccompProfile.type | string | `"RuntimeDefault"` |  |
| service.type | string | `"ClusterIP"` |  |
| service.port | int | `5656` |  |
| service.portName | string | `"gel"` |  |
| networkPolicy.enabled | bool | `true` |  |
| ciliumNetworkPolicy.enabled | bool | `true` |  |
| resources.limits.cpu | int | `1` |  |
| resources.limits.memory | string | `"2048Mi"` |  |
| resources.requests.cpu | string | `"250m"` |  |
| resources.requests.memory | string | `"1024Mi"` |  |
| autoscaling.enabled | bool | `false` |  |
| autoscaling.minReplicas | int | `1` |  |
| autoscaling.maxReplicas | int | `100` |  |
| autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| vpa.enabled | bool | `false` |  |
| vpa.containerPolicies.minAllowed.cpu | string | `"250m"` |  |
| vpa.containerPolicies.minAllowed.memory | string | `"1024Mi"` |  |
| nodeSelector | object | `{}` |  |
| tolerations | list | `[]` |  |
| affinity | object | `{}` |  |
