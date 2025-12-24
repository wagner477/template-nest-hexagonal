# 🧱 template-nest-hexagonal  
Estrutura base para iniciar serviços NestJS utilizando **Arquitetura Hexagonal (Ports & Adapters)**, com módulos desacoplados, domínio isolado e infraestrutura facilmente substituível.

Este template foi projetado para aplicações reais e escaláveis, incluindo exemplos prontos de:  
- Prisma  
- Docker + docker-compose  
- Módulo User completo  
- Casos de uso isolados  
- Layers bem definidas  
- Padrões corporativos  

---

# 📚 Índice  

- [Visão Geral](#visão-geral)  
- [Arquitetura Hexagonal](#arquitetura-hexagonal)  
  - [Princípios](#princípios)  
  - [Fluxo Geral](#fluxo-geral)  
- [Diagramas C4](#diagramas-c4)  
  - [Nível 1 — Visão de Sistema](#nível-1--visão-de-sistema)  
  - [Nível 2 — Containers](#nível-2--containers)  
  - [Nível-3 — Componentes](#nível-3--componentes)  
- [Estrutura de Pastas](#estrutura-de-pastas)  
- [Instalação](#instalação)  
- [Variáveis de Ambiente](#variáveis-de-ambiente)  
- [Docker](#docker)  
- [Prisma](#prisma)  
- [Módulo User (Exemplo Completo)](#módulo-user-exemplo-completo)  
  - [Entidade](#entidade)  
  - [Portas](#portas)  
  - [Caso de Uso](#caso-de-uso)  
  - [Repositório Prisma](#repositório-prisma)  
  - [Controller](#controller)  
  - [Módulo](#módulo)  
- [Como Criar um Novo Módulo](#como-criar-um-novo-módulo)  
- [Scripts](#scripts)  
- [Boas Práticas](#boas-práticas)  
- [Roadmap](#roadmap)  
- [Licença](#licença)

---

# 🚀 Visão Geral  
Este template oferece uma base completa para desenvolvimento de APIs profissionais utilizando:

- NestJS  
- Arquitetura Hexagonal  
- Prisma + PostgreSQL  
- Docker  
- Clean Code  
- Testes unitários  
- Camadas desacopladas  
- Extensibilidade para mensageria, cache, filas, microsserviços  

Ideal para:

- Empresas que desejam padronizar projetos  
- Microsserviços  
- Serviços escaláveis  
- Times que buscam boas práticas  
- Desenvolvedores que querem aprender Hexagonal na prática  

---

# 🧩 Arquitetura Hexagonal

## Princípios  

✔ Independência de framework  
✔ Domínio isolado  
✔ Casos de uso como núcleo da aplicação  
✔ Entradas e saídas substituíveis  
✔ Adaptação sem alterar o domínio  
✔ Testabilidade elevada  

---

## 🔁 Fluxo Geral

```mermaid
flowchart LR
    A[Request HTTP] --> B[Controller]
    B --> C[Use Case]
    C --> D[Port Out Interface]
    D --> E[Adapter: Prisma Repository]
    E --> F[(PostgreSQL)]
