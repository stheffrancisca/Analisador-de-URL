# Analisador-de-URL
Analisador de URL
  - Seu programa deve pedir um link/URL para o usuário, como por exemplo: https://www.hashtagtreinamentos.com/blog
    - Ele deve analisar essa URL dizendo:
        - Domínio: hashtagtreinamentos.com
        - Protocolo: HTTPS (tudo que vem antes de começar o endereço da URL, no caso antes do :)
        - Caminho: /blog (tudo que vem depois do domínio, a partir da primeira / até antes dos parâmetros de busca)
        - Parâmetros de busca: (Tudo que vem depois do ? e são separados entre si por um &. Os links podem ter isso ou não)

Exemplos de URL:

https://www.hashtagtreinamentos.com/blog<br>
https://lp.hashtagtreinamentos.com/inscricao-intensivao-de-python-igfb?origemurl=curso&fonte=portal<br>
https://lp.hashtagtreinamentos.com/inscricao-intensivao-de-python-igfb?origemurl=exercicios

url_analise = input("Insira uma URL")

posicao_doispoints = url_analise.find(":")
posicao_ponto = url_analise.find(".")
posicao_barrafimdominio = url_analise.find("/", posicao_ponto)
posicao_interrogacao = url_analise.find("?")

protocolo = url_analise[:posicao_doispoints]
print("Protocolo", protocolo)

dominio = url_analise[posicao_ponto+1:posicao_barrafimdominio]
print("Domínio", dominio)

caminho = url_analise[posicao_barrafimdominio:posicao_interrogacao]
print("Caminho", caminho)

texto_parametros_url = url_analise[posicao_interrogacao+1:]
parametros_url = texto_parametros_url.split("&")
print("Parâmetros URL", parametros_url)
