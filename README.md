# Bingo

Projeto de Bingo multiplayer desenvolvido em **Java**, utilizando comunicação cliente-servidor através de **Sockets TCP** e interface gráfica com **Java Swing**.

## Tecnologias

* **Java / JDK 17**
* **IntelliJ IDEA**
* **Java Swing**
* **IntelliJ GUI Designer**
* **TCP Sockets**
* `ServerSocket` e `Socket`
* Threads para comunicação e gerenciamento das conexões

## Sobre o projeto

O projeto é dividido em duas aplicações:

* **Server** — responsável por gerenciar os jogadores, iniciar e encerrar partidas, sortear números e verificar o vencedor.
* **Client** — aplicação utilizada pelos jogadores para se conectar ao servidor e acompanhar sua cartela.

O servidor pode aceitar múltiplos clientes simultaneamente através de conexões TCP.

Durante uma partida, o servidor:

1. Aceita as conexões dos jogadores.
2. Atribui um ID para cada jogador.
3. Gera uma cartela aleatória para cada jogador.
4. Inicia a partida.
5. Sorteia ou recebe números para serem selecionados.
6. Envia os números selecionados para todos os clientes.
7. Verifica quando algum jogador completa sua cartela.

## Interface gráfica

A interface foi desenvolvida utilizando **Java Swing** e o **GUI Designer do IntelliJ IDEA**.

As telas foram inicialmente construídas visualmente no IntelliJ através dos arquivos `.form`. O GUI Designer gera e associa os componentes Swing aos campos presentes nas classes `UI.java`.

Existem duas interfaces principais:

* `server.UI` — interface de configuração e controle do servidor e da partida.
* `client.UI` — interface utilizada pelo jogador para conectar ao servidor e visualizar sua cartela.

## Estrutura do projeto

```text
src/
├── client/
│   ├── ClientConnection.java
│   ├── Main.java
│   ├── UI.java
│   └── UI.form
│
└── server/
    ├── Bingo.java
    ├── ClientMessageManager.java
    ├── ConnectionListener.java
    ├── Main.java
    ├── ServerConnection.java
    ├── UI.java
    └── UI.form
```

## Como executar

### Requisitos

* **JDK 17**
* **IntelliJ IDEA**
* Projeto configurado com o IntelliJ GUI Designer

### Servidor

Execute:

```text
server.Main
```

Na interface do servidor:

1. Defina a porta que será utilizada.
2. Configure o IP.
3. Inicie o servidor.
4. Aguarde os clientes se conectarem.
5. Inicie a partida.

### Cliente

Execute:

```text
client.Main
```

No cliente:

1. Informe o IP do servidor.
2. Informe a porta utilizada pelo servidor.
3. Clique em **Conectar**.
4. Aguarde o servidor iniciar a partida.

Para testes na mesma máquina, pode ser utilizado:

```text
IP: 127.0.0.1
```

Para testes em uma rede local, o cliente deve utilizar o endereço IPv4 da máquina que está executando o servidor.

<img width="696" height="617" alt="image" src="https://github.com/user-attachments/assets/8f3d11c8-4ea3-4691-9d53-53b99ad76938" />
<img width="632" height="485" alt="image" src="https://github.com/user-attachments/assets/ab97d603-ba78-427e-9ba1-0d535c2c9015" />
<img width="1397" height="613" alt="image" src="https://github.com/user-attachments/assets/52146bc6-a1b4-402f-81c3-1bef10167a63" />
