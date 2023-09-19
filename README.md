# Cotacao
Cotação do dólar

import requests
from datetime import datetime
import time


while True:
    requisicao = requests.get('http://economia.awesomeapi.com.br/last/USD-BRL,EUR-BRL,BTC-BRL')

    requisicao_dic = requisicao.json()
    cotacao_dolar = requisicao_dic['USDBRL']['bid']
    cotacao_euro = requisicao_dic['EURBRL']['bid']
    cotacao_biticoin = requisicao_dic['BTCBRL']['bid']

    print(f'A cotação atual do Dólar é: R$ {cotacao_dolar}')
    print(f'Data da última atualização: {datetime.now()}')

#Atualização a cada:
    time.sleep(1800)

