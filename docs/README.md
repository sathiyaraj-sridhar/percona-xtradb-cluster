This document provides a guide on how to deploy **Percona XtraDB Cluster (PXC)** in various deployment environment such as DEV, STG, and PRD. However, It does not delve into the related technology in detail. For instance, It explains how to deploy **PXC** in Docker container without providing further information on Docker.

The intended audience for this document includes:
- Software engineers
- Program managers

Let's take a brief look at these learning materials.

```
├── LICENSE
├── docker
│ ├── compose.yml
│ ├── dockerfile.base.dev
│ └── dockerfile.pxc.8.0.35
├── docs
│ ├── README.md
│ └── dev-environment.md
├── source
│ ├── cert
│ └── conf
│     ├── initialize.txt
│     ├── node1.conf
│     ├── node2.conf
│     └── node3.conf
└── supervisor
    ├── mysql-bootstrap-pxc.ini
    ├── mysql.ini
    └── supervisord.conf
```
- **source:** It includes everything needed for **PXC**, like certificates, configurations, scripts, and more.
- **supervisor:** It includes configuration file for `supervisord` and **PXC** programs.
- **docker:** It includes all the Docker-related materials like Dockerfile, Compose, and the Context directory.
- **docs:** It includes user guides for utilizing these materials.

Let's start.

**Step 1:** Create a directory to manage all my open-source repositories under the `/opt/oss` path. You can also clone it under your custom path.

```bash
sudo mkdir /opt/oss
sudo chown -R $USER /opt/oss
```

**Step 2:** Clone the repository.

```bash
git clone https://github.com/sathiyaraj-sridhar/percona-xtradb-cluster.git /opt/oss/percona-xtradb-cluster
```

## Roadmaps

**Development environment (DEV):**
- [x] [Deploying three-node Percona XtraDB Cluster in a Docker Container](dev-environment.md)
- [ ] Testing Ansible playbooks in a Docker container.
- [ ] Testing Chef cookbooks in a Docker container.

**Staging and QA environment (STG & QA):**
- [ ] Provisioning infrastructure for a Kubernetes setup using Terraform.
- [ ] Deploying a three-node Percona XtraDB Cluster in Kubernetes.
- [ ] Let's understand how to scale Percona XtraDB Cluster in Kubernetes.
- [ ] Let's understand how to backup Percona XtraDB Cluster data in Kubernetes.

**Production environment (PRD):**
- [ ] Provisioning infrastructure on the AWS cloud using Terraform.
- [ ] Deploying a three-node Percona XtraDB Cluster in the AWS cloud using Ansible.
- [ ] Deploying a three-node Percona XtraDB Cluster in the AWS cloud using Chef.
- [ ] Let's understand how to scale Percona XtraDB Cluster in the AWS cloud.
- [ ] Let's understand how to backup Percona XtraDB Cluster data in the AWS cloud.
