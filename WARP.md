# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Repository Overview

This is a **CloudOps Portfolio** repository that serves as an umbrella project showcasing a multi-repository DevOps portfolio. The actual implementation is split across three separate repositories:

- **cloudops-backend**: Node.js + Express API with Docker and CI/CD
- **cloudops-frontend**: React app with Nginx serving, Docker and CI/CD  
- **cloudops-infra**: AWS Infrastructure with Terraform + monitoring (Prometheus + Grafana)

This repository contains:
- Documentation and architecture overview
- Development environment setup with Vagrant
- Mermaid flowchart diagrams showing the overall architecture

## Architecture

The portfolio demonstrates a complete DevOps workflow:
```
GitHub Repos (Backend + Frontend) → CI/CD (GitHub Actions) → DockerHub → AWS Deployment (EC2 + S3/CloudFront) → Monitoring (Prometheus + Grafana)
```

## Common Development Commands

### Vagrant Development Environment

Start the development VM:
```bash
vagrant up
```

SSH into the VM:
```bash
vagrant ssh cloudops
```

Check VM status:
```bash
vagrant status
```

Stop the VM:
```bash
vagrant halt
```

Destroy the VM:
```bash
vagrant destroy
```

Reload VM configuration:
```bash
vagrant reload
```

### Git Operations

View recent commits:
```bash
git log --oneline -10
```

Check repository status:
```bash
git status
```

View architecture diagram:
```bash
cat "flowchart TD.mmd"
```

## Development Environment

The repository includes a Vagrant configuration that sets up:
- Ubuntu 22.04 LTS (jammy64) VM
- 2GB RAM, 1 CPU
- Private network IP: 10.0.4.10
- Synced folder from host portfolio directory to `/home/vagrant/cloudops`

## Project Structure

```
.
├── README.md              # Portfolio overview and links to other repos
├── Vagrantfile           # Local development VM configuration
├── flowchart TD.mmd      # Mermaid diagram of the architecture
└── .gitignore           # Git ignore rules (excludes .vagrant/)
```

## Working with Related Repositories

This portfolio consists of three separate repositories that should be cloned individually:

1. **Backend API**: `git clone https://github.com/GhostGto/cloudops-backend.git`
2. **Frontend App**: `git clone https://github.com/GhostGto/cloudops-frontend.git`  
3. **Infrastructure**: `git clone https://github.com/GhostGto/cloudops-infra.git`

Each repository has its own development workflow, build processes, and deployment pipelines.

## Key Technologies

- **Virtualization**: Vagrant + VirtualBox
- **Documentation**: Markdown, Mermaid diagrams
- **Version Control**: Git with clean commit history
- **Architecture**: Multi-repo microservices approach
- **Cloud Platform**: AWS (EC2, S3, CloudFront)
- **Containerization**: Docker
- **CI/CD**: GitHub Actions
- **Monitoring**: Prometheus + Grafana
- **Infrastructure as Code**: Terraform

## Development Workflow

1. Use `vagrant up` to start the development environment
2. SSH into the VM with `vagrant ssh cloudops` 
3. Navigate to `/home/vagrant/cloudops` for the synced portfolio files
4. Clone the individual component repositories as needed
5. Work on documentation updates and architecture diagrams in this repo
6. The actual application development happens in the separate component repositories