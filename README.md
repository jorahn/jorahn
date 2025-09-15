# Chess AI Through Language Models: Strategic Reasoning Without Search

**Jonathan Rahn** | AI Lab Lead, Drees & Sommer | [GitHub](https://github.com/jorahn) | [HuggingFace](https://huggingface.co/jrahn) | [Research Page](https://jorahn.github.io/research/) | [W&B](https://wandb.ai/jrahn/ROOK)

## Research Overview

This work explores transformer-based strategic reasoning through chess as a testbed, demonstrating that language models can develop sophisticated game-playing capabilities without traditional search algorithms. In collaboration with [LAION](https://laion.ai/notes/rook), we've developed a progression of models that challenge fundamental assumptions about how AI systems learn strategic thinking.

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
  - **🏆 32.1% Checkmate-in-One accuracy** - outperforms ChessGPT-Base (Feng et al., NeurIPS'23) with **124M vs 3B parameters** (24x smaller)
  - 99.9% environment simulation accuracy (details: Next State 99.61%, NLS 99.99%, Reward 99.11%, Terminated 99.13%; see RookWorld/README)
  - 26.2% action accuracy
- **Model**: [RookWorld-LM 124M](https://huggingface.co/jrahn/RookWorld-LM-124M)
- **Dataset**: [rookworld_7m](https://huggingface.co/datasets/jrahn/rookworld_7m)
- **Repository**: [jorahn/RookWorld](https://github.com/jorahn/RookWorld)
- **Significance**: Enables closed-loop self-play without external engines
- **Interactive Demo**: [RookWorld Space](https://huggingface.co/spaces/jrahn/rookworld)

### ROOK-LM (124M params) - Chain-of-Thought Integration

Implementation of Chain-of-Thought reasoning for chess, incorporating position analysis → candidate evaluation → move selection.

- **Model**: [ROOK-LM 124M](https://huggingface.co/jrahn/ROOK-LM-124M)
- **Dataset**: [rook_40m](https://huggingface.co/datasets/lfsm/rook-40m) (6B tokens, generated on Tsubame 4.0)
- **Architecture**: GPT-2 with custom chess tokenization
- **Performance**: 22.2% action accuracy, 24.4% Checkmate-in-One
- **Repository**: [jorahn/RookWorld](https://github.com/jorahn/RookWorld)
- **Technical Details**: [LAION Research Note](https://laion.ai/notes/rook/)

### ROOK-CLF (9M params) - Classification Approach

Reproduction of Google DeepMind's ["Grandmaster-Level Chess Without Search"](https://arxiv.org/abs/2402.04494) methodology using LLaMA-based decoder.

- **Performance**: 49% action accuracy, 57% on Checkmate-in-One
- **Achievement**: Demonstrated searchless chess AI feasibility with minimal parameters
- **Model**: [ROOK-CLF-9M on HuggingFace](https://huggingface.co/jrahn/ROOK-CLF-9m)
- **Interactive Demo**: [Try it in your browser](https://jorahn.github.io/research/rook-clf-demo/)
- **Repository**: [jorahn/rook](https://github.com/jorahn/rook)

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
