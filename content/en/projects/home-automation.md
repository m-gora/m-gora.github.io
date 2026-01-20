---
title: "Home Server & Automation"
description: "Building a production-grade home automation platform with enterprise DevOps practices"
featured_image: ""
tags: ["devops", "k3s", "kubernetes", "home-assistant", "automation", "iot"]
---

## Overview

My home automation setup isn't just about turning lights on and off—it's a full-scale infrastructure project that applies the same DevOps principles I use professionally. Running on **k3s** (lightweight Kubernetes), this system demonstrates production-grade architecture patterns in a home environment.

**GitHub Repository:** [m-gora/homeserver](https://github.com/m-gora/homeserver)

## Architecture & Technologies

The platform is built on a modern cloud-native stack:

- **Home Assistant** serves as the automation brain, orchestrating all smart home logic
- **Mosquitto MQTT broker** handles real-time device communication
- **Zigbee2MQTT** bridges Zigbee devices to the MQTT network, eliminating vendor lock-in
- **GitHub Actions Self-Hosted Runners (ARC)** enable CI/CD pipelines directly from my home lab

## Production-Grade Infrastructure

What makes this setup interesting from an engineering perspective:

**Automated Certificate Management** - Using **cert-manager** with **Let's Encrypt** to automatically provision and renew SSL certificates, ensuring secure HTTPS access without manual intervention.

**Dynamic DNS & IPv6 Tunneling** - **external-dns** automatically creates DNS entries at **Cloudflare**, which also tunnels IPv4 traffic to my IPv6-only endpoint—a creative workaround for CGNAT limitations that many home networks face.

**GitOps Workflow** - Infrastructure as code principles with version-controlled configurations, making the entire setup reproducible and maintainable.

**Automated Dependency Management** - **Renovate** continuously monitors container image versions and automatically opens pull requests when updates are available, keeping the cluster secure and up-to-date with minimal manual intervention.

## Planned Enhancements

An interesting idea I explored was integrating **Google Tasks** with the GitHub workflow—automatically creating tasks in my calendar whenever Renovate opens a pull request for review. While the concept would provide better visibility into pending updates, the implementation overhead didn't justify the marginal gains.

However, since **Home Assistant** already has both **GitHub** and **Google Tasks** integrations built-in, this might be worth revisiting. Leveraging existing integrations could achieve the same goal with significantly less setup effort—a good reminder that sometimes the best architecture is the one that uses what's already there.

## Real-World Integrations

Currently managing several device ecosystems:

- **Thermostatic Radiator Valves (TRVs)** for intelligent room-by-room heating control
- **Terrarium automation** with coordinated lighting schedules, heating control, and automated rain pump system
- **Roborock vacuum** integrated for scheduling and zone-based cleaning

## Why This Matters

This project showcases the ability to take enterprise-grade DevOps practices—Kubernetes orchestration, automatic certificate management, DNS automation, CI/CD pipelines—and apply them to solve real problems in a resource-constrained environment. It's a practical demonstration of infrastructure skills that scales from home labs to production cloud deployments. 