# 🛠️ AI-Powered IT Support Agent (RAG + Tool-Use)

> **Projeto Portfólio — Disciplina: Desenvolvendo Software com IA Generativa** > *Curso de Extensão/Especialização em Engenharia de IA* > **Dupla:** Mardemes & [Nome do Colega]  
> **Data de Entrega:** 08/06/2026 | **Nota Alvo:** 10.0 (Peso: 60% da Média Final)

---

## 🌐 Links do Projeto
* **Ambiente de Produção (Demo Online):** [Link do seu Streamlit](https://projeto-portfolio-rag.streamlit.app/)
* **Vídeo Demonstrativo (Pitch & Walkthrough de 3 min):** [Link do YouTube/Loom](https://youtu.be/exemplo-video-demo)

---

## 🎯 1. O Problema Concreto

### Domínio e Contexto
No ambiente corporativo de Engenharia de Software e Operações de TI, os analistas de Suporte de Nível 1 enfrentam uma sobrecarga severa de chamados repetitivos. As informações necessárias para a resolução dos problemas estão fragmentadas em dezenas de manuais técnicos, e-mails de incidentes passados e documentações de arquitetura (frequentemente atualizadas).

### Persona-Alvo
**Analistas de Suporte de TI N1 e Engenheiros de SRE**, que precisam de respostas rápidas, exatas e acionáveis durante janelas críticas de incidentes de infraestrutura.

### Por que LLM + RAG + Tool-Use é a abordagem certa?
1. **RAG (Retrieval-Augmented Generation):** Manuais internos de engenharia mudam constantemente (ex: regras de limites de API, janelas de manutenção). Treinar ou tunar (*fine-tuning*) um modelo seria caro e obsoleto em dias. O RAG garante que o modelo consulte a verdade factual mais recente indexada no banco vetorial.
2. **Tool-Use (Function Calling):** LLMs sofrem de incapacidade crônica de computar lógica matemática exata de cabeça e tendem a alucinar parâmetros técnicos dinâmicos. Delegar cálculos e checagens exatas para funções locais em Python elimina esse problema, garantindo acurácia de 100% em operações lógicas.

### ❓ 3 Perguntas Representativas Respondidas pelo Sistema
1. *"O que é a política de retry em chamadas HTTP e qual a recomendação do nosso guia?"*
2. *"Calcule o tempo total acumulado de 5 chamadas usando backoff exponencial se cada uma demorar inicialmente 13 segundos."*
3. *"Como o Pydantic faz a validação de payload no nosso ecossistema e qual BaseModel herdar?"*

---

## 🏗️ 2. Arquitetura do Sistema

O pipeline foi desenhado sob o princípio de **eficiência de custo e blindagem contra alucinações**, estruturado em quatro camadas principais:
