<div align="center">
  <img src="images/logo_makehub.png" alt="Makehub Logo" width="300"/>
</div>

# Optimization and Routing of LLM Requests Across Different Providers

**Final Thesis X-HEC Entrepreneurs Program**

**Author:** Baptiste Cruvellier
**Academic Advisor:** Gentian Jakllari
**Company:** Makehub
**Year:** 2025

## Overview

This thesis presents the design, implementation, and empirical validation of **Makehub**, an intelligent routing gateway for Large Language Model (LLM) inference that achieves **40-70% cost savings** while maintaining or improving response quality and speed.

### The Problem

The LLM inference market is characterized by extreme fragmentation, with over 50 providers offering varying combinations of models, pricing structures, and performance profiles. Key findings:

- **No price-performance correlation** (r=0.046): Higher cost does not predict lower latency or higher throughput
- **Massive same-model variance** (57%): Identical models like GPT-4o vary in latency by up to 57% across providers
- **Dynamic performance fluctuations**: Provider performance degrades unpredictably due to load conditions and infrastructure incidents

### The Solution

Makehub acts as a unified API layer between client applications and multiple LLM providers, implementing four complementary optimization strategies:

1. **Real-time performance monitoring** - Passive instrumentation and active pinging across 500+ model-provider pairs
2. **Intelligent provider routing** - 3D vectorial scoring in (price, throughput, latency) space with automatic fallback
3. **Model routing via family system** - LLM-as-a-Judge complexity evaluation to match requests to appropriate model tiers
4. **Prompt compression** - LLM-based message filtering reduces input tokens by 30-70%

### Key Results

- **40-70% cost reduction** in production deployment
- **22% latency improvement** (224ms per request) for GPT-4o workloads
- **99.9% uptime** achieved through cascading fallback mechanisms
- Analysis of **170,555 production requests** across 8 providers and 3 model families

## Contents

### 1. Presentation of Makehub
- Contextualization of Large Language Models (LLMs)
  - Definition and fundamentals (tokens, transformers, inference)
  - Closed-source vs open-source models
  - Model-provider abstraction layer
  - Code assistants: from autocomplete to agentic systems

### 2. The Makehub Project
- Team presentation (CEO, CPO, CTO)
- Origin of the project (Berkeley X-HEC exchange)
- Market opportunity and problem statement

### 3. Problem Statement: Optimizing LLM Request Routing
- Definition of protocols used for LLM calls (OpenAI API, streaming)
- State of the art: industry methods for cost/performance optimization
- Empirical analysis of provider landscape

### 4. Real-Time Monitoring of Server Load
- Defining server "performance" (latency, throughput, context window, cost)
- Implementation of measurement protocol
  - Point-in-time measurement (passive)
  - Periodic pinging (active)
  - Data fusion strategy

### 5. Implementation of the Routing Logic
- System architecture and components (10-stage request pipeline)
- Provider filtering algorithm
  - Capability filtering (context window, vision, tools, caching)
  - 3D vectorial scoring
- Fallback mechanism (cascading retry logic)

### 6. Advanced Optimizations
- Model routing via family system
  - LLM-as-a-Judge complexity evaluation
  - Score-based model selection
- Prompt compression implementation
  - LLM-based message filtering
  - Integration with provider routing

### 7. Conclusion
- Summary of contributions
- Future directions
- Personal growth and learning

## Technical Stack

- **Backend:** TypeScript, Node.js
- **Database:** PostgreSQL
- **API Compatibility:** OpenAI-compatible API
- **Integration:** Cursor, Cline, Aider, and other code assistants
- **Architecture:** 10-stage request pipeline with dual-source monitoring

## Compilation

This LaTeX document requires:
- **LaTeX Distribution:** MiKTeX or TeX Live
- **Compiler:** pdflatex with `-shell-escape` flag (for minted package)
- **Bibliography:** Biber backend

### Build Commands

```bash
pdflatex -synctex=1 -interaction=nonstopmode -shell-escape -file-line-error these.tex
biber these
pdflatex -synctex=1 -interaction=nonstopmode -shell-escape -file-line-error these.tex
pdflatex -synctex=1 -interaction=nonstopmode -shell-escape -file-line-error these.tex
```

### Required Packages

- amsmath, graphicx, float
- minted (syntax highlighting)
- biblatex with biber backend
- svg (for logo inclusion)
- listings (for code blocks)
- geometry (page layout)

## Key Contributions

### 1. Empirical Characterization of Provider Landscape
- First large-scale study (170,555 requests) quantifying price-performance relationships
- Discovery of negligible price-latency correlation challenges assumptions underlying static provider selection
- Documentation of 57% same-model variance highlights infrastructure as primary performance determinant

### 2. Novel Multi-Criteria Routing Algorithm
- 3D vectorial scoring framework enables continuous interpolation between cost and performance
- Integration of capability filtering, performance metrics, and prompt caching history
- Demonstrated 40-70% cost savings with sub-second routing overhead

### 3. Production-Validated System Architecture
- Open-source implementation deployed in production
- Seamless integration with existing code assistants
- Robust fallback mechanisms achieve 99.9% uptime

## Broader Implications

This work establishes several principles for LLM infrastructure design:

- **Measurement over assumptions**: Real-world performance monitoring reveals patterns invisible in synthetic benchmarks
- **Unified abstraction layers**: Decoupling client applications from provider-specific APIs enables competition on performance and price
- **Composable optimizations**: Provider routing, model routing, and prompt compression achieve multiplicative savings when combined

## Acknowledgments

Special thanks to:
- **Academic advisor:** Gentian Jakllari
- **Co-founders:** Romain Batlle (CEO) and Samir Fernando Florido (CPO)
- **X-HEC Master's program** for the entrepreneurial opportunity
- **Berkeley exchange program** and the Silicon Valley ecosystem
- Family and friends for their constant support

## License

This thesis is academic work submitted as part of the X-HEC Entrepreneurs Master's program.

## Contact

**Makehub Team**
- Website: [makehub.ai](https://makehub.ai)
- Author: Baptiste Cruvellier (CTO)
- Email: baptiste@cruvellier.eu

---

*Generated with ❤️ for the X-HEC Entrepreneurs program, 2025*
