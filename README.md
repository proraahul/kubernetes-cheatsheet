# ☸️ Kubernetes Cheatsheet

## 🧵 Basic kubectl Commands
| Description                          | Command                                      |
|--------------------------------------|----------------------------------------------|
| View cluster info                    | `kubectl cluster-info`                       |
| List all nodes                       | `kubectl get nodes`                          |
| Get detailed info about a node       | `kubectl describe node [NODE_NAME]`          |
| View client and server versions      | `kubectl version`                            |

## 📦 Pods
| Description                          | Command                                      |
|--------------------------------------|----------------------------------------------|
| List all pods                        | `kubectl get pods`                           |
| List pods in a namespace             | `kubectl get pods -n [NAMESPACE]`            |
| Describe a pod                       | `kubectl describe pod [POD_NAME]`            |
| Delete a pod                         | `kubectl delete pod [POD_NAME]`              |
| Execute command in a pod             | `kubectl exec -it [POD_NAME] -- [COMMAND]`   |
| View logs of a pod                   | `kubectl logs [POD_NAME]`                    |

## 📁 Deployments
| Description                          | Command                                      |
|--------------------------------------|----------------------------------------------|
| Create deployment                    | `kubectl create deployment [NAME] --image=[IMAGE]` |
| Get deployments                      | `kubectl get deployments`                    |
| Describe a deployment                | `kubectl describe deployment [NAME]`         |
| Update image in deployment           | `kubectl set image deployment/[NAME] [CONTAINER]=[NEW_IMAGE]` |
| Scale a deployment                   | `kubectl scale deployment [NAME] --replicas=[COUNT]` |
| Delete a deployment                  | `kubectl delete deployment [NAME]`           |

## 🌐 Services
| Description                          | Command                                      |
|--------------------------------------|----------------------------------------------|
| List services                        | `kubectl get services`                       |
| List services                        | `kubectl get svc`                       |
| Expose deployment as a service       | `kubectl expose deployment [NAME] --type=[TYPE] --port=[PORT]` |
| Describe a service                   | `kubectl describe service [NAME]`            |
| Delete a service                     | `kubectl delete service [NAME]`              |

## 📄 ConfigMaps & Secrets
| Description                          | Command                                      |
|--------------------------------------|----------------------------------------------|
| Create configmap from file           | `kubectl create configmap [NAME] --from-file=[FILE]` |
| List configmaps                      | `kubectl get configmaps`                     |
| Create a secret                      | `kubectl create secret generic [NAME] --from-literal=[KEY]=[VALUE]` |
| List secrets                         | `kubectl get secrets`                        |

## 📚 Namespaces
| Description                          | Command                                      |
|--------------------------------------|----------------------------------------------|
| List all namespaces                  | `kubectl get namespaces`                     |
| Create a namespace                   | `kubectl create namespace [NAME]`            |
| Delete a namespace                   | `kubectl delete namespace [NAME]`            |
| Use a specific namespace             | `kubectl config set-context --current --namespace=[NAME]` |

## 🧪 Troubleshooting & Debugging
| Description                          | Command                                      |
|--------------------------------------|----------------------------------------------|
| Get events                           | `kubectl get events`                         |
| Describe any resource                | `kubectl describe [RESOURCE] [NAME]`         |
| View pod logs                        | `kubectl logs [POD_NAME]`                    |
| Run a temporary pod for debugging    | `kubectl run -i --tty debug --image=busybox --restart=Never -- sh` |

## 🛠️ Apply & Manage Manifests
| Description                          | Command                                      |
|--------------------------------------|----------------------------------------------|
| Apply a manifest file                | `kubectl apply -f [FILE]`                    |
| Delete resources from manifest       | `kubectl delete -f [FILE]`                   |
| Dry run a manifest                   | `kubectl apply --dry-run=client -f [FILE]`   |
| Diff changes before applying         | `kubectl diff -f [FILE]`                     |

## 🔎 Misc & Utilities
| Description                          | Command                                      |
|--------------------------------------|----------------------------------------------|
| Get all resources                    | `kubectl get all`                            |
| Get resource by label                | `kubectl get pods -l [LABEL_KEY]=[VALUE]`    |
| View resource YAML                   | `kubectl get [RESOURCE] [NAME] -o yaml`      |
| Explain a resource                   | `kubectl explain [RESOURCE]`                 |

## 🔎 Create Image to Pod
| `kubectl run podName --image imageName:1.0 --port=80` |

## Expose service port 
| `kubectl expose pod podName --name=servicename --port=80` | 

## Port forwading connect service to pod
|  `kubectl port-forward service/serviceName 7080:80`


---

✅ **Tip**: Use `-n [NAMESPACE]` to target a specific namespace and `-o wide` for extended output.
