# Minecraft Survival - Servidor dos Cria
[![Deploy to Oracle Cloud](https://github.com/omifares/minecraft-server/actions/workflows/deploy.yml/badge.svg)](https://github.com/omifares/minecraft-server/actions/workflows/deploy.yml)

Servidor de Minecraft dos guri rodando 24/7 na nuvem (Oracle Cloud) com GitOps, backup automático e monitoramento em tempo real.

## Como Entrar no Servidor

 - IP / Host: minkata.orion.v6.army

 - Porta: 55700

 - Versão: Paper Minecraft (26.2)

 - Modo: Survival

> Dica: Adicione o servidor aos favoritos no Minecraft para checar o status e o ping em tempo real.

## O que temos no servidor?

 - Backups Automáticos Diários: O container de backup salva o estado do mundo e das configurações a cada 24 horas, mantendo histórico de 7 dias. Se alguém explodir a vila com TNT sem querer, o rollback tá no esquema!
 
 - Alta Performance (Paper Engine): Servidor otimizado para manter 20 TPS cravados, pode torar.

 - Proteção de Conta: Sistema de login/senha para garantir que ninguém roube seu inventário.

 - Monitoramento 24/7: Métricas de CPU, memória, RAM e ping direto no Grafana Cloud.

## Arquitetura & Infraestrutura (Nerd Corner)

Para quem tem curiosidade de como a máquina roda por baixo dos panos, o projeto mantém a seguinte estrutura:

- Infra: Oracle Cloud Infrastructure (OCI) - Ubuntu LTS.

- Containers: Docker Compose (itzg/minecraft-server + itzg/mc-backup).

- CI/CD: GitHub Actions + Ansible Playbooks.

- Disaster Recovery: Se a VM for recriada do zero, o Ansible detecta a ausência do mundo e restaura o .tar.gz mais recente do Cloudflare R2 antes de subir o container.

- Observabilidade: Prometheus gravando métricas via remote_write no Grafana Cloud.

## Regras da Casa

- Sem Griefing: Respeite as construções e farms dos outros.

- Farms Extremas: Se a sua farm de derrubar o TPS do servidor, a gente vai trocar uma ideia no Zap.

- Mantenha o Mapa Bonito: Evite deixar árvores voando ou buracos de creeper abertos no spawn.

- Bugs ou Problemas: Avise o quanto antes!
