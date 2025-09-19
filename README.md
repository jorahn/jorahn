# Chess AI Through Language Models: Strategic Reasoning Without Search

<div align="center">

**Jonathan Rahn** | AI Lab Lead, Drees & Sommer

<a href="https://jorahn.github.io/" target="_blank">
    <img src="https://img.shields.io/badge/🌐_Research_Website-Visit_Interactive_Demos-blue?style=for-the-badge&color=4A90E2" alt="Research Website"/>
</a>
<a href="https://jorahn.github.io/research/" target="_blank">
    <img src="https://img.shields.io/badge/🎮_Try_Models-Live_Chess_AI-green?style=for-the-badge&color=50C878" alt="Interactive Demos"/>
</a>
<a href="https://laion.ai/notes/rook/" target="_blank">
    <img src="https://img.shields.io/badge/📄_LAION_Publication-Read_Research-orange?style=for-the-badge&color=FF8C42" alt="LAION Research"/>
</a>

<br/>

<a href="https://github.com/jorahn">
    <img src="https://img.shields.io/badge/GitHub-jorahn-lightgrey?style=flat&logo=github" alt="GitHub"/>
</a>
<a href="https://huggingface.co/jrahn">
    <img src="https://img.shields.io/badge/🤗_HuggingFace-jrahn-yellow?style=flat" alt="HuggingFace"/>
</a>

</div>

## Quick Start

Welcome to my chess AI research repositories! This work demonstrates that transformer models can learn strategic reasoning without traditional search algorithms.

**🎮 Try the models:** [Interactive Demos](https://jorahn.github.io/research/)
**📖 Full Documentation:** [Research Website](https://jorahn.github.io/)
**📄 Research Publication:** [LAION Notes](https://laion.ai/notes/rook/)

### Key Repositories
- 🔬 **[RookWorld](https://github.com/jorahn/RookWorld)** - Unified policy+environment models (PyTorch/llm.c)
- 🎯 **[rook](https://github.com/jorahn/rook)** - Classification approach (HuggingFace Transformers)
- 🚀 **[rookworld-trl](https://github.com/jorahn/rookworld-trl)** - RLVR training (TRL framework)

-----

## The ROOK Project Evolution

### RookWorld-RLVR (Current)

Active development integrating Reinforcement Learning with Verifiable Rewards (GRPO) for enhanced reasoning capabilities.  
Repo Transformers & TRL: [jorahn/RookWorld-TRL](https://github.com/jorahn/rookworld-trl)  
Repo PyTorch: [jorahn/RookWorld-RLVR](https://github.com/jorahn/rookworld-rlvr)

### RookWorld-LM (2024) - Unified Agent+Environment

**124M params:** Unified chess policy and world model in a single transformer architecture.
Post: [ROOK: REASONING OVER ORGANIZED KNOWLEDGE](https://laion.ai/notes/rook/)

- **Collaboration**: [Jenia Jitsev](https://scholar.google.com/citations?user=p1FuAMkAAAAJ&hl=en) (LAION/JSC), [Qi Sun](https://scholar.google.com/citations?user=rv0MJuAAAAAJ&hl=en) (Tokyo Tech/Sakana AI)
- **Multi-task Performance**:
  - **🏆 32.1% Checkmate-in-One accuracy** - outperforms ChessGPT-Base (Feng et al., NeurIPS'23) with **124M vs 3B parameters** (24x smaller)
  - 99.9% environment simulation accuracy (details: Next State 99.61%, NLS 99.99%, Reward 99.11%, Terminated 99.13%; see RookWorld/README)
  - 26.2% action accuracy
- **Interactive Demo**: [Try it in your browser](https://jorahn.github.io/research/rookworld-demo/?model=rookworld)
- **Model**: [RookWorld-LM 124M](https://huggingface.co/jrahn/RookWorld-LM-124M)
- **Dataset**: [rookworld_7m](https://huggingface.co/datasets/jrahn/rookworld_7m)
- **Repository**: [jorahn/RookWorld](https://github.com/jorahn/RookWorld)
- **Significance**: Enables closed-loop self-play without external engines

### ROOK-LM (2024) - Chain-of-Thought Reasoning

**124M params:** Implementation of reasoning traces for chess, incorporating position analysis → candidate evaluation → move selection.

- **Dataset**: [rook_40m](https://huggingface.co/datasets/lfsm/rook-40m) (6B tokens, generated on Tsubame 4.0)
- **Architecture**: GPT-2 with custom chess tokenization
- **Performance**: 22.2% action accuracy, 24.4% Checkmate-in-One with reasoning traces
- **Technical Details**: [LAION Research Note](https://laion.ai/notes/rook/)
- **Interactive Demo**: [Try it in your browser](https://jorahn.github.io/research/rookworld-demo/?model=rook-lm)
- **Model**: [ROOK-LM 124M](https://huggingface.co/jrahn/ROOK-LM-124M)
- **Repository**: [jorahn/RookWorld](https://github.com/jorahn/RookWorld)

### ROOK-CLF (2024) - Decoder-based Behavioral Cloning

**9M params:** Reproduction of Google DeepMind's ["Grandmaster-Level Chess Without Search"](https://arxiv.org/abs/2402.04494) methodology using LLaMA-based decoder.

- **Performance**: 49% action accuracy, 57% on Checkmate-in-One
- **Achievement**: Demonstrated searchless chess AI feasibility with minimal parameters
- **Model**: [Available on HuggingFace](https://huggingface.co/jrahn/ROOK-CLF-9m)
- **Interactive Demo**: [Try it in your browser](https://jorahn.github.io/research/rook-clf-demo/)
- **Repository**: [jorahn/rook](https://github.com/jorahn/rook)
- **Training Logs**: [W&B](https://wandb.ai/jrahn/ROOK)

### LAION Strategic Game Dataset (2023) - Dataset Engineering

Contributed to the [LAION Strategic Game Dataset](https://laion.ai/blog/strategic-game-dataset/) project, responding to their call for participation to enhance AI models' strategic planning capabilities through game-based synthetic datasets. Developed chess-to-text transformation tools for dataset generation as part of this community effort exploring strategic reasoning in language models.

- **Contribution**: Chess dataset generation and transformation pipeline
- **Code**: [chess-to-text repository](https://github.com/jorahn/chess-to-text)
- **Project Scale**: 3.2 billion chess games, 608 billion moves via Stockfish self-play
- **Impact**: Foundation work that evolved into the ROOK project research

### YoloChess (2022) - Encoder-based Behavioral Cloning

**87M params (Custom DeBERTaV2-base, Vocab Size 500):** Two-stage training approach using masked language modeling (MLM) pretraining on FEN representations, followed by supervised fine-tuning on a sequence classification objective for move prediction. Established baseline performance and identified key challenges in chess representation for transformer architectures.

- **Dataset**: [yolochess_lichess-elite_2211](https://huggingface.co/datasets/jrahn/yolochess_lichess-elite_2211)
- **Architecture**: DeBERTa v2 with custom FEN tokenization and classification head
- **Training**: MLM pretraining → Supervised fine-tuning for sequence classification
- **W&B Logs**: [Training Report](https://wandb.ai/jrahn/chessv62/reports/Training-V6b-2-Fine-Tuning---VmlldzoyNjgzODk3)

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

Background spans early esports content management with leading German clan mTw during competitive gaming's formative years, founding and scaling startup readmore.de (CEO, 2005) which earned two esports awards before acquisition by publishing house Computec Media AG in 2007. Academic foundation in neuro-informatics (University of Lübeck) and business economics & management (Witten/Herdecke University, IPADE Mexico DF, Masters 2012), followed by games publishing startup experience and transition into data-driven digital performance marketing. Continuous learning includes fast.ai deep learning (2018), INRIA scikit-learn MOOC (2021), and Mastering LLMs with Hamel Husain (Maven, 2024). Recognition includes the SEOday 2023 best speaker award for GPT-4 content generation innovation. Active contributor to HuggingFace ecosystem (transformers, datasets, evaluate) and open source frameworks. Current work at Drees & Sommer, building the AI Lab & exploring applications in construction and real estate optimization.

-----

## Research Implications

The RookWorld results suggest that:

1. **Search-free strategic AI** is viable with appropriate training data
1. **Unified architectures** can efficiently handle multiple strategic reasoning tasks
1. **Chain-of-thought training** improves both performance and interpretability
1. **Language model paradigms** apply effectively to structured strategic domains

These findings have implications beyond chess for any domain requiring sequential decision-making under 
