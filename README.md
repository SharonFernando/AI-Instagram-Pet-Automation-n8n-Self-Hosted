# 🐾 AI Instagram Pet Automation (n8n Self-Hosted)

Sistema totalmente automatizado de geração e publicação de conteúdo no Instagram utilizando IA e arquitetura orientada a eventos.

Em produção desde **novembro de 2025**.

🔗 Projeto em funcionamento:
https://www.instagram.com/focinhosecaudas/

---

## 🚀 Visão Geral

Este projeto automatiza todo o pipeline de criação e publicação de posts no Instagram sobre raças de cães e gatos.

O fluxo realiza automaticamente:

- Execução diária às 8h
- Seleção dinâmica de espécie (cão ou gato)
- Consulta de raças via APIs públicas
- Escolha aleatória de raça
- Geração de legenda com IA
- Busca de imagem específica da raça
- Publicação automática via API oficial do Instagram
- Registro dos dados em Google Sheets

O sistema é totalmente **self-hosted utilizando n8n**, implantado em infraestrutura Oracle Cloud Free Tier.

---

## 🧰 Stack Tecnológica

- n8n (self-hosted)
- Google Gemini API
- TheDogAPI
- TheCatAPI
- Meta Graph API (Instagram)
- Google Sheets API
- Oracle Cloud Infrastructure

---

## 🏗 Arquitetura do Workflow
![DIAGRAMA](images/diagrama.png)

---

## 🧠 Implementação da IA

O sistema utiliza saída estruturada (JSON obrigatório) para garantir compatibilidade com as etapas seguintes do fluxo.

### Principais decisões técnicas:

- Engenharia de prompt com tradução automática da espécie e raça
- Resposta obrigatoriamente em JSON válido
- Parser estruturado para validação da saída
- Formatação determinística para consumo pela API

Essa abordagem reduz falhas e aumenta a confiabilidade em ambiente de produção.

---

## 🔁 Fluxo de Publicação no Instagram

A publicação segue o padrão oficial exigido pela API do Instagram:

1. Criação do container de mídia  
2. Aguardar processamento  
3. Publicação da mídia  
4. Registro dos dados  

Essa implementação garante conformidade com a arquitetura exigida pela Meta Graph API.

---

## 🔐 Gerenciamento de Credenciais

Todas as credenciais são gerenciadas utilizando o sistema nativo de credenciais do n8n.

As credenciais:

- São armazenadas de forma criptografada
- Não ficam expostas no workflow
- Não são versionadas no repositório
- Permanecem isoladas da lógica do fluxo

Para executar o projeto é necessário configurar no n8n:

- Google Gemini API
- TheDogAPI
- TheCatAPI
- Meta Graph API
- Google Sheets OAuth2

---

## ☁️ Infraestrutura

- Instância self-hosted do n8n
- Implantado na Oracle Cloud Free Tier
- Execução automatizada diária
- Estratégia de retry para casos sem imagem disponível
- Persistência de dados para auditoria

A arquitetura foi pensada para ser leve, econômica e estável em ambiente de produção.

---

## 🐳 Como Executar

1. Implantar uma instância self-hosted do n8n
2. Importar o arquivo JSON do workflow
3. Configurar as credenciais no painel do n8n
4. Ativar o workflow

---

## 📈 Status em Produção

- Operando de forma autônoma desde novembro de 2025
- Postagens diárias automáticas
- Zero intervenção manual
- Registro estruturado de todas as publicações

---

## 🔮 Possíveis Evoluções

- Suporte a múltiplas contas
- Publicação em formato carrossel
- Otimização de hashtags com IA
- Integração com métricas de engajamento
- Automação de comentários

---

## 📌 Destaques de Engenharia

- Arquitetura orientada a eventos
- Orquestração de múltiplas APIs
- Integração estruturada com LLM
- Publicação via API oficial do Instagram
- Tratamento de erros e estratégia de retry
- Implantação em ambiente cloud self-hosted

---

## 👨‍💻 Autor

**Sharon Fernando**

Projeto de automação em produção desenvolvido como aplicação real de orquestração de APIs e integração com IA.

