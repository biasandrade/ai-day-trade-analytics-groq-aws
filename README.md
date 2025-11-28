# 📊 Day Trade Analytics em Tempo Real com IA

> APP inteligente de análise de ações da Nasdaq usando Agentes de IA para apoiar decisões de trading

[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.28+-red.svg)](https://streamlit.io/)
[![AWS](https://img.shields.io/badge/AWS-Deploy-orange.svg)](https://aws.amazon.com/)

## 🎯 O Problema de Negócio

No day trade, **tempo é dinheiro**. Analisar múltiplas fontes de dados, cruzar notícias com indicadores técnicos e tomar decisões rápidas pode significar a diferença entre lucro e prejuízo. 
Este projeto vem para **consolidar análise técnica + sentimento de mercado em uma única interface** para suportar investidores.

## 💡 A Solução

Sistema web que combina:
- **Agentes de IA autônomos** que buscam notícias e dados financeiros em tempo real
- **Análise técnica automatizada** (candlesticks, médias móveis, volume)
- **Infraestrutura AWS** para rodar 24/7 e servir múltiplos usuários

**Resultado:** De 15 minutos de análise manual para insights instantâneos.

## 🎯 Outras Aplicações

A arquitetura de **Multi-Agent AI** deste projeto pode ser adaptada para diversos cenários onde é necessário **consolidar múltiplas fontes de dados em tempo real**:

### 💼 Finanças & Investimentos
- 📊 **Análise de Múltiplos Ativos:** Comparar simultaneamente MSFT, AAPL, GOOGL com dashboard lado a lado
- 🏦 **Análise de Portfólio:** Avaliar risco e diversificação de carteira (ex: 50% AAPL, 30% MSFT, 20% TSLA)
- 💹 **Fundos Imobiliários:** Análise de FIIs com dados de rentabilidade + notícias do setor
- 🌎 **Mercados Internacionais:** Análise cross-market (comparar ações NYSE vs B3)

### 📈 Business Intelligence
- 🛒 **Monitoramento de Concorrentes:** Agentes buscam preços, promoções e reviews de competidores
- 📰 **Análise de Sentimento de Marca:** Consolidar menções em news, redes sociais e reviews
- 🎯 **Pesquisa de Mercado:** Agentes coletam tendências, preferências e pain points de clientes
- 📊 **Dashboard Executivo:** Consolidar KPIs de vendas + dados externos (economia, setor)

### 🚨 Alertas & Automação
- 📲 **Alertas via Telegram/WhatsApp:** "Me avise se TSLA subir 5%" ou "Notifique se aparecer notícia negativa"
- ⏰ **Relatórios Automatizados:** Enviar análise diária dos principais ativos por email
- 🔔 **Monitoramento de Indicadores:** Alertar quando RSI < 30 ou volume > média

### 🧪 Análise Avançada
- 📉 **Backtest de Estratégias:** Simular "comprar quando RSI < 30" nos últimos 6 meses
- 🔮 **Previsão de Preços:** Adicionar modelo LSTM para estimar preço futuro
- 🎲 **Análise de Correlação:** Identificar ativos que se movem juntos (hedging)

**Conceito-chave:** Qualquer problema que exija **coordenação de múltiplas fontes de dados + análise inteligente + decisão rápida** pode usar essa arquitetura multi-agente.

---

## 🎬 Demonstração APP Local

![Sistema local em Ação](images/demolocal.gif)

## 🎬 Demonstração APP AWS

![Sistema aws em Ação](images/demoaws.gif)

## 🚀 Features

- **Multi-Agent AI System**: 3 agentes especializados trabalhando em equipe
  - Agente de Web Search (DuckDuckGo)
  - Agente Financeiro (YFinance)
  - Coordenador Multi-Agente
  
- **Visualizações Interativas**:
  - Gráfico de preços históricos (6 meses)
  - Candlestick chart
  - Médias móveis (SMA e EMA)
  - Volume de negociação

- **Deploy Profissional**:
  - Roda local ou na AWS
  - Configuração para execução em segundo plano
  - Escalável para múltiplos usuários

---

## 🛠️ Stack Técnica

```
Python 3.9+
├── Streamlit         # Interface web
├── Phi Framework     # Orquestração de agentes
├── Groq              # LLM inference (OpenAI GPT)
├── YFinance          # Dados financeiros
├── Plotly            # Visualizações interativas
└── AWS EC2           # Deploy em produção
```

## 📦 Instalação

### Pré-requisitos
- Python 3.9+
- Conta Groq (API key gratuita)
- AWS Account (opcional, para deploy)

### Setup Local

```bash
# Clone o repositório
git clone https://github.com/biasandrade/ai-day-trade-analytics-groq-aws.git
cd ai-day-trade-analytics-groq-aws

# Crie um ambiente virtual
python -m venv venv
source venv/bin/activate  # Linux/Mac
# ou
venv\Scripts\activate  # Windows

# Instale as dependências
pip install -r requirements.txt

# Configure as variáveis de ambiente
cp .env.example .env
# Edite o .env com sua GROQ_API_KEY
```

### Configuração da API Key

1. Crie uma conta gratuita em [Groq](https://console.groq.com/)
2. Gere sua API key
3. Adicione no arquivo `.env`:
```
GROQ_API_KEY=sua_chave_aqui
```

## ▶️ Como Usar

### Execução Local

```bash
streamlit run ba_app.py
```

Acesse: `http://localhost:8501`

### Deploy na AWS

```bash
# Conecte na sua instância EC2
ssh -i sua-chave.pem ec2-user@seu-ip

# Clone e configure o projeto
git clone https://github.com/biasandrade/ai-day-trade-analytics-groq-aws.git
cd ai-day-trade-analytics-groq-aws

pip install -r requirements.txt

# Execute em segundo plano
nohup streamlit run ba_app.py --server.port 8501 &
```

Configure o Security Group da EC2 para liberar a porta 8501.

## 📊 Exemplo de Uso

1. Digite o ticker da ação (ex: MSFT, TSLA, AMZN)
2. Clique em "Analisar"
3. Aguarde enquanto os agentes de IA:
   - Buscam recomendações de analistas
   - Coletam notícias recentes
   - Extraem dados fundamentalistas
4. Visualize os gráficos e insights gerados

## 🎓 Aprendizado

Este projeto me permitiu integrar minhas duas áreas:

**Do lado dos negócios:**
- Apliquei conceitos de trading que uso há 8 anos
- Resolvi um problema real de produtividade
- Pensei em escalabilidade e monetização

**Do lado técnico:**
- Arquitetura de multi-agentes
- Integração de LLMs em aplicações reais
- Deploy em cloud com AWS
- Cache e otimização de performance

## 🔮 Próximos Passos

- [ ] Modelo preditivo de preços (LSTM/Transformer)
- [ ] Alertas de trading (mensagens)

## 📫 Contato

**Beatriz Andrade**
- LinkedIn: [andrade-beatriz](https://www.linkedin.com/in/andrade-beatriz/)
- Email: biasandrade@gmail.com
- GitHub: [@biasandrade](https://github.com/biasandrade)

---
Este projeto faz parte do curso "Business Analytics e Machine Learning Para Projetos de Data Science" do curso de Pós-graduação em Data Scienceda da Data Science Academy.

⭐ Se este projeto te ajudou, deixe uma estrela!

