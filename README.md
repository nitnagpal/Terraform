# Terraform
Directory Structure for Terraform Project
```
terraform
├── aws
│   ├── ap-south-1
│   │   ├── common
│   │   │   ├── network
│   │   │   └── service
│   │   ├── dev
│   │   │   ├── network
│   │   │   └── service
│   │   ├── prod
│   │   │   ├── network
│   │   │   └── service
│   │   └── stage
│   │       ├── network
│   │       └── service
│   ├── ap-southeast-1
│   ├── global
│   └── us-east-1
└── gcloud
    ├── asia-south1
    │   ├── common
    │   │   ├── network
    │   │   └── service
    │   ├── dev
    │   │   ├── network
    │   │   └── service
    │   ├── prod
    │   │   ├── network
    │   │   └── service
    │   └── stage
    │       ├── network
    │       └── service
    ├── asia-southeast1
    ├── global
    └── us-east1
```

All the ENV related networking TFs will go in network dir of that ENV

Each Microservice will have a dedicated folder in service dir that will have all the TFs

Terraform apply to be run from network folder for networking and service specific folder for each service

Having a separate tfstate file for each service and component reduces the need of frequently updating the tfstate file which otherwise can result in conflicts when used by multiple members of team and also corruption of tfstate file. 
