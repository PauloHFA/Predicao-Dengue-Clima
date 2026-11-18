# 📋 Pendências e Próximos Passos — Predicao-Dengue-Clima

> Documento de rastreabilidade do backlog, melhorias sugeridas e itens pendentes para evoluções futuras do **Predicao-Dengue-Clima**.

---

## 🚀 1. Backlog de Melhorias Futuras (Propostas)

### 1.1 Expansão Multi-Estado (Nordeste e Brasil)
- [ ] **Descrição:** Generalizar o pipeline de ingestão e validação (`src/dengue/ingestao/`) para abranger novos estados da região Nordeste e cobertura nacional.
- [ ] **Justificativa:** Atualmente o projeto é homologado e validado de ponta a ponta para o piloto da Paraíba (223 municípios).
- [ ] **Impacto:** Alto (Escalabilidade epidemiológica nacional).

### 1.2 Pipeline de Inferência Semanal Contínua (Automação em Nuvem)
- [ ] **Descrição:** Criar um orquestrador automatizado (ex: GitHub Actions agendado ou Apache Airflow) para buscar dados semanais do InfoDengue/INMET, rodar previsões com LightGBM Quantílico e atualizar o painel interativo automaticamente.
- [ ] **Justificativa:** Transforma o modelo estático em um sistema de alerta precoce operacional para secretarias de saúde.
- [ ] **Impacto:** Alto (Aplicação prática em saúde pública).

---

## ✅ 2. O que já está Concluído (Status Atual)

- **Piloto da Paraíba (223 Municípios):** Ingestão completa e validada por contrato Pandera para SINAN, InfoDengue, INMET, IBGE Censo 2022 e NOAA.
- **Rigor Científico (REG-01 a REG-14):** 14 regras metodológicas implementadas, com suíte de 23 testes automatizados 100% aprovados.
- **Modelagem de Ponta:**
  - *LightGBM Quantílico* com ganho de ~50% de acurácia no horizonte $h=4$ semanas.
  - *DLNM* identificando ótimo biológico de risco entre 26,5°C e 28,5°C.
  - *Estatística Espacial LISA* mapeando clusters nos 223 municípios.
- **Relatórios e Visualizações:** Mapa LISA interativo, Simulador de cenários climáticos em tempo real, Dashboard executivo e Relatório técnico em PDF (5 páginas).

---

## 🛠️ 3. Dependências de Infraestrutura Externa
- APIs públicas do InfoDengue (Fiocruz), INMET e IBGE.
- Opcional: Chaves de API para atualizações contínuas de telemetria climática global (NOAA CPC).
