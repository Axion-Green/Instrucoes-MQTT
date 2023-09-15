# Projeto IoT - Axion Green (Purificador de Ar)

![Axion Green Logo](https://github.com/Axion-Green.png)

## Introdução

A Internet das Coisas (IoT) é uma tecnologia que conecta dispositivos físicos à internet, permitindo a coleta e o compartilhamento de dados em tempo real. A IoT desempenha um papel crucial em diversos setores, incluindo saúde, transporte, automação residencial e meio ambiente. O projeto Axion Green é um exemplo de aplicação IoT que busca aprimorar a qualidade do ar em ambientes fechados, utilizando um purificador de ar conectado à internet.

## Arquitetura do Projeto

A arquitetura do projeto Axion Green é composta por três componentes principais: Dispositivos IoT, Back-end e Front-end.

### Dispositivos IoT

Os dispositivos IoT incluem sensores de qualidade do ar e um purificador de ar. Os sensores monitoram os níveis de poluentes no ambiente e enviam dados para o back-end por meio de uma conexão sem fio. O purificador de ar é controlado remotamente com base nos dados recebidos.

### Back-end

O back-end é uma plataforma de IoT hospedada em um provedor de serviços em nuvem (CSP). Ele recebe dados dos sensores, os armazena em um banco de dados e oferece serviços de controle para o purificador de ar. O back-end também hospeda uma API para acesso aos dados e controle.

### Front-end

O front-end é uma interface de usuário acessível por meio de um aplicativo móvel ou um site. Ele permite aos usuários visualizar os dados em tempo real, configurar o purificador de ar e receber notificações sobre níveis prejudiciais de poluentes.

![image](https://github.com/Axion-Green/Instrucoes-MQTT/assets/126187491/3a842217-07da-48ab-91bc-4a4b17833b0b)
![link do site](https://react-site-commit.vercel.app/)
## Desenvolvimento

Para implementar este projeto, siga as etapas abaixo:

### Instalação da Plataforma de IoT em um CSP ou VM Local

Você pode optar por usar uma plataforma de IoT existente hospedada em um CSP ou configurar uma VM local com uma plataforma de código aberto, como o AWS IoT Core ou o Microsoft Azure IoT Hub.

### Configuração da Plataforma de IoT

- Crie dispositivos virtuais para representar os sensores e o purificador de ar.
- Defina os protocolos de comunicação apropriados (por exemplo, MQTT).
- Configure políticas de segurança para proteger os dados.

### Especificações de Hardware

- Sensores de qualidade do ar
- Purificador de ar
- Placa de desenvolvimento IoT (por exemplo, NodeMCU ESP8266)
- Conexão à internet
- Plataforma de nuvem (CSP) ou VM local
- Aplicativo móvel ou interface web

## Recursos Necessários para Implementação

### Sensores de Qualidade do Ar

- Modelo: [Inserir modelo]
- Conexão: [Inserir detalhes]
- Protocolo de Comunicação: [Inserir protocolo]

### Dispositivos IoT

- Modelo: NodeMCU ESP8266
- Firmware: [Inserir versão]
- Conexão à Internet: Wi-Fi
- Bibliotecas: [Listar bibliotecas necessárias]

### Plataforma de Nuvem

- CSP: [Inserir CSP]
- Serviços: [Listar serviços utilizados]
- Configurações: [Inserir configurações específicas]

### Front-end

- Tipo: Aplicativo móvel (iOS/Android) ou Interface Web
- Tecnologias: [Listar tecnologias utilizadas]
- Funcionalidades: [Descrever funcionalidades principais]

## Instruções de Uso

### Configuração dos Dispositivos IoT

1. Conecte os sensores de qualidade do ar aos dispositivos IoT.
2. Configure os dispositivos virtuais na plataforma de IoT, definindo protocolos e políticas de segurança.

### Desenvolvimento do Front-end

1. Desenvolva a interface do usuário para visualização dos dados em tempo real.
2. Implemente o controle remoto do purificador de ar.
3. Integre notificações para alertas de poluentes prejudiciais.

### Comunicação MQTT

O protocolo MQTT (Message Queuing Telemetry Transport) é fundamental para a comunicação entre os dispositivos IoT e o back-end da plataforma. Ele permite a troca eficiente de mensagens entre os dispositivos e o servidor MQTT hospedado no back-end. Aqui estão os passos básicos de como funciona o MQTT em nosso projeto:

1. **Publicação de Dados:** Os sensores de qualidade do ar (dispositivos IoT) publicam regularmente dados sobre os níveis de poluentes no ambiente no formato de tópicos MQTT.

2. **Assinatura de Dados:** O back-end assina os tópicos MQTT relevantes para coletar dados dos sensores em tempo real. Isso permite que o back-end receba as informações dos dispositivos.

3. **Controle Remoto:** O front-end também usa o protocolo MQTT para enviar comandos de controle para o purificador de ar. Quando o usuário realiza uma ação, como ligar ou desligar o purificador, o front-end publica um comando no tópico MQTT correspondente.

4. **Recebimento de Comandos:** O purificador de ar (dispositivo IoT) está constantemente ouvindo os tópicos MQTT para comandos. Quando recebe um comando, ele executa a ação correspondente, como ligar ou desligar.

Essa arquitetura baseada em MQTT permite uma comunicação eficaz e em tempo real entre os dispositivos IoT, o back-end e o front-end, garantindo que os dados sejam atualizados e os comandos sejam executados de maneira confiável.

### Health Check

Para verificar o status da aplicação e garantir seu funcionamento adequado, implementamos um endpoint de verificação de status (health check). Este endpoint é um recurso simples que pode ser acessado para verificar se a aplicação está em execução e funcionando corretamente. Eis como funciona:

- **URL do Health Check:** Você pode acessar o health check através da seguinte URL: `http://seu-backend.com/health`.

- **Resposta do Health Check:** Quando o health check é acessado, o back-end deve responder com um status HTTP `200 OK` se a aplicação estiver funcionando normalmente. Isso indica que todos os serviços essenciais estão operacionais.

- **Monitoramento Automatizado:** Você pode configurar ferramentas de monitoramento para verificar regularmente o status da aplicação, automatizando a detecção de problemas.

O health check é uma prática recomendada para garantir a disponibilidade contínua da aplicação e identificar rapidamente quaisquer problemas que possam surgir.

## Entidade Lógica de Dispositivo IoT

A criação de entidades lógicas de dispositivo IoT é fundamental para a representação e o gerenciamento eficientes dos dispositivos na plataforma de IoT. Aqui estão os principais detalhes sobre como essas entidades são criadas:

- **Nome do Dispositivo:** Cada dispositivo IoT é nomeado de acordo com sua função ou localização, tornando mais fácil identificá-lo na plataforma.

- **Tipo de Dispositivo:** Define-se o tipo de dispositivo, como "Sensor de Qualidade do Ar" ou "Purificador de Ar", para categorizar e organizar os dispositivos.

- **Localização:** Registra-se a localização física do dispositivo, o que é útil para acompanhar a distribuição dos sensores e dos purificadores.

- **Protocolo de Comunicação:** Especifica-se o protocolo de comunicação utilizado pelo dispositivo, como MQTT, para garantir uma comunicação adequada.

Essas entidades lógicas permitem que a plataforma gerencie efetivamente os dispositivos IoT, rastreie seus dados e forneça funcionalidades de controle. Cada dispositivo é associado a uma entidade lógica que armazena metadados importantes para o gerenciamento centralizado.

