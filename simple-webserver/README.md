# windows-containers/webserver
This is a simple webserver container implemented in PowerShell borrowed from a number of sources.

## Build on Windows 11 or Server 2022
`docker build -t webserver .`

## Tag
`docker tag webserver quay.io/revoman/webserver:latest`

## Push
`docker push quay.io/revoman/webserver:latest`

## Use
`docker run -it --rm -p 8080:80 quay.io/revoman/webserver:latest`

```bash
oc adm policy add-scc-to-user anyuid -z runwinweb -n win-test-workload
oc apply -f deployment.yaml
```

The pod logs should look like this:
<img width="348" alt="image" src="https://user-images.githubusercontent.com/5229889/196250421-a6c8df49-79ea-43f7-b6d0-e0e4a50c57f9.png">
