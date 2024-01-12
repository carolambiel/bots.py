# bot de automatizacao de tarefas 
    #cadastro de produtos

import pyautogui
import time
import pandas as pd

pyautogui.PAUSE = 1
pyautogui.press("win")
pyautogui.write("chrome")
pyautogui.press("enter")
loja = ("https://dlp.hashtagtreinamentos.com/python/intensivao/login")  
pyautogui.write(loja)
pyautogui.press("enter")
pyautogui.click(x=425, y=397)
pyautogui.write("carol")
pyautogui.press("tab")
pyautogui.write("raposa10")
pyautogui.press("tab")
pyautogui.press("enter")


tabela = pd.read_csv("produtos.csv.zip")
print(tabela)       


for linha in tabela.index:
    pyautogui.doubleClick(x=270, y=292)
    pyautogui.write(str(tabela.loc[linha, "codigo"]))
    pyautogui.press("tab")
    pyautogui.write(str(tabela.loc[linha, "marca"]))
    pyautogui.press("tab")
    pyautogui.write(str(tabela.loc[linha, "tipo"]))
    pyautogui.press("tab")
    pyautogui.write(str(tabela.loc[linha, "categoria"]))
    pyautogui.press("tab")
    pyautogui.write(str(tabela.loc[linha, "preco_unitario"]))
    pyautogui.press("tab")
    pyautogui.write(str(tabela.loc[linha, "custo"]))
    pyautogui.press("tab")
    #valores obs
    obs = tabela.loc[linha, "obs"]
    if not pd.isna(obs):
        pyautogui.write(str(obs))
    pyautogui.press("tab")
    pyautogui.press("enter")
    pyautogui.scroll(5000)
