# Aula---5---Sistemas-Distribuidos

Atividade prática — Simulador de Conta Compartilhada

- Vamos simular vários atendimentos atualizando o mesmo saldo.
- Primeiro executaremos a aplicação SEM proteção.
- Depois repetiremos COM Lock.
- Compararemos o saldo esperado com o saldo obtido.
- Usaremos apenas a biblioteca padrão do Python: threading e time.

--------------------------------------------------------------------

Passo 1 — crie corrida.py


import threading
import time

saldo = 1000

def sacar(valor):
    global saldo

    saldo_atual = saldo
    time.sleep(0.01)
    saldo = saldo_atual - valor

threads = []

for i in range(10):
    t = threading.Thread(target=sacar, args=(50,))
    threads.append(t)
    t.start()

-------------------------------------------------------------------------

Passo 2 — execute várias vezes

python corrida.py

# Se python não funcionar no Windows:
py corrida.py

# Execute novamente:
python corrida.py
python corrida.py
python corrida.py

-----------------------------------------------------------------------



















