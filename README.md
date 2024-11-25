import os
import shutil

def organizar_arquivos(diretorio):
    for arquivo in os.listdir(diretorio):
        caminho_arquivo = os.path.join(diretorio, arquivo)
        if os.path.isfile(caminho_arquivo):
            extensao = arquivo.split('.')[-1]
            pasta_destino = os.path.join(diretorio, extensao)
            
            if not os.path.exists(pasta_destino):
                os.makedirs(pasta_destino)
            
            shutil.move(caminho_arquivo, os.path.join(pasta_destino, arquivo))
            print(f"Movido {arquivo} para {pasta_destino}")

# Caminho do diretório a ser organizado
diretorio = "/caminho/para/seu/diretorio"
organizar_arquivos(diretorio)
