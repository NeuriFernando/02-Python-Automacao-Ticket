# Automação na abertura de ticket utilizando Python

### Importando Bibliotecas
```import pandas as pd
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.common.action_chains import ActionChains
import time
import pyautogui
import time
import pyperclip
```

### Código Completo
```navegador = webdriver.Chrome()
navegador.maximize_window()
navegador.implicitly_wait(30)
navegador.set_page_load_timeout(220)
navegador.get("link gerenciador de ticket")
navegador.find_element('xpath', '//*[@id="i0116"]').send_keys("e-mail")
navegador.find_element('xpath', '//*[@id="i0116"]').send_keys(Keys.ENTER)
navegador.find_element('xpath', '//*[@id="i0118"]').send_keys("Senha")
navegador.find_element('xpath', '/html/body/div/form[1]/div/div/div[2]/div[1]/div/div/div/div/div/div[3]/div/div[2]/div/div[4]/div[2]/div/div/div/div/input').send_keys(Keys.ENTER)
navegador.find_element('xpath', '/html/body/div/form[1]/div/div/div[2]/div[1]/div/div/div/div/div/div[2]/div[2]/div/div[2]/div/div[2]/div/div[3]/div/div/div[2]/div').click()
navegador.find_element('xpath', '/html/body/div/form/div/div/div[2]/div[1]/div/div/div/div/div/div[3]/div/div[2]/div/div[3]/div[2]/div/div/div[2]/input').click()
time.sleep(5)

for dado in dados:
    requisitado = dado[0]
    grupo = dado[1]
    prioridade = dado[2]
    data = dado[3]
    data=data.strftime("%d/%m/%y")
    tecnico = dado[4]
    hora = dado[5]
    mensagem = f'''
    Agendamento para atendimento presencial. Bitlocker e atualização do sistema operacional (se possível).

    Data: {data}
    Horario: {hora}
    Técnico: {tecnico}   
    
    '''   
    
    navegador.find_element('xpath', '/html/body/div/section/main/div[1]/div/sp-page-row/div/div/span[1]/div/div/div[1]/div[1]/div/div[3]/form/div/sp-variable-layout/div[1]/div/div/div/div/span/div/a/span[2]/b').click()
    time.sleep(3)
    navegador.find_element('xpath', '/html/body/div[3]/div/input').send_keys(requisitado)
    navegador.find_element('xpath', '/html/body/div[3]/div/input').send_keys(Keys.ENTER)
    navegador.find_element('xpath', '/html/body/div[1]/section/main/div[1]/div/sp-page-row/div/div/span[1]/div/div/div[1]/div[1]/div/div[3]/form/div/sp-variable-layout/div[2]/div/div/div[1]/div/span/span/div/div/a/span[2]/b').click()
    time.sleep(3)
    navegador.find_element('xpath', '/html/body/div[4]/div/input').send_keys(grupo)
    time.sleep(2)
    navegador.find_element('xpath', '/html/body/div[4]/div/input').send_keys(Keys.ENTER)
    time.sleep(2)
    navegador.find_element('xpath', '/html/body/div[1]/section/main/div[1]/div/sp-page-row/div/div/span[1]/div/div/div[1]/div[1]/div/div[3]/form/div/sp-variable-layout/div[2]/div/div/div[2]/div/span/div/a/span[2]/b').click()
    time.sleep(3)
    navegador.find_element('xpath', '/html/body/div[5]/div/input').send_keys(prioridade)
    time.sleep(2)
    navegador.find_element('xpath', '/html/body/div[5]/div/input').send_keys(Keys.ENTER)
    navegador.find_element('xpath', '/html/body/div[1]/section/main/div[1]/div/sp-page-row/div/div/span[1]/div/div/div[1]/div[1]/div/div[3]/form/div/sp-variable-layout/div[2]/div/div/div[3]/div/span/textarea').click()
    navegador.find_element('xpath', '/html/body/div[1]/section/main/div[1]/div/sp-page-row/div/div/span[1]/div/div/div[1]/div[1]/div/div[3]/form/div/sp-variable-layout/div[2]/div/div/div[3]/div/span/textarea').send_keys(mensagem)   
    navegador.find_element('xpath', '/html/body/div[1]/section/main/div[1]/div/sp-page-row/div/div/span[1]/div/div/div[1]/div[2]/div/div[1]/div[3]/button').click()
    navegador.find_element('xpath', '//*[@id="xcc091e21dbc34050865f1a2f2a9619f3"]/div/ul/li[1]/span/a').click()
    navegador.find_element('xpath', '//*[@id="x2b49ed74dbb60090865f1a2f2a9619cc"]/div/div[3]/div[3]/a/div/h2').click()
```


