# Guia de Proteção e Reconhecimento de Vulnerabilidades

Este documento detalha como identificar vulnerabilidades críticas e aplicar medidas de proteção eficazes para sistemas, dispositivos e dados.

## 1. Entendendo e Reconhecendo Vulnerabilidades

Vulnerabilidade é uma fraqueza no sistema que pode ser explorada por um atacante. Reconhecê-las envolve auditoria constante, análise de logs e uso de ferramentas de varredura (*scanners*).

### Vulnerabilidades de Hardware
São falhas físicas ou de baixo nível (firmware).
* **Exemplos:** Falhas no processador (como o Spectre/Meltdown), portas físicas inseguras ou dispositivos USB maliciosos.
* **Reconhecimento:** Monitorar boletins de segurança de fabricantes (CVEs) e manter o firmware atualizado.

### Vulnerabilidades de Software
Falhas na codificação ou lógica do programa:
* **Synful Knock:** Uma técnica onde um atacante envia uma sequência específica de pacotes TCP para "acordar" um backdoor em roteadores comprometidos.
* **Estouro de Buffer (Buffer Overflow):** Ocorre quando um programa escreve mais dados em um buffer do que ele consegue suportar, podendo corromper a memória ou permitir execução de código malicioso.
* **Entrada Não Validada:** Quando o sistema aceita dados do usuário sem filtragem, permitindo ataques como SQL Injection ou Cross-Site Scripting (XSS).
* **Condição de Corrida (Race Condition):** Falha onde o resultado de um processo depende da temporização ou sequência de eventos incontroláveis.
* **Fragilidades na Prática:** Geralmente causadas por falta de práticas de *DevSecOps* e testes de segurança insuficientes durante o desenvolvimento.
* **Problema de Controle de Acesso:** Falha em garantir que apenas usuários autorizados acessem recursos específicos (Ex: bypass de autenticação).

---

## 2. Estratégias de Proteção

### Protegendo Dispositivos (Endpoints)
* **Princípio do Menor Privilégio:** Conceder acesso apenas ao necessário.
* **Atualizações (Patch Management):** Manter sistemas operacionais e aplicações sempre atualizados.
* **Antivírus/EDR:** Ferramentas de detecção e resposta a ameaças.

### Segurança de Rede Sem Fio (Wi-Fi)
* **Protocolos:** Utilizar WPA3 (ou WPA2-AES no mínimo). Evitar WEP ou WPA (TKIP).
* **Autenticação:** Usar WPA-Enterprise (servidor RADIUS) em ambientes corporativos.
* **Segregação:** Utilizar VLANs para isolar dispositivos de convidados da rede interna.

---

## 3. Criptografia: Conceitos e Prática

**O que é Criptografia?**
É a ciência de transformar informações (texto simples) em um formato ilegível (texto cifrado) usando chaves matemáticas, garantindo a confidencialidade dos dados.

### Como Criptografar: EFS (Encrypting File System)
O EFS é um recurso do Windows que permite criptografar pastas e arquivos individualmente no nível do sistema de arquivos NTFS.

**Passos para usar o EFS:**
1.  **Localize:** Clique com o botão direito no arquivo ou pasta que deseja proteger.
2.  **Propriedades:** Vá em `Propriedades` > `Avançados`.
3.  **Ativar:** Marque a opção "Criptografar o conteúdo para proteger os dados".
4.  **Confirmar:** Clique em OK e aplique as alterações.
*Nota: O EFS vincula a chave de criptografia à conta do usuário. Se a senha do Windows for perdida sem um backup do certificado EFS, os dados podem se tornar inacessíveis permanentemente.*