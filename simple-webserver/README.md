# windows-containers/webserver
This is a simple webserver container implemented in PowerShell borrowed from a number of sources.

## Build on Windows 11 or Server 2022
`docker build -t webserver .`

## Tag
`docker tag webserver quay.revoweb.com/nrevo/webserver`

## Push
`docker push quay.revoweb.com/nrevo/webserver`

## Use
`docker run -it --rm -p 8080:80 webserver`

```bash
oc adm policy add-scc-to-user anyuid -z runwinweb -n win-test-workload
oc apply -f deployment.yaml
```

