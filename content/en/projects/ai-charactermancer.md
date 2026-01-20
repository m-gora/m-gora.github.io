---
title: "AI Charactermancer"
description: "Next-generation Pathfinder 1e character builder powered by AI and multi-agent optimization"
featured_image: ""
tags: ["python", "ai", "langgraph", "rag", "multi-agent-systems", "game-design", "pathfinder"]
---

## The Challenge

Building an optimized character in **Pathfinder 1e** is notoriously complex. With thousands of feats, archetypes, prestige classes, and intricate synergies spanning 20 character levels, even experienced players struggle to find optimal builds. Most character creators are glorified forms—they let you input choices but don't help you discover them.

**What if an AI could understand your concept and find the optimal build for you?**

**GitHub Repository:** [m-gora/ai-charactermancer](https://github.com/m-gora/ai-charactermancer)

## The Vision

AI Charactermancer is a **character creation system on steroids**—combining RAG (Retrieval-Augmented Generation) with multi-agent architecture to search through Pathfinder 1e's vast rule system and discover synergistic builds that humans might miss.

You describe your concept: *"I want a trip-focused melee character with excellent battlefield control at mid-levels."* The system analyzes the entire ruleset, simulates progression paths, and presents optimized builds with performance metrics across all 20 levels.

## Architecture

### Multi-Agent LangGraph System

The core architecture uses **LangGraph** to orchestrate multiple specialized agents, each responsible for different aspects of character creation:

**Orchestrator/Supervisor Agent** - The central router that:
- Parses user goals and generates a step-by-step build plan
- Delegates tasks to specialist agents
- Manages the overall workflow state

**Specialist Agents** - Domain experts for character components:
- **Feat Agent** - Searches for optimal feat chains and synergies
- **Stats Agent** - Optimizes ability score distribution
- **Gear Agent** - Identifies equipment that maximizes build effectiveness
- **Skills Agent** - Allocates skill points strategically
- **Multiclassing Agent** - Evaluates complex class progression paths

**Rule Checker Agent** - Validates all choices against Pathfinder 1e rules, catching invalid combinations and triggering corrections

**Information-Gathering Agent** - Detects ambiguity in user input and asks clarifying questions through human-in-the-loop interrupts

### RAG-Powered Knowledge Base

All Pathfinder 1e content is ingested into a **vector database**:
- Classes, archetypes, prestige classes
- Feats and feat chains
- Equipment and magic items
- Spells and abilities

**Hybrid search** combines semantic similarity with metadata filtering to find relevant rules based on character context (e.g., "feats for trip at BAB +5").

### Advanced Features

**Lookahead Simulation** - The multiclassing agent doesn't just optimize for the current level—it simulates multiple progression paths (e.g., Fighter 2/Wizard 8 vs. straight Wizard 10) up to target levels to find builds that peak when you need them.

**Parallel Optimization** - Multiple agents work simultaneously to find synergies between feats, items, and class features, discovering combinations that manual builders might overlook.

**Performance Metrics** - Calculates key indicators (DPR, CMB/CMD, spell DCs) at each level and generates visualization charts showing when your build hits peak performance.

**Prestige Class Optimization** - Automatically identifies optimal "dipping" sequences to meet prestige class prerequisites while maximizing overall effectiveness.

## Technical Implementation

### State Management
- **Centralized typed state** (`CharacterBuildState`) tracks user goals, build plan, character sheet, verification errors, and user interactions
- **Persistent checkpointer** (SQLite-backed) enables state resumption during human-in-the-loop interrupts

### Verification & Self-Correction
- Conditional edges route invalid builds back to the originating specialist agent
- Agents automatically attempt fixes based on rule checker feedback
- Human intervention only requested when automated correction fails

### Weighted Scoring System
Customizable performance metrics ($w_n$ weights) adapt to user goals:
- Combat optimization prioritizes DPR and survivability
- Skill-focused builds emphasize skill checks and versatility
- Spellcasters optimize for spell DC and versatility

## Current Status

**Active Development** - Core architecture designed, currently implementing:
- Knowledge base ingestion pipeline
- Specialist agent behaviors
- Lookahead simulation engine
- Visualization layer

## Why This Matters

Beyond Pathfinder, this project demonstrates:

**Complex Decision Space Optimization** - Multi-agent systems navigating thousands of valid choices to find optimal solutions

**Rule-Based AI Systems** - Combining LLMs with structured rule validation for domains requiring perfect accuracy

**Human-AI Collaboration** - Seamless HITL patterns that clarify ambiguity without overwhelming users

**Explainable Recommendations** - Not just "here's a build" but "here's why this works and when it peaks"

The same patterns apply to tax optimization, medical treatment planning, or any domain with complex rules and multiple valid paths to success.