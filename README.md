🤖 **RPA – Automação de Digitação de Pedidos em Sistema Desktop**

Este projeto implementa um RPA (Robotic Process Automation) que lê um arquivo CSV com pedidos e digita automaticamente os dados em um sistema desktop que não possui API ou integração nativa. Ele é pensado para trabalhar em conjunto com o processo de leitura de pedidos por visão de IA:

a IA gera o CSV com produtos e quantidades;

o RPA pega esse CSV e faz a “digitação robótica” no sistema.

🚀 Objetivo

Substituir a digitação manual e repetitiva de pedidos em um sistema fechado.

Em vez de alguém ficar copiando e colando linha por linha, o RPA:

lê todos os itens de um arquivo CSV;

preenche os campos do sistema exatamente na ordem definida;

confirma cada item;

segue para o próximo até completar toda a lista.

Isso reduz erros humanos, cansaço e tempo gasto em tarefas mecânicas.

🧠 Tecnologias utilizadas

O RPA é construído em cima de:

Python 3 – linguagem base do script.

PyAutoGUI – responsável por controlar mouse e teclado, clicando e digitando como um usuário humano.

Pandas – leitura e manipulação do arquivo CSV com os pedidos.


⚙️ Como funciona (visão geral do fluxo)

De forma genérica, o RPA segue os seguintes passos:

Leitura do arquivo CSV de pedidos

O script abre um arquivo de entrada (por exemplo, o mesmo gerado pela visão de IA).

Lê as colunas que contém as informações necessárias, em geral:

código do produto;

quantidade;

outras colunas podem existir (como origem da imagem), mas o RPA utiliza apenas o que é relevante para digitação.

Interação inicial com o usuário

Uma pequena janela ou mensagem é exibida informando o que o script vai fazer.

O usuário tem a oportunidade de:

confirmar que o sistema-alvo já está aberto;

posicionar o cursor no campo correto (por exemplo, o primeiro campo de código do produto);

cancelar o processo, se necessário.

Validações antes de começar

O RPA pode verificar alguns pontos, por exemplo:

se o Caps Lock está ativado (o que alteraria a forma como os códigos são digitados);

se o usuário já posicionou o foco na janela correta.

Se algo estiver incorreto (por exemplo, Caps Lock ligado), o script avisa o usuário e aguarda até que seja corrigido.

Contagem regressiva e início da automação

Após o usuário confirmar, o RPA pode fazer uma pequena contagem regressiva (por exemplo, alguns segundos), dando tempo para o usuário retornar ao sistema e não tocar mais no teclado/mouse.

A partir daí, o controle do teclado e do mouse é assumido pelo script.

Preenchimento automático dos itens

Para cada linha do CSV:

o RPA digita o código do produto no campo atual;

envia a tecla de confirmação (por exemplo, Enter ou Tab) para mover para o próximo campo;

digita a quantidade correspondente;

confirma o item (por exemplo, pressionando outra tecla específica do sistema);

passa para a próxima linha do CSV e repete o processo.

Se o sistema exigir mais etapas (como clicar em botões, selecionar campos específicos, mudar abas), essas ações também são simuladas pelo script via PyAutoGUI.

Finalização do processo

Ao terminar de percorrer todos os itens do CSV:

o RPA pode exibir uma mensagem informando que o processo foi concluído com sucesso;

opcionalmente, pode registrar um resumo (quantos itens foram processados, se houve alguma linha ignorada, etc.).

📂 Estrutura esperada do arquivo CSV

O arquivo CSV de entrada deve conter, pelo menos, as colunas que representam:

o identificador do produto (código);

a quantidade que precisa ser lançada no sistema.

Outras colunas podem existir, mas o RPA irá usar apenas aquelas que foram configuradas na lógica (por exemplo, código e quantidade). É importante manter:

o nome das colunas conforme configurado;

o arquivo salvo em um local conhecido para o script (mesma pasta do script ou um caminho configurado).

🧰 Requisitos

Para que o RPA funcione de forma estável, são necessários:

Python 3 instalado no computador onde o sistema desktop é acessado.

Instalação das bibliotecas responsáveis por:

automação de mouse e teclado;

leitura de CSV.

Sistema desktop aberto e pronto para receber a digitação:

tela correta;

campos visíveis;

sem janelas de pop-up inesperadas atrapalhando.

Além disso, é importante:

não usar o teclado ou o mouse enquanto o RPA está em execução;

evitar que notificações ou outras janelas apareçam por cima do sistema.


🔗 Integração com outras automações

Este RPA foi pensado para funcionar como a “segunda parte” de um fluxo maior:

A visão de IA lê as imagens de pedidos, identifica produtos e quantidades e gera um CSV estruturado.

O RPA lê esse CSV e faz o lançamento automático desses dados no sistema interno da empresa.

A partir desse ponto, você pode:

acionar impressões de etiquetas;

gerar relatórios;

disparar outros fluxos a partir dos dados já registrados no sistema.

📝 Em resumo, o RPA transforma o CSV de pedidos em ações automáticas dentro do sistema, reproduzindo a digitação humana de forma muito mais rápida, consistente e confiável, liberando tempo para que você foque em atividades que realmente exigem decisão e análise — e não apenas repetir sempre os mesmos cliques e digitações.
