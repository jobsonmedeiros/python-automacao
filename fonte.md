~~~Python

import pyautogui
import time
import pyperclip
import pandas as pd

pyautogui.PAUSE = 1

## mostra mensagem em prompt ao usuário
pyautogui.alert("ATENÇÃO: Iniciando script, este processo automatizado usará seu mouse e teclado. Deixe-os livres. Clique em OK para continuar!")

#  abrindo o navegador edge

## abre menu iniciar
pyautogui.press("winleft")

## seleciona o edge
pyautogui.write("edge")

## aperta tecla enter
pyautogui.press("enter")

## digita atalho ctrl+t que abre nova aba no navegador
pyautogui.hotkey('ctrl','t')

## define o link para o arquivo que será baixado
linkdodownload = "https://docs.google.com/spreadsheets/d/1jr8bb9KeL4jL_hkTvY3GnzWe-PYywYW6/edit?usp=sharing&ouid=100295986206034552058&rtpof=true&sd=true"

## copia o link para a área de transferência
pyperclip.copy(linkdodownload)

## cola o link na nova aba
pyautogui.hotkey('ctrl', 'v')

## pressiona enter para abrir o link
pyautogui.press('enter')

## aguarda 12 segundos para carregar a página
time.sleep(12)

## click em 'arquivo'
pyautogui.click(90, 125)

## click em 'download'
pyautogui.click(94,427)

## click em 'formato xlsx'
pyautogui.click(360, 422)

## dataframe recebe o arquivo baixado
df = pd.read_excel(r'C:/Users/Dev/Downloads/Python-Aula1/Vendas - Dez.xlsx')

## mostra os dados lidos
display(df)

## soma de todos as vendas realizadas no período
faturamento = df['Valor Final'].sum()

## soma de todas as unidades vendidas
unidades = df['Quantidade'].sum()

#  criando o corpo do email do relatório pro chefe 

## abrindo nova aba
pyautogui.hotkey('ctrl', 't')

## escreve o endereço do serviço de email
pyautogui.write('mail.google.com')

## pressiona enter
pyautogui.press('enter')

## aguarda 10 segundos para a página carregar
time.sleep(10)

## clica em escrever e-mail
pyautogui.click(37, 173)

## ## aguarda 10 segundos para a página carregar
time.sleep(10)

## escreve no campo 'para' o destinatário
pyautogui.write('jobsonmm@gmail.com')

## pressiona tab para ir para o campo 'assunto'
pyautogui.press('tab')
pyautogui.press('tab')

## informa o assunto do e-mail
pyautogui.write('Relatório diário de vendas')

## pressiona tab para ir para o campo 'corpo'
pyautogui.press('tab')

## guarda na variável corpoEmail o conteúdo textual
corpoEmail = f"""
Prezados, bom dia. 

O faturamento de ontem foi de R$ {faturamento:,.2f}.
A quantidade de produtos vendidos foi de {unidades:,} unidades.

Att.,

Jobson Medeiros - TI

"""

## coloca o corpo do email na área de transferência do SO
pyperclip.copy(corpoEmail)

## cola o texto no corpo do email
pyautogui.hotkey('ctrl', 'v')

## atalho para enviar o email
pyautogui.hotkey('ctrl', 'enter')

## alerta ao usuário de trabalho finalizado
pyautogui.alert("AVISO: Processo concluído. Mouse e teclado liberados!")

~~~
