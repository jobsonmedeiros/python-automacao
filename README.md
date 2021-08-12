# Automação em Python

### Projeto de automação de criação de relatório de vendas e envio por e-mail

DESAFIO por HashtagTreinamentos 

## PROBLEMÁTICA

Criar uma rotina de automação em Python para facilitar o seguinte cenário:

1 - Você ao chegar no trabalho todos os dias, como primeira atividade, deve criar e enviar o relatório de vendas do dia anterior para a administração via e-mail.
2 - Esse relatório textual contém duas informações importantes no corpo do e-mail: Total faturado e total de unidades vendidas.
3 - O relatório de venda fica em uma planilha, no formato .xlsx, na web.

### Tecnologias utilizadas
- ![](https://github.com/jobsonmedeiros/python-automacao/blob/main/python.ico) [Python](https://www.python.org/=16x16) - é uma linguagem de programação que permite trabalhar rapidamente e integrar sistemas de forma mais eficaz.
- ![](https://github.com/jobsonmedeiros/python-automacao/blob/main/anaconda3.ico) [Anaconda](https://www.anaconda.com/), uma plataforma de ciência de dados para Python
- ![](https://github.com/jobsonmedeiros/python-automacao/blob/main/jupyternotebook.ico) [Jupyter Notebook](https://jupyter.org/) - um aplicativo da web de código aberto que permite criar e compartilhar documentos que contêm código ao vivo, equações, visualizações e texto narrativo. Os usos incluem: limpeza e transformação de dados, simulação numérica, modelagem estatística, visualização de dados, aprendizado de máquina etc.

#### Bibliotecas:
-  [Pandas](https://pandas.pydata.org/) - uma ferramenta de análise e manipulação de dados de código aberto rápida, poderosa, flexível e fácil de usar,
construída sobre a linguagem de programação Python
-  [PyAutoGui](https://pypi.org/project/PyAutoGUI/) - um módulo Python de automação de interface de usuário de plataforma cruzada para seres humanos. Usado para controlar programaticamente o mouse e o teclado.
-  [Pyperclip](https://pypi.org/project/pyperclip/) - um módulo Python de plataforma cruzada para copiar e colar funções da área de transferência.

## RESOLUÇÃO

[Código-fonte do projeto](https://github.com/jobsonmedeiros/python-automacao/blob/main/Rotina-Relatorio-Diario.ipynb) comentado.

> Vale ressaltar que mesmo que seguido à risca, o projeto pode não funcionar em outro computador, pois os cliques foram calibrados para os pixels da minha tela:
- A diagonal é de 16.3" (41.4 cm)
- Dimensões do display, largura x altura: 14.2" x 8" (36.1 cm x 20.3 cm)

É possível "calibrar" usando o programa [ColoPix](https://colorpix.softonic.com.br/).

## Descrição do trabalho realizado pelo script

- Emite mensagem de alerta ao usuário informando que iniciará a execução de um procedimento automatizado e que, portanto, o mouse e o teclado não devem ser utilizados até o fim de sua execução;
- Abre o menu iniciar e aciona o navegador Edge (Antigo Explorer);
- Abre uma nova aba e insere o link para acessar a planilha de dados das vendas;
- Faz download da planilha;
- Acessa a planilha;
- Faz a soma do total (em R$) das vendas no período;
- Faz a soma da quantidade de produtos vendidos no período;
- Acessa o gmail e cria um novo email;
- Preenche campos: 'Destinatários' e 'Assunto';
- Preenche com uma mensagem automática o corpo do e-mail, onde constam duas variáveis: {faturamento:,.2f} e {unidades:,}, que terão valores dinâmicos a cada dia;
- Envia o e-mail aos destinatários;
- Emite alerta ao usuário informando que o trabalho foi concluído e que teclado e mouse já estão liberados.


