# helm-repository-manager
## Anatomia de um helm chart

repository_root/
├── chart1/  # Directory for chart1
│   ├── Chart.yaml
│   ├── values.yaml
│   ├── templates/
│   │   ├── deployment.yaml
│   │   ├── service.yaml
│   │   └── ...
│   └── ...
├── chart2/  # Directory for chart2
│   ├── Chart.yaml
│   ├── values.yaml
│   ├── templates/
│   │   ├── deployment.yaml
│   │   ├── service.yaml
│   │   └── ...
│   └── ...
├── index.yaml  # Repository index file
