# Chess AI Through Language Models: Strategic Reasoning Without Search

**Jonathan Rahn** | AI Lab Lead, Drees & Sommer | [GitHub](https://github.com/jorahn) | [HuggingFace](https://huggingface.co/jrahn)

## Research Overview

This work explores transformer-based strategic reasoning through chess as a testbed, demonstrating that language models can develop sophisticated game-playing capabilities without traditional search algorithms. In collaboration with [LAION](https://laion.ai/notes/room), we’ve developed a progression of models that challenge fundamental assumptions about how AI systems learn strategic thinking.

The core hypothesis: complex strategic reasoning can emerge from next-token prediction when models are trained on appropriately structured strategic data.

-----

## The ROOK Project Evolution

### RookWorld-RLVR (Current)

Active development integrating Reinforcement Learning with Verifiable Rewards (GRPO) for enhanced reasoning capabilities.  
Repo Transformers & TRL: [jorahn/RookWorld-TRL](https://github.com/jorahn/rookworld-trl)  
Repo PyTorch: [jorahn/RookWorld-RLVR](https://github.com/jorahn/rookworld-rlvr)

### RookWorld-LM (124M params) - Unified Agent+Environment

**Key breakthrough**: Unified chess policy and world model in a single transformer architecture.  
Post: [ROOK: REASONING OVER ORGANIZED KNOWLEDGE](https://laion.ai/notes/rook/)

- **Collaboration**: [Jenia Jitsev](https://scholar.google.com/citations?user=p1FuAMkAAAAJ&hl=en) (LAION/JSC), [Qi Sun](https://scholar.google.com/citations?user=rv0MJuAAAAAJ&hl=en) (Tokyo Tech/Sakana AI)
- **Multi-task Performance**:
  - 32.1% Checkmate-in-One accuracy (vs ChessGPT-Base 26.5%)
  - 99.9% environment simulation accuracy
  - 26.2% overall action accuracy
- **Dataset**: [rookworld-46m](https://huggingface.co/datasets/jrahn/rookworld-46m)
- **Significance**: Enables closed-loop self-play without external engines
- **Interactive Demo**: [RookWorld Space](https://huggingface.co/spaces/jrahn/rookworld)

### ROOK-LM (124M params) - Chain-of-Thought Integration

Implementation of Chain-of-Thought reasoning for chess, incorporating position analysis → candidate evaluation → move selection.

- **Dataset**: [rook-40m](https://huggingface.co/datasets/jrahn/rook-40m) (6B tokens, generated on Tsubame 4.0)
- **Architecture**: GPT-2 with custom chess tokenization
- **Performance**: 22.2% action accuracy with comprehensive reasoning traces
- **Technical Details**: [LAION Blog Post](https://laion.ai/blog/rook/)

### ROOK-CLF (9M params) - Classification Approach

Reproduction of Google DeepMind’s [“Grandmaster-Level Chess Without Search”](https://arxiv.org/abs/2402.04494) methodology using LLaMA-based decoder.

- **Performance**: 49% action accuracy, 57% on Checkmate-in-One
- **Achievement**: Demonstrated searchless chess AI feasibility with minimal parameters
- **Model**: [Available on HuggingFace](https://huggingface.co/jrahn/rook-clf)

### YoloChess (2022) - Foundation Work

Initial exploration using BERT-based position evaluation with custom FEN encoders. Established baseline performance and identified key challenges in chess representation for transformer architectures.

- **Dataset**: [yolochess_lichess-elite_2211](https://huggingface.co/datasets/jrahn/yolochess_lichess-elite_2211)
- **Architecture**: DeBERTa v2 with FEN tokenization

-----

## Technical Contributions

### Novel Architectures

- **Unified world modeling**: Simultaneous policy and environment simulation in transformers
- **Strategic tokenization**: Custom representations for structured game states
- **Multi-task scaling**: Consistent performance improvements with unified training objectives

### Dataset Engineering

- **Large-scale annotation**: 40M+ positions annotated with Stockfish 16.1 on supercomputing infrastructure
- **Multi-format datasets**: Support for classification, autoregressive, and multi-task learning
- **Reproducible pipelines**: Full data generation code and methodology documentation

### Open Science Impact

All models, datasets, and code publicly available. Contributing to democratization of strategic AI research.

-----

## Research Context

Background spans neuro-informatics (University of Lübeck), games industry applications, business economics & management (Witten/Herdecke University, IPADE Mexico DF), and AI/ML consulting. Active contributor to HuggingFace ecosystem (transformers, datasets, evaluate) and open source frameworks including keras-rl and custom implementations like keras-wide-n-deep. Current work at Drees & Sommer, building the AI Lab & exploring applications in construction and real estate optimization.

-----

## Research Implications

The RookWorld results suggest that:

1. **Search-free strategic AI** is viable with appropriate training data
1. **Unified architectures** can efficiently handle multiple strategic reasoning tasks
1. **Chain-of-thought training** improves both performance and interpretability
1. **Language model paradigms** apply effectively to structured strategic domains

These findings have implications beyond chess for any domain requiring sequential decision-making under 
