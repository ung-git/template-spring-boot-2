
forEach: k8s.Ingress
fileName: {{object.metadata.name}}.md
path: trouble-shooting/kubernetes/{{object.kind}}
---

#### Object: {{object.metadata.name}}
#### Type: {{object.kind}}

### Cluster에 {{object.metadata.name}} {{object.kind}}를 생성하려면 아래의 명령어를 실행하세요.

```
$ kubectl create -f {{{yamlPath}}}
```
- Yaml 파일에 명시된 스펙으로 {{object.metadata.name}} {{object.kind}}를 생성합니다.

```
$ kubectl apply -f {{{yamlPath}}}
```
- Create가 된 상태라면 {{object.metadata.name}} {{object.kind}}의 수정이 이루어지고, Create가 된 상태가 아니라면 {{object.metadata.name}} {{object.kind}}를 Create 해주는 명령어입니다.  
#

### {{object.metadata.name}} {{object.kind}}가 정상적으로 생성되었는지 확인하시려면 아래의 명령어를 실행하세요.

```
$ kubectl get ingress {{object.metadata.name}} -w

NAME      HOSTS   ADDRESS    PORTS   AGE
ingress   *       ???        80      7m36s

```
- {{object.metadata.name}} {{object.kind}}가 확인이 되신다면 정상 생성이 된 것 입니다.
> ADDRESS 부분에 값이 채워지지 않은 이유는 gateway provider가 없기 때문입니다.
>> Ingress 는 Kubernetes의 스펙일 뿐, 이를 실질적으로 지원하는 ingress controller가 필요로 합니다.  
>> 참고: https://labs.msaez.io/#/courses/cna-full/public-full-2022-hw/ops-ingress
#

### 생성된 {{object.metadata.name}} {{object.kind}}의 상세 실행 정보를 확인하시려면 아래의 명령어를 입력하세요.

```
$ Kubectl describe {{object.kind}} {{object.metadata.name}}
```
- {{object.metadata.name}} {{object.kind}}의 실행 정보 상태를 확인하여 문제가 있는지 확인합니다. 
#

### {{object.metadata.name}} {{object.kind}}를 삭제하려면 아래의 명령어를 실행하세요.

```
$ kubectl delete {{object.kind}} {{object.metadata.name}}
```
#