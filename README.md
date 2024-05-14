# Simulação de Cruzamento de Trilhos de Trem

Este projeto consiste em uma simulação de um cruzamento entre uma linha ferroviária e uma via de veículos automotivos, implementado em linguagem C++ com o FreeRTOS. O objetivo é demonstrar como usar semáforos para sincronizar o acesso a recursos compartilhados, garantindo a passagem segura de trens e carros pelo cruzamento.

## Funcionalidades

- Cada trem e carro é representado por uma thread.
- Um semáforo (cancela) é usado para evitar colisões.
- O acesso ao cruzamento é gerenciado usando semáforos.
- Os trens têm prioridade sobre os carros.
- Uma interface simples mostra o estado atual dos trens e carros, bem como a situação da cancela.

## Requisitos

- FreeRTOS
- Conhecimento básico de programação em C
- Conhecimento básico de multithreading

## Como usar

1. **Configuração do Ambiente**: Certifique-se de ter instalado e configurado seu ambiente de desenvolvimento corretamente.

2. **Compilação**: Compile o código-fonte usando o compilador adequado para o seu sistema.
3. 
## Estrutura do Código

- `main.c`:  função `main` e as definições das tarefas.
- `taskTrem`: Função que simula o comportamento dos trens.
- `taskCarro`: Função que simula o comportamento dos carros.
- `passarTrem`: Função que simula a passagem de um trem pelo cruzamento.
- `passarCarro`: Função que simula a passagem de um carro pelo cruzamento.

## Semáforos

Dois semáforos são utilizados:
- `semaforo_cruzamento`: Controla o acesso ao cruzamento pelos carros. Quando um carro se aproxima do cruzamento, ele verifica se o semáforo está livre. Se estiver livre, o carro passa pelo cruzamento. Se não estiver livre, o carro aguarda na fila até sua vez.
- `semaforo_cancela`: Controla o estado da cancela. Quando um trem se aproxima do cruzamento, ele adquire o semáforo para garantir que a cancela seja fechada. Após finalizar a travessia, o trem libera o semáforo para que a cancela seja aberta.

## Video Demonstrativo

https://youtu.be/ustrKh9d0x4

## Licença

Este projeto é licenciado sob a Licença MIT. Consulte o arquivo [LICENSE](LICENSE) para obter mais detalhes.
