
# 📊 Government Metrics Dashboard

[![Licença MIT](https://img.shields.io/badge/Licença-MIT-green)](https://pt.wikipedia.org/wiki/Licen%C3%A7a_MIT)
[![Python 3.9+](https://img.shields.io/badge/Python-3.9%2B-blue)](https://www.python.org/downloads/)
[![Streamlit](https://img.shields.io/badge/Streamlit-Dashboard-FF4B4B)](https://streamlit.io)
[![PowerBI](https://img.shields.io/badge/Power_BI-Visualiza%C3%A7%C3%A3o-yellow)](https://powerbi.microsoft.com/)

## 📌 Sumário
1. [Visão Geral](#-visão-geral)
2. [Funcionalidades](#-funcionalidades)
3. [Fontes de Dados](#-fontes-de-dados)
4. [Instalação](#-instalação)
5. [Como Usar](#-como-usar)
6. [Exemplos](#-exemplos)
7. [Estrutura do Projeto](#-estrutura-do-projeto)
8. [Contribuição](#-contribuição)
9. [Licença](#-licença)
10. [Contato](#-contato)

---

## 🌐 Visão Geral

Plataforma integrada para monitoramento estratégico de políticas públicas com:

- 📈 **Visualização interativa** de KPIs governamentais
- 🚨 **Sistema de alertas** para metas em risco
- 🔗 **Integração automatizada** com fontes oficiais
- 📱 **Acesso multiplataforma** (web, mobile, tablets)

**Aplicações:**
- Acompanhamento de programas públicos
- Transparência ativa
- Tomada de decisão baseada em dados
- Prestação de contas à sociedade

---

## ✨ Funcionalidades

### Principais Módulos
| Módulo | Descrição | Tecnologia |
|--------|-----------|------------|
| Painel de Metas | Acompanhamento de objetivos | Plotly/Dash |
| Mapa de Indicadores | Georreferenciamento de KPIs | Folium/Geopandas |
| Alerta Automático | Notificações por e-mail/Teams | Airflow |
| Relatório Customizado | Geração de PDFs dinâmicos | ReportLab |

### Exemplo de Código para Alertas
```python
from dashboard import AlertSystem

alerta = AlertSystem(
    kpi='taxa_evasao_escolar',
    meta=0.95,
    periodo='mensal'
)
alerta.verificar_status(valor_atual=0.89)
# Retorna: {"status": "crítico", "desvio": -6.3%}
```

---

## 📊 Fontes de Dados

| Fonte | Dados | Atualização | Acesso |
|-------|-------|-------------|--------|
| SIOP | Orçamento Público | Diária | API |
| SICONV | Convênios | Diária | CSV |
| INEP | Educação | Anual | Microdados |
| DATASUS | Saúde | Mensal | TABNET |

**Estrutura de Metadados:**
```python
indicador = {
    "nome": "taxa_alfabetizacao",
    "fonte": "PNAD/IBGE",
    "meta_2023": 0.98,
    "responsavel": "Secretaria de Educação"
}
```

---

## ⚙️ Instalação

### Requisitos Mínimos
- Python 3.9+
- PostgreSQL 12+
- 8GB RAM (16GB recomendado)

### Instalação via Docker (Recomendado)
```bash
docker-compose up -d
```

### Instalação Manual
```bash
git clone https://github.com/seu-usuario/government-metrics-dashboard.git
cd government-metrics-dashboard
pip install -r requirements.txt
python init_db.py
```

---

## 🚀 Como Usar

### 1. Modo Desenvolvimento
```bash
streamlit run app/main.py
```

### 2. Produção
```bash
gunicorn -w 4 -b :8000 app:server
```

### 3. Atualização de Dados
```bash
python pipelines/update_data.py --fonte todos
```

---

## 🖥️ Exemplos Práticos

### Caso 1: Painel Educacional
```python
from dashboard import EducationDashboard

edu_dash = EducationDashboard(estado="SP")
edu_dash.carregar_dados()
edu_dash.exibir_metas(
    indicadores=["ideb", "evasao"],
    nivel="municipal"
)
```

**Saída:**
![Painel Educacional](https://exemplo.com/print-dashboard-educ.png)

### Caso 2: Relatório de Saúde
```bash
python generate_report.py --tema saude --periodo 2023 --formato pdf
```

---

## 🗂 Estrutura do Projeto

```
government-metrics-dashboard/
├── data/
│   ├── raw/              # Dados brutos das fontes
│   └── processed/        # Dados tratados
├── app/
│   ├── modules/          # Módulos do dashboard
│   ├── templates/        # Layouts HTML
│   └── main.py           # Aplicação principal
├── pipelines/
│   ├── etl/              # Scripts de ingestão
│   └── alerts/           # Lógica de notificações
├── requirements.txt
└── README.md
```

---

## 🤝 Contribuição

1. **Sugira Novos Indicadores** via [issues](https://github.com/seu-usuario/government-metrics-dashboard/issues)
2. **Padrões de Código**:
   ```python
   def calcular_meta(kpi: str, ano: int) -> float:
       """Calcula valor esperado para meta anual
       
       Args:
           kpi: Código do indicador
           ano: Ano de referência
           
       Returns:
           Valor numérico da meta
       """
       return meta
   ```
3. **Fluxo Recomendado**:
   ```bash
   git checkout -b feature/novo-modulo
   git commit -m "Adiciona painel de segurança pública"
   git push origin feature/novo-modulo
   ```

---

## 📜 Licença

```text
Copyright 2023 Government Metrics Dashboard

Permissão é concedida, gratuitamente...
```

---

## 📧 Contato

**Equipe de Gestão Pública**  
[gestao@dashboard.gov.br](mailto:gestao@dashboard.gov.br)  

**Suporte Técnico**  
[suporte@dashboard.gov.br](mailto:suporte@dashboard.gov.br)  

**Acesso ao Sistema**  
[![Portal](https://img.shields.io/badge/Acesse_o_Portal-Portal_Gestão-blue)](https://painel.governo.br)

---

💡 **Para Gestores:**  
Consulte nosso manual de metas:  
[📘 Guia de Metas](docs/manual_metas.pdf)

> **Nota Importante:** Todos os dados são atualizados conforme disponibilidade nas fontes oficiais.
```

### Destaques:
1. **Integração com Sistemas Governamentais**: Conecta-se diretamente às fontes oficiais
2. **Visualização Adaptativa**: Layout responsivo para diferentes dispositivos
3. **Segurança**: Autenticação via gov.br e níveis de acesso
4. **Auditoria**: Log completo de acessos e modificações
5. **Pronto para Produção**: Configuração Docker completa

### Para Implementação:
1. Configure as conexões com suas bases de dados locais
2. Defina metas e thresholds específicos para sua organização
3. Personalize os templates com a identidade visual institucional
4. Integre com sistemas internos via API REST