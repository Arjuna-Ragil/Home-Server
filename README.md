# Home Server Base Setup

An Ansible playbook designed to automate the initial configuration and deployment of core infrastructure for a self-hosted home server on Ubuntu Server.

## Overview

This repository contains automation scripts to provision a clean Ubuntu Server installation into a functional homelab environment. It streamlines the deployment of container runtimes, management dashboards, and secure networking overlays, enforcing an Infrastructure as Code (IaC) approach for homelab management.

## Components & Features

- **Infrastructure & Orchestration:** Automates the installation of Docker and CasaOS, establishing a stable runtime environment for managing containerized self-hosted applications and developer tools.
- **Zero-Trust Networking:** Configures Tailscale to enable secure, encrypted remote access and internal routing within a private mesh network.
- **Secure Public Access:** Deploys Cloudflare Tunnels (`cloudflared`) to safely expose public-facing web services to the internet securely without requiring manual port forwarding.

## Repository Structure

- `baseSetup.yml`: The main Ansible playbook containing tasks for system updates, package installations, and service configurations.
- `inventory.ini`: Configuration file defining the target host IPs, user credentials, and connection variables for the server deployment.

## Prerequisites

- A target machine running Ubuntu Server.
- SSH access configured between the control machine and the target server.
- Ansible installed on your local development/control machine.

## Getting Started

1. Update the target server IP and SSH connection details in the `inventory.ini` file.
2. Execute the playbook by running the following command in your terminal:

```bash
ansible-playbook -i inventory.ini baseSetup.yml
