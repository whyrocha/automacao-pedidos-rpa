🤖 Automação de Pedidos: Visão Computacional (AI) e Digitação (RPA)
Este projeto de dois estágios automatiza a transcrição de pedidos escritos à mão e a digitação subsequente desses itens em um sistema desktop, transformando uma tarefa manual e propensa a erros em um fluxo de trabalho rápido e consistente.


🚀 Objetivo
Eliminar o processo manual e repetitivo de:

Transcrever códigos de produtos e quantidades de imagens (pedidos manuscritos).

Digitar manualmente esses dados em um sistema ERP ou de cotação.

Com este fluxo de trabalho, a IA extrai os dados, e o RPA insere-os, economizando horas de trabalho e garantindo alta precisão na entrada de dados.

🧠 Tecnologias utilizadas

1 - **Python 3**
**OpenAI API** — modelo de visão (gpt-4.1-mini) para ler os pedidos nas imagens
**dotenv (python-dotenv)** — para carregar a variável de ambiente OPENAI_API_KEY do arquivo .env
**Módulos nativos do Python:**
**os** — para listar arquivos e montar caminhos de pastas
**csv** — para gerar o arquivo pedidos.csv
**base64** — para codificar a imagem em base64 e enviá-la para o modelo
