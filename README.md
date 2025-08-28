Hi — Currently, I build language models that learn both strategy and rules

Focus: chess as a clean testbed for rule-aware reasoning. From supervised policies → autoregressive CoT → unified agent-and-environment models.

**Links:** [Repos](https://github.com/jorahn) · [Models & Datasets](https://huggingface.co/jrahn)

## Projects

Current:
- **RookWorld-LM + RLVR** — current iteration leveraging RLVR (GRPO).  
  repo: [jorahn/RookWorld-RLVR](https://github.com/jorahn/rookworld-rlvr)

Open research with LAION "[ROOK: REASONING OVER ORGANIZED KNOWLEDGE](https://laion.ai/notes/rook/)" · [slides](https://docs.google.com/presentation/d/12KMjMfzsnCa6q9BxF2shZ5uesOFe2mQXR7txRHxi3-g/edit)
- **RookWorld-LM** — unified agent+environment; closed-loop self-play.  
  repo: [jorahn/RookWorld](https://github.com/jorahn/RookWorld) · models: [RookWorld-LM-124M](https://huggingface.co/jrahn/RookWorld-LM-124M) / [rookworld_7m_3e_gpt2_124M_hf](https://huggingface.co/jrahn/rookworld_7m_3e_gpt2_124M_hf) · dataset: [rookworld_7m](https://huggingface.co/datasets/jrahn/rookworld_7m) / [rookworld_evol_st1_8m](https://huggingface.co/datasets/jrahn/rookworld_evol_st1_8m) / [rookworld_evol_st1_policy_1m](https://huggingface.co/datasets/jrahn/rookworld_evol_st1_policy_1m)
- **Arbiter** — environment modeling via text; Gym-style I/O.  
  repo: [jorahn/RookWorld](https://github.com/jorahn/RookWorld) · model: [arbitersim_2m_3e_gpt2_124M_hf](https://huggingface.co/jrahn/arbitersim_2m_3e_gpt2_124M_hf) · dataset: [arbiter_6m](https://huggingface.co/datasets/jrahn/arbiter_6m)
- **ROOK-LM** — autoregressive CoT: position → candidates → evals → best.  
  repo: [jorahn/RookWorld](https://github.com/jorahn/RookWorld) · model: [ROOK-LM-124m](https://huggingface.co/jrahn/ROOK-LM-124m)
- **ROOK-CLF** — small classifier baseline using decoder arch; reproducible setup.  
  repo: [jorahn/rook](https://github.com/jorahn/rook) · model: [ROOK-CLF-9m](https://huggingface.co/jrahn/ROOK-CLF-9m) · w&b: [logs](https://wandb.ai/jrahn/ROOK)

Prior:
- **YoloChess** — FEN encoder pretrain + position→move cls.  
  models: [yolochess_mlm_azure-cloud-35](https://huggingface.co/jrahn/yolochess_mlm_azure-cloud-35) · [bertsgambit](https://huggingface.co/jrahn/bertsgambit)  
  datasets: [yolochess_lichess-elite_2211](https://huggingface.co/datasets/jrahn/yolochess_lichess-elite_2211) · [yolochess_deepblue](https://huggingface.co/datasets/jrahn/yolochess_deepblue)
  slides: [link](https://docs.google.com/presentation/d/1Y4N8gDzIfTQ51FrP6YC5hvgYA85TPZqjEM2W1lc79Kg/edit)

-----

**Demo:** [RookWorld Space](https://huggingface.co/spaces/jrahn/RookWorld)