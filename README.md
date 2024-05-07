# Lista-automatica-Pyton
Preencher lista de produtos automáticamente.

# Exemplo computador de casa

import pyautogui
import time
pyautogui.PAUSE = 0.5

pyautogui.press("Win")
pyautogui.write("chrome")
pyautogui.press("enter")
pyautogui.click(946, 617)

pyautogui.write("https://dlp.hashtagtreinamentos.com/python/intensivao/login")
pyautogui.press("enter")
time.sleep(3)

pyautogui.click(-1154, 590)
pyautogui.write("amandassilvaaiid@gmail.com")
pyautogui.press("tab")
pyautogui.write("102030")
pyautogui.click(-859, 787)
time.sleep(3)

import pandas as pd

tabela = pd.read_csv("produtos.csv")
print(tabela)

for linha in tabela.index:

    pyautogui.click(x=-1200, y=440)
    codigo = tabela.loc[linha, "codigo"]
    pyautogui.write(str(codigo))
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

    obs = str(tabela.loc[linha, "obs"])
    if obs != "nan":
        pyautogui.write(obs)
    pyautogui.press("tab")
    pyautogui.press("enter")
    pyautogui.scroll(5000)
