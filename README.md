# Treinando LLM - CP6 (Generative AI)

Fine-tuning de uma LLM local com GPU para responder perguntas sobre a FIAP e conceitos de IA.

> Checkpoint 6 — Generative AI. Entrega: 15/10/2026.

## Integrantes do grupo

| Nome | RM |
| --- | --- |
| Aline Fernandes Zeppelini | RM97966 |
| Camilly Breitbach Ishida | RM551474 |
| Julia Leite Galvão | RM550201 |

## Checklist de requisitos

| # | Requisito do enunciado | Status | Onde está |
| --- | --- | :---: | --- |
| 1 | Selecionar/escolher LLM | ✅ | `TinyLlama/TinyLlama-1.1B-Chat-v1.0` — `notebook_colab.ipynb` |
| 2 | Escolher um problema específico | ✅ | Q&A sobre FIAP e conceitos de IA — `dataset/qa_fiap.jsonl` |
| 3 | Testar diferentes parâmetros | ⬜ | `notebook_colab.ipynb` (seção 6) |
| 4 | Verificar/avaliar o modelo (respostas) | ⬜ | `notebook_colab.ipynb` (seção 7 e 8) |
| 5 | Fazer todos os testes utilizando GPU | ⬜ | GPU T4 (Google Colab) |
| 6 | Criar frontend para o usuário inserir o prompt | ⬜ | `frontend/app.py` |
| 7 | Print da GPU instalada e funcionando no VSCode | ⬜ | `docs/prints/` |
| 8 | Documentação e código no GitHub | ⬜ | este repositório |

## Modelo e técnica

- **Modelo base:** TinyLlama-1.1B-Chat-v1.0
- **Técnica:** fine-tuning com QLoRA (quantização 4-bit + LoRA)
- **Dataset:** `dataset/qa_fiap.jsonl` (30 pares instrução/resposta em português)
- **Bibliotecas:** transformers, peft, bitsandbytes, trl, accelerate

## Estrutura

```
.
├── README.md
├── cp                      # enunciado do checkpoint
├── notebook_colab.ipynb    # treinamento (Colab, GPU T4)
├── dataset/qa_fiap.jsonl
├── frontend/app.py         # interface Gradio
└── docs/
    ├── resultados.md       # parâmetros testados e avaliação das respostas
    └── prints/             # prints da GPU (Colab e VSCode) e do frontend
```

## Como rodar o treinamento

1. Abrir `notebook_colab.ipynb` no Google Colab
2. Ambiente de execução > Alterar tipo > GPU T4
3. Rodar as células em ordem
4. Upload de `dataset/qa_fiap.jsonl` quando pedido

## Como rodar o frontend

```bash
pip install -r frontend/requirements.txt
python frontend/app.py
```

## Stack

Python, PyTorch, Transformers, PEFT (LoRA), BitsAndBytes, TRL, Gradio, Google Colab.
