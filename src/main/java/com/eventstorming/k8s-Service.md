forEach: k8s.Service
fileName: {{object.metadata.name}}.md
path: k8s/service
---

# h1 Heading 8-)
## h2 Heading
### h3 Heading
#### h4 Heading
##### h5 Heading
###### h6 Heading


Trouble-Shooting for Kubernetes
the YAML for such application should look similar to this :
```yaml
apiVersion: "v1"
kind: "{{object.kind}}"
metadata: 
  name: "{{object.metadata.name}}"
  labels: 
    app: "{{object.metadata.name}}"
spec: 
  ports: 
    - 
      port: 8080
      targetPort: 8080
  selector: 
    app: "dashboard"
```


## Horizontal Rules

