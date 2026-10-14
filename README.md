 """# 🤖 Robô de Coleta e Consolidação de Vagas (SRE / Tecnologia)

Este é um pipeline automatizado desenvolvido em Python para buscar, filtrar, unificar e consolidar vagas de emprego de múltiplas fontes (**LinkedIn** e **Adzuna**) com foco no **Brasil** e em oportunidades **Remotas**.

Ideal para profissionais e recrutadores que desejam monitorar o mercado de trabalho diariamente de forma automatizada e centralizada.

## 🚀 Funcionalidades

- **Varredura no LinkedIn**: Utiliza o crawler automatizado com `Playwright` para acessar as listagens públicas do LinkedIn de forma segura, simulando navegação humana (scroll), aplicando filtros geográficos estritos para o Brasil e identificando vagas com a flag de trabalho remoto (`f_WT=2`).
- **Consumo da API Adzuna**: Integração oficial com a API do Adzuna para obter vagas qualificadas em tempo real utilizando chaves de acesso.
- **Higiene e Consolidação de Dados**: Mescla os resultados obtidos de ambas as plataformas diretamente em memória, elimina registros duplicados de forma inteligente (mesmo título de vaga na mesma empresa) e gera de forma exclusiva uma base limpa.
- **Exportação Direta**: Gera arquivos prontos para consumo nos formatos Excel (`.xlsx`) e CSV (`.csv`).

## 📁 Estrutura de Arquivos Gerados

O robô mantém seu espaço limpo. Ele não cria arquivos temporários de buscas individuais. Apenas a saída final consolidada é gravada no seu diretório de preferência:

- `vagas_consolidadas.xlsx`: Planilha Excel ideal para análises manuais e filtros visuais.
- `vagas_consolidadas.csv`: Base formatada em CSV (UTF-8 com BOM) ideal para integrações com bancos de dados, BI (PowerBI/Looker Studio) ou pipelines de Inteligência Artificial.

## 🛠️ Tecnologias Utilizadas

- **Python 3.10+**
- **Playwright** (Navegador automatizado em modo headless para scraping)
- **BeautifulSoup4** & **Requests** (Análise sintática do HTML)
- **Pandas** & **OpenPyXL** (Manipulação de dados e exportação de relatórios)
- **Nest-Asyncio** (Suporte à execução assíncrona concorrente em ambientes baseados em notebooks)

## ⚙️ Configurações e Instalação

### Pré-requisitos

Antes de rodar, instale as dependências essenciais do sistema e os pacotes Python:

```bash
pip install playwright nest_asyncio pandas openpyxl requests beautifulsoup4
playwright install chromium
playwright install-deps
```

### Configuração de Parâmetros

No topo do script ou notebook, configure as variáveis de controle de busca:

```python
PALAVRA_CHAVE = "SRE remoto"
LOCALIDADE = "Brasil"
LIMITE_VAGAS = None # Defina um número ou None para trazer todas as vagas possíveis
```

## 📖 Como Executar

1. Abra o arquivo do Jupyter Notebook ou execute o script principal contendo a chamada:
   ```python
   df_vagas = executar_pipeline_e_consolidar()
   ```
2. Acesse a pasta configurada (por padrão no Google Drive em `Colab Notebooks/Vagas`) para visualizar sua planilha consolidada de vagas atualizada.

---
Desenvolvido para simplificar a busca por novas oportunidades de carreira. Sinta-se à vontade para contribuir, abrir Issues ou enviar pull requests!
"""

pasta_vagas = "/content/drive/MyDrive/Colab Notebooks/Vagas"
os.makedirs(pasta_vagas, exist_ok=True)
caminho_readme = os.path.join(pasta_vagas, "README.md")

with open(caminho_readme, "w", encoding="utf-8") as f:
    f.write(readme_content)

print(f"✅ README.md gerado com sucesso em: {caminho_readme}")
