# Sistema_Monitoramento_BLE_ESP32
Este projeto propõe o desenvolvimento de um sistema de monitoramento baseado na tecnologia Bluetooth Low Energy (BLE) utilizando o ESP32, possibilitando o controle e acompanhamento de ambientes públicos ou privados.

# Projeto de Monitoramento Ambiental com ESP32 e Bluetooth Low Energy (BLE)

## Objetivo

Este projeto visa oferecer uma solução eficiente para o monitoramento de ambientes fechados, permitindo o registro e controle do fluxo de pessoas em tempo real. Foi desenvolvido para resolver problemas de segurança em locais que não possuem meios sistemáticos de detecção de presença ou dispositivos, tornando-os vulneráveis a acessos não autorizados.

Utilizando tecnologia IoT baseada no microcontrolador ESP32 e comunicação Bluetooth Low Energy (BLE), o sistema identifica acessos, detecta possíveis intrusos e emite alertas automáticos, elevando significativamente o nível de segurança e controle do ambiente monitorado.

Essa solução é aplicável em diversos contextos, como empresas, instituições de ensino, laboratórios e locais que armazenam informações ou documentos confidenciais, além de espaços públicos com grande circulação de pessoas. Assim, promove ambientes mais seguros, inteligentes e confiáveis.

## Metas Principais

Desde sua idealização, as metas do projeto foram:

- Desenvolver um sistema de apoio ao monitoramento de ambientes.
- Garantir maior controle de acesso.

Para alcançar isso, foram definidas duas interfaces principais:

- **Interface do administrador:** Responsável pelo cadastro e gerenciamento dos dispositivos autorizados a acessar o ambiente.
- **Interface do usuário (aplicativo móvel):** Transforma o celular do usuário em um beacon, permitindo a detecção via Bluetooth pelo ESP32, que atua como central de processamento.

Com essa arquitetura, o sistema identifica em tempo real os dispositivos presentes no local monitorado, proporcionando funcionalidades como:

- Monitoramento do ambiente.
- Visualização dos dispositivos conectados.
- Controle de acesso.
- Reforço da segurança do local.

## Escopo do Projeto

O escopo do projeto inclui:

- Desenvolvimento da interface do administrador.
- Aplicativo móvel para os usuários.
- Registro e monitoramento do fluxo de pessoas via BLE.
- Emissão de alertas de dispositivos não autorizados.
- Relatórios de presença em tempo real.

## Desenvolvimento do Projeto

Ao invés de criar uma interface própria para monitoramento, o projeto utilizou a plataforma **Home Assistant** como interface gráfica para o usuário e como central de controle para envio de notificações.

Para configurar o ESP32, empregou-se o **ESPHome**, ferramenta que facilita habilitar módulos necessários para o monitoramento via Bluetooth, transformando o ESP32 em um tracker baseado em Bluetooth Low Energy.

Além disso, o projeto integrou o protocolo **MQTT**, que atua como canal de comunicação externo. Esse recurso será utilizado em etapas futuras para transmissão das informações de detecção de dispositivos Bluetooth para plataformas externas ou sistemas internos em desenvolvimento.

