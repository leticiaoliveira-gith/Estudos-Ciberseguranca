# Dispositivos de Proteção e Técnicas de Varredura

Este documento aborda as ferramentas essenciais para proteger redes e os métodos utilizados para identificar vulnerabilidades através de varreduras.

## 1. Dispositivos e Soluções de Segurança

* **Roteadores (Routers):** Atuam como o ponto de entrada e saída da rede, encaminhando pacotes entre redes distintas. Devem ser configurados com regras de acesso (ACLs) para filtrar tráfego indesejado.
* **Firewall:** Barreira de segurança que monitora e controla o tráfego de rede (entrada e saída) com base em regras predefinidas.
* **IPS (Intrusion Prevention System):** Sistema que monitora a rede para identificar atividades suspeitas e **bloqueia** ativamente as ameaças em tempo real.
* **VPN (Virtual Private Network):** Cria um túnel criptografado sobre uma rede pública, permitindo que usuários remotos acessem recursos internos de forma segura.
* **Antivírus:** Software projetado para detectar, isolar e remover malwares (vírus, cavalos de troia, ransomware) de dispositivos.

### Tipos de Firewalls

* **Firewalls de Camada de Rede (Network Layer):** Operam na camada 3 do modelo OSI, filtrando pacotes com base nos endereços IP de origem e destino.

* **Firewalls de Camada de Transporte:** Operam na camada 4, filtrando com base em portas e protocolos (TCP/UDP).

* **Firewalls de Camada de Aplicação:** Inspecionam o conteúdo dos dados (payload) para bloquear ataques específicos a aplicações (ex: SQL Injection, XSS).

* **Context-Aware:** Firewalls inteligentes que consideram o contexto do tráfego (quem está acessando, qual dispositivo, localização, horário) para tomar decisões de segurança.

* **Proxy:** Atua como intermediário entre o cliente e o servidor externo, ocultando a rede interna e filtrando requisições.

* **Proxy Reverso:** Protege servidores internos, recebendo requisições da internet e as encaminhando de forma segura para os servidores da rede privada.

* **NAT (Network Address Translation):** Embora seja uma técnica de rede, firewalls modernos usam NAT para esconder os endereços IP internos da rede externa, aumentando a segurança.

* **Firewalls Baseados em Host:** Softwares instalados localmente em um dispositivo (como o Windows Firewall) que controlam o tráfego específico daquele computador.

---

## 2. Varreduras de Portas (Port Scanning)

O *port scanning* é uma técnica utilizada para descobrir quais portas estão abertas em um host e quais serviços estão rodando nelas.

### O que é o NMAP
O NMAP (*Network Mapper*) é a ferramenta padrão de mercado para descoberta de rede e auditoria de segurança.

### Como funciona
O NMAP envia pacotes específicos para um alvo e analisa as respostas:
* **Porta Aberta:** O serviço responde aceitando a conexão.
* **Porta Fechada:** O serviço responde recusando a conexão.
* **Porta Filtrada:** O firewall bloqueou o pacote, e o NMAP não obteve uma resposta clara.

---

## 3. IDS X IPS

Ambos monitoram o tráfego, mas possuem objetivos distintos:

* **IDS (Intrusion Detection System):** É um sistema de monitoramento **passivo**. Ele analisa logs e tráfego, identifica padrões de ataque e **gera alertas** para os administradores, mas não toma medidas automáticas de bloqueio.

* **IPS (Intrusion Prevention System):** É um sistema **ativo**. Além de detectar, ele atua no fluxo de tráfego, **bloqueando ou descartando** pacotes maliciosos automaticamente para interromper um ataque.

[Image of firewall network security diagram]
[Image of IDS vs IPS architecture]