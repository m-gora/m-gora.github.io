---
title: "Bandcheck"
description: "Community-driven content warning platform for safer music discovery"
featured_image: "/images/bandcheck.png"
tags: ["typescript", "react", "azure", "terraform", "auth0", "open-source", "community"]
---

## Making Music Discovery Safer

**Live Platform:** [bandcheck.marcodoes.tech](https://bandcheck.marcodoes.tech)  
**GitHub Repository:** [m-gora/bandcheck](https://github.com/m-gora/bandcheck)

Music should be accessible to everyone, but not all content is suitable for all listeners. Bandcheck addresses a gap in music platforms: **content warnings for potentially triggering or sensitive material**.

## Our Mission

Bandcheck's mission is to make discovering music safer by building a **shared knowledge base of content warnings** contributed by the community. Unlike traditional review platforms that focus on subjective ratings, Bandcheck provides **evidence-based, factual information** about content—empowering listeners to make informed decisions.

The platform is **non-profit and open source** because we believe access to information about potentially triggering content should be freely available to everyone.

## How It Works

**Community-Driven Reviews** - Users contribute content warnings for songs, albums, and artists, specifying categories like explicit language, violence, substance references, or other sensitive topics.

**Evidence-Based Approach** - Reviews focus on objective content descriptions rather than subjective quality judgments. "This song contains explicit language and references to substance abuse" rather than "This song is good/bad."

**Informed Decisions** - Listeners can search for music and view aggregated content warnings before deciding whether it's appropriate for their context—whether that's personal triggers, playing music around children, or workplace environments.

## Technical Stack

Built with modern cloud-native technologies for scalability and maintainability:

**Frontend**
- **React** with TypeScript for type-safe, maintainable UI development
- Responsive design for seamless mobile and desktop experiences

**Backend & Infrastructure**
- **Azure Functions** for serverless, scalable API endpoints
- **Auth0** for secure authentication and user management
- **Terraform** for infrastructure as code, ensuring reproducible deployments
- **GitHub Actions** for automated build and deployment pipelines

**Local Development**
- **Azurite** + **Docker Compose** to run Azure cloud dependencies locally
- Seamless local-to-cloud parity for efficient development workflow

**Architecture**
- Documented using **arc42** architecture framework
- **Function as a Service (FaaS)** architecture enabling independent scaling per function
- Cloud-native design for high availability and cost efficiency

## Open Source Philosophy

The entire codebase is open source, inviting:
- **Community contributions** to expand coverage and improve the platform
- **Transparency** in how content warnings are collected and displayed
- **Reusability** - others can deploy their own instances or adapt the system for different media types

## Why This Matters

Bandcheck represents a **user-centered approach to content moderation** that prioritizes safety without gatekeeping. By separating content warnings from quality judgments, it respects both artistic expression and individual boundaries.

From a technical perspective, it demonstrates:
- **Function as a Service (FaaS) architecture** with Azure Functions at scale
- **CI/CD automation** with GitHub Actions for continuous deployment
- **Local development parity** using Azurite and Docker Compose to mirror cloud environments
- **Community platform design** balancing openness with safety
- **Infrastructure as code** for reproducible cloud deployments
- **Authentication & authorization** patterns with Auth0

The same principles apply to any platform requiring community-contributed metadata—movie databases, podcast directories, or game content ratings.