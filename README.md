# AIOps Framework for GenAI Projects

## Overview

The AIOps (AI Operations) framework provides a standardized approach for developing, evaluating, deploying, and monitoring AI applications at Novo Nordisk. The framework focuses on bringing automation, consistency, and visibility to AI applications, with a specific emphasis on GenAI and LLM-based projects.

## Purpose

This framework aims to:
- Standardize development approaches across different AI projects
- Provide faster development cycles with consistent tools and patterns
- Ensure higher quality AI solutions through systematic evaluation
- Reduce maintenance costs through automation
- Improve visibility into AI application performance

## Core Capabilities

The AIOps framework consists of five main components:

1. **Developer Experience**: Tools and templates for efficient development
2. **Flow Development**: Standardized approaches for building AI workflows
3. **Evaluation**: Systematic testing and quality assessment
4. **Production**: Automated deployment pipelines
5. **Insights & Analytics**: Monitoring and continuous improvement

Underpinning these components are four core capabilities:
- Automation
- Standardization
- Governance
- Observability

## Current Scope

### In Current Phase:
- Prompt Flow orchestration (experiment, evaluate, deploy)
- CI/CD pipelines for automated testing and deployment
- Monitoring & alerting for deployed flows
- DataOps for preparing and registering data assets

### Not In Current Scope:
- Model training and fine-tuning
- Custom RAG implementations beyond templates

## Use Cases

The framework currently supports the following use cases:

### comming soon

## Implementation Workflow

The AIOps workflow follows these high-level steps:

1. **Development**: Create and test prompt flows locally
2. **Quality Control**: Automated PR checks for code quality
3. **Deployment Pipeline**: 
   - Test flows against multiple datasets
   - Generate performance reports
   - Deploy to chosen target (Azure ML, Web Apps)
4. **Monitoring**: Track performance metrics and usage patterns

## Getting Started

To begin using the AIOps framework:

1. Review the architecture documentation in the `Docs/design.md` file
2. Complete the requirements questionnaire at `Docs/RequirementsQuestionnaire.md`
3. Follow the presentation slides in `Docs/AIOps_Presentation-new.md` for an overview



## Implementation Roadmap

**Immediate Actions (Next 30 Days):**
- Complete AIOps pipeline setup for QCP use case
- Define standard metrics for flow evaluation
- Develop basic monitoring dashboards

**Medium-Term (60-90 Days):**
- Extend AIOps framework to CMC use case
- Implement enhanced security controls
- Create documentation and training materials

**Future Enhancements:**
- Databricks connectors for improved data integration
- Specialized RAG evaluation metrics
- Fine-tuning workflow support

## Contributing

Please follow these steps to contribute to the project:
1. Review the existing documentation
2. Ensure your changes align with the AIOps framework principles
3. Submit pull requests with comprehensive descriptions

## Contact

For more information about this project, please contact the project maintainers.