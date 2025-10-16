# 📡 Sistema_Monitoramento_BLE_ESP32

Este projeto propõe o desenvolvimento de um sistema de monitoramento baseado na tecnologia **Bluetooth Low Energy (BLE)** utilizando o **ESP32**, possibilitando o controle e acompanhamento de ambientes públicos ou privados.

---

# 🌿 Projeto de Monitoramento Ambiental com ESP32 e Bluetooth Low Energy (BLE)

## 🎯 Objetivo

Este projeto visa oferecer uma solução eficiente para o monitoramento de ambientes fechados, permitindo o registro e controle do fluxo de pessoas em tempo real. Foi desenvolvido para resolver problemas de segurança em locais que não possuem meios sistemáticos de detecção de presença ou dispositivos, tornando-os vulneráveis a acessos não autorizados.

Utilizando tecnologia IoT baseada no microcontrolador **ESP32** e comunicação Bluetooth Low Energy (BLE), o sistema identifica acessos, detecta possíveis intrusos e emite alertas automáticos, elevando significativamente o nível de segurança e controle do ambiente monitorado.

Essa solução é aplicável em diversos contextos, como empresas, instituições de ensino, laboratórios e locais que armazenam informações ou documentos confidenciais, além de espaços públicos com grande circulação de pessoas. Assim, promove ambientes mais seguros, inteligentes e confiáveis.

## 🏆 Metas Principais

Desde sua idealização, as metas do projeto foram:

- Desenvolver um sistema de apoio ao monitoramento de ambientes.
- Garantir maior controle de acesso.

Para alcançar isso, foram definidas duas interfaces principais:

- ⚙️ **Interface do administrador:** Responsável pelo cadastro e gerenciamento dos dispositivos autorizados a acessar o ambiente.
- 📱 **Interface do usuário (aplicativo móvel):** Transforma o celular do usuário em um beacon, permitindo a detecção via Bluetooth pelo ESP32, que atua como central de processamento.

Com essa arquitetura, o sistema identifica em tempo real os dispositivos presentes no local monitorado, proporcionando funcionalidades como:

- 🔍 Monitoramento do ambiente.
- 📶 Visualização dos dispositivos conectados.
- 🚪 Controle de acesso.
- 🛡️ Reforço da segurança do local.

## 📋 Escopo do Projeto

O escopo do projeto inclui:

- Desenvolvimento da interface do administrador.
- Aplicativo móvel para os usuários.
- Registro e monitoramento do fluxo de pessoas via BLE.
- Emissão de alertas de dispositivos não autorizados.
- Relatórios de presença em tempo real.

## ⚙️ Desenvolvimento do Projeto

Ao invés de criar uma interface própria para monitoramento, o projeto utilizou a plataforma **Home Assistant** como interface gráfica para o usuário e como central de controle para envio de notificações.

Para configurar o ESP32, empregou-se o **ESPHome**, ferramenta que facilita habilitar módulos necessários para o monitoramento via Bluetooth, transformando o ESP32 em um tracker baseado em Bluetooth Low Energy.

Além disso, o projeto integrou o protocolo **MQTT**, que atua como canal de comunicação externo. Esse recurso será utilizado em etapas futuras para transmissão das informações de detecção de dispositivos Bluetooth para plataformas externas ou sistemas internos em desenvolvimento.

---

## 🚀 Passos de Implementação

### 🔧 Instalação do ESPHome

O primeiro passo é garantir que o interpretador **Python** esteja instalado no seu computador. É recomendável instalar a versão mais recente disponível.

Para verificar se o Python já está instalado, abra o terminal e digite:

* python --verison


Se o comando não for reconhecido, a **Microsoft Store** será aberta para que você possa instalar a versão mais recente do Python. Instale seguindo as instruções da loja.

Após a instalação do Python, você estará pronto para prosseguir com a instalação do ESPHome.


<img width="886" height="600" alt="image" src="https://github.com/user-attachments/assets/1609b79d-30c9-48ab-ae5d-bc1dc4448c98" />


Para confirmar se o Python foi instalado corretamente no seu sistema, siga as etapas abaixo:

Abra o terminal ou prompt de comando do seu sistema (no Windows, pode ser o PowerShell ou CMD).

Digite o comando abaixo e pressione Enter para verificar a versão do Python instalada:

* python --version

<br>

<img width="886" height="339" alt="image" src="https://github.com/user-attachments/assets/3c956c50-8943-49ff-9b5f-200a4aefe3fd" />

<br>

Se a instalação do Python foi concluída com sucesso, você pode prosseguir para a próxima etapa: instalar o ESPHome﻿.

Para isso, abra o terminal e execute o comando abaixo:

* pip install esphome

Após a instalação, crie uma nova pasta para o seu projeto ESPHome.

Em seguida, execute o comando wizard do ESPHome para iniciar a configuração do dispositivo.

Importante: substitua no comando o caminho indicado pelo caminho correto onde o Python está instalado no seu sistema.

Este comando wizard ajudará a criar o arquivo de configuração inicial e orientará as próximas etapas para configurar seu ESP32 utilizando o ESPHome.

<br> 

<img width="886" height="217" alt="image" src="https://github.com/user-attachments/assets/60f926b0-e301-4d05-bd70-706eef3923bf" />

<br>

Após iniciar o ESPHome, será necessário escolher um nome para o seu projeto e selecionar o modelo da placa ESP32 que será utilizada.

Essas informações são importantes para configurar corretamente o firmware que será gerado e instalado no dispositivo.

No assistente de configuração (wizard), você deverá:

- Inserir um nome exclusivo para identificar seu dispositivo;
- Selecionar o modelo correto da placa ESP32, para que os parâmetros de hardware sejam ajustados adequadamente.

Esses passos iniciais garantem que o ESPHome crie a configuração compatível e otimize o funcionamento do dispositivo no seu ambiente.

<img width="886" height="477" alt="image" src="https://github.com/user-attachments/assets/34576b18-d475-49a0-a676-1678704bbc2a" />

<br>

Após definir o nome e o modelo da placa ESP32, será necessário escolher a rede Wi-Fi à qual o dispositivo estará conectado.

No processo de configuração, você deverá informar:

- O **SSID** (nome da rede Wi-Fi).
- A **senha** da rede para permitir a conexão segura do ESP32.

Essa etapa é essencial para que o dispositivo possa comunicar-se com a rede local e, consequentemente, com a plataforma de monitoramento.

Certifique-se de que o ESP32 esteja dentro do alcance do sinal da rede selecionada para garantir a conexão estável e o funcionamento adequado do sistema.

<br>

<img width="886" height="652" alt="image" src="https://github.com/user-attachments/assets/861180db-c403-4860-9068-14b20ae332be" />

<br>

ogo após configurar a rede Wi-Fi, será necessário definir uma senha para o recurso de **OTA** ([translate:Over The Air]).

Esta senha é essencial para garantir a segurança durante o processo de atualização remota do firmware do ESP32, evitando que dispositivos não autorizados realizem alterações.

No assistente de configuração, insira uma senha forte e segura para proteção da atualização OTA.
<br>
<img width="886" height="298" alt="image" src="https://github.com/user-attachments/assets/6d959ed4-dba0-41eb-b2bb-d3f58d4fccda" />

<br>

Após seguir os passos anteriores, o arquivo de configuração no formato YAML já estará criado.

Para visualizar e editar esse arquivo no Visual Studio Code, utilize o seguinte comando no terminal:
* code .

 Esse comando abrirá todo o diretório atual no VS Code, permitindo fácil acesso e edição do arquivo `.yaml`.

Caso queira abrir diretamente um arquivo específico, utilize:

* code nome_do_arquivo.yaml

<br>

<img width="886" height="348" alt="image" src="https://github.com/user-attachments/assets/a015f071-9e07-445f-9d27-f281ac42f0cb" />

<br>

Após a criação do arquivo de configuração YAML, para executar o firmware no ESP32, utilize o seguinte comando no terminal:

* Caminho_onde_de_instalação_Python﻿_esphome run nomedoArquivo.yaml

Substitua `Caminho_onde_de_instalação_[translate:Python]_esphome` pelo caminho correto onde o [translate:Python] e o [translate:esphome] estão instalados no seu sistema, e `nomedoArquivo.yaml` pelo nome do arquivo que você criou.

Pronto! As configurações necessárias para usar o [translate:ESPHome] estarão aplicadas e o dispositivo estará pronto para operação.

---

## Configuração do [translate:Home Assistant]

Para iniciar, será necessário criar uma máquina virtual para o [translate:Home Assistant]. Para isso, é preciso ter instalado o [translate:VirtualBox] ou outro programa que permita o gerenciamento de máquinas virtuais.

Essa máquina virtual será o ambiente onde o [translate:Home Assistant] será executado, permitindo a integração com seus dispositivos ESP32 configurados via [translate:ESPHome].

<br>

<img width="886" height="209" alt="image" src="https://github.com/user-attachments/assets/efac9c53-1466-448d-8f91-a7cf4c02c885" />

<br>

#### Instalação do Desktop Virtual do [translate:Home Assistant]

Após a instalação inicial, é necessário instalar o desktop virtual do [translate:Home Assistant].

Você pode encontrar o instalador e as instruções oficiais na página abaixo:

[Windows - Home Assistant](https://www.home-assistant.io/installation/windows/)

Nesta página, você terá acesso a todas as informações para baixar e configurar o [translate:Home Assistant] usando uma máquina virtual no Windows, incluindo pré-requisitos como o [translate:VirtualBox] e configuração do ambiente virtualizado para executar o sistema.

Seguindo essas orientações, o seu ambiente estará preparado para integrar o sistema de monitoramento baseado no ESP32 com [translate:ESPHome].

<br>

<img width="886" height="408" alt="image" src="https://github.com/user-attachments/assets/81db7327-c5ea-408c-b0cf-59807e9d8e8d" />
<br>

Após a instalação do [translate:VirtualBox], é necessário abrir o programa para iniciar o processo de criação da máquina virtual para o [translate:Home Assistant

<br>
<img width="886" height="550" alt="image" src="https://github.com/user-attachments/assets/c565684e-672c-43a5-a0f3-60b7a93537f1" />

<br>


Durante o processo de criação da máquina virtual no VirtualBox, escolha as seguintes especificações:

- **Type:** Linux  
- **Version:** Other Linux (64-bit)

Em seguida, prossiga para definir a capacidade da máquina virtual, configurando:

- Quantidade de memória RAM (mínimo recomendado: 2 GB)  
- Número de CPUs (mínimo recomendado: 2 CPUs)


<br>
<img width="881" height="555" alt="image" src="https://github.com/user-attachments/assets/cb66ff31-3edb-45ff-9445-d67a98aac027" />
<br>
Após criar a máquina virtual no VirtualBox, é necessário selecionar o arquivo **.vdi** da máquina virtual que foi baixada e descompactada.
1. Clique no ícone de pasta ao lado da opção **Disco Rígido** para abrir o navegador de arquivos.
2. Navegue até o local onde o arquivo **.vdi** foi salvo.
3. Selecione o arquivo **.vdi** correspondente à sua máquina virtual.
4. Confirme para vincular o arquivo à máquina virtual.
<br>
<img width="886" height="547" alt="image" src="https://github.com/user-attachments/assets/9e2fd0e7-05b8-4ea7-942c-ab239ce67731" />
<br>


Após selecionar e criar a máquina virtual, é necessário realizar algumas configurações adicionais para garantir o correto funcionamento do sistema.

### Ativando EFI

1. No VirtualBox, selecione a máquina virtual criada.
2. Clique em **Settings** (Configurações).
3. Vá para a aba **System**.
4. Marque a opção **Enable EFI (special OSes only)**.
<br>
<img width="886" height="551" alt="image" src="https://github.com/user-attachments/assets/37b2ed00-3eac-4993-af51-535a001130db" />
<br>
Logo após configurar o EFI, acesse a aba **Network** nas configurações da máquina virtual.

- Selecione a opção **Modo Bridged** para que a máquina virtual se conecte diretamente à rede física.
- Essa configuração permite que a máquina virtual receba um endereço IP da mesma rede do host, facilitando a comunicação e integração.

Como mostra a imagem a seguir:  
<br>
<img width="886" height="615" alt="image" src="https://github.com/user-attachments/assets/888cf9ea-5de0-4f57-ace5-c9a98061e476" />
<br>

Essa configuração é fundamental para que o [translate:Home Assistant] possa comunicar-se adequadamente na rede local.

Após salvar todas as configurações necessárias, você já pode iniciar a máquina virtual do [translate:Home Assistant].

Ao iniciar, o sistema exibirá o endereço IP de acesso da máquina, que poderá ser utilizado para acessar a interface web do [translate:Home Assistant].

### Como acessar:

- Utilize um navegador web e digite o endereço IP exibido, seguido da porta `8123`, por exemplo:  
  `http://192.168.x.x:8123`

