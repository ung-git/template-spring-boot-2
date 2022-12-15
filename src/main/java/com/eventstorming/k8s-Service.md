forEach: k8s.Service
fileName: Test.md
---

# h1 Heading 8-)
## h2 Heading
### h3 Heading
#### h4 Heading
##### h5 Heading
###### h6 Heading


Trouble-Shooting for Kubernetes
the YAML for such application should look similar to this :

apiVersion: "v1"
kind: "{{object.kind}}"
metadata: 
  name: "{{metadata.name}}"
  labels: 
    app: "dashboard"
spec: 
  ports: 
    - 
      port: 8080
      targetPort: 8080
  selector: 
    app: "dashboard"



## Horizontal Rules

