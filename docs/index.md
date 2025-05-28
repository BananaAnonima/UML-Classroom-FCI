<h2><a href= "https://www.mackenzie.br">Universidade Presbiteriana Mackenzie</a></h2>
<h3><a href= "https://www.mackenzie.br/graduacao/sao-paulo-higienopolis/sistemas-de-informacao">Sistemas de Informação</a></h3>


<font size="+12"><center>
*&lt;Sistema Falcão Sombrio para Drones&gt;*
</center></font>

**Conteúdo**

- [Autores](#autores)
- [Descrição do Projeto](#descrição-do-projeto)
- [Análise de Requisitos Funcionais e Não-Funcionais](#análise-de-requisitos-funcionais-e-não-funcionais)
    - [Requisitos Funcionais](#requisitos-funcionais)
    - [Requisitos Não Funcionais](#requisitos-não-funcionais)
- [Diagrama de Atividades](#diagrama-de-atividades)
- [Diagrama de Casos de Uso](#diagrama-de-casos-de-uso)
- [Descrição dos Casos de Uso](#descrição-dos-casos-de-uso)
    - [Autenticar operador](#autenticar-operador)
    - [Fluxo Principal - Autenticar operador](#fluxo-principal---autenticar-operador)
    - [Gerenciar frota](#gerenciar-frota)
    - [Fluxo Principal - gerenciar frota](#fluxo-principal---gerenciar-frota)
    - [Comandar e controlar drones](#comandar-e-controlar-drones)
    - [Fluxo Principal - Comandar e controlar drones](#fluxo-principal---comandar-e-controlar-drones)
    - [Comunicação segura](#comunicação-segura)
    - [Fluxo Principal - Comunicação segura](#fluxo-principal---comunicação-segura)
    - [Registro de missão](#registro-de-missão)
    - [Fluxo Principal - Registro de missão](#fluxo-principal---registro-de-missão)
    - [Monitorar em tempo real](#monitorar-em-tempo-real)
    - [Fluxo Principal - Monitorar em tempo real](#fluxo-principal---monitorar-em-tempo-real)
    - [Auditoria de eventos](#auditoria-de-eventos)
    - [Fluxo Principal - Auditoria de eventos](#fluxo-principal---auditoria-de-eventos)
    - [Navegação Autônoma dos drones](#navegação-autônoma-dos-drones)
    - [Fluxo Principal - Navegação Autônoma dos drones](#fluxo-principal---navegação-autônoma-dos-drones)
    - [Gerenciar atualização/recuperação](#gerenciar-atualizaçãorecuperação)
    - [Fluxo Principal - Gerenciar atualização/recuperação](#fluxo-principal---gerenciar-atualizaçãorecuperação)
    - [Salva dados da missão](#salva-dados-da-missão)
    - [Fluxo Principal - Salva dados da missão](#fluxo-principal---salva-dados-da-missão)
- [Diagrama de Sequência](#diagrama-de-sequência)
- [Diagrama de Classes](#diagrama-de-classes)
- [Diagrama de Estados](#diagrama-de-estados)
- [Diagrama de Implantação](#diagrama-de-implantação)
- [Referências](#referências)


# Autores

João Pedro Mascaro Baccelli | RA: 10224004

# Descrição do Projeto

O Falcão Sombrio é um sistema avançado de controle e operação de drones bélicos autônomos desenvolvido para a empresa multinacional Securus Dynamics, especializada em soluções tecnológicas para defesa militar.

A iniciativa visa substituir a antiga arquitetura de software do Aquila-X — uma frota de drones equipados com inteligência artificial e sensores de última geração — por uma plataforma robusta, segura e distribuída, com foco em tempo real, autonomia, segurança cibernética e escalabilidade.

# Análise de Requisitos Funcionais e Não-Funcionais
### Requisitos Funcionais

| Área                        | Código  | Requisito                                                                 |
|----------------------------|---------|---------------------------------------------------------------------------|
| Central de Controle        | RF01    | Gerenciamento de frotas de drones.                                       |
|                            | RF02    | Controle remoto e autônomo dos drones.                                   |
|                            | RF03    | Dashboard em tempo real com telemetria.                                  |
|                            | RF04    | Definição de zonas de voo e restrições geográficas.                      |
|                            | RF05    | Configuração de missões pré-programadas.                                 |
|                            | RF06    | Sistema de alerta para falhas críticas.                                  |
|                            | RF07    | Atribuição de missões a grupos de drones.                                |
|                            | RF08    | Relatórios de desempenho e eficiência operacional.                       |
| Sistema de Navegação       | RF09    | Sensoriamento via LIDAR, câmeras e GPS.                                  |
|                            | RF10    | Detecção e evasão de ameaças em tempo real.                              |
|                            | RF11    | Operação autônoma baseada em redes neurais.                              |
|                            | RF12    | Identificação e rastreamento de alvos móveis.                            |
|                            | RF13    | Ajuste de rota com base em mudanças ambientais e ameaças.                |
|                            | RF14    | Detecção de obstáculos e manobras evasivas.                              |
|                            | RF15    | Suporte a múltiplos modos de navegação.                                  |
|                            | RF16    | Redundância nos sensores para garantir precisão.                         |
| Gerenciamento de Comunicação| RF17   | Comunicação segura em tempo real.                                        |
|                            | RF18    | Mecanismos de fallback para perda de conexão.                            |
|                            | RF19    | Comunicação via satélite em áreas remotas.                               |
|                            | RF20    | Garantia de integridade dos pacotes de dados.                            |
|                            | RF21    | Sincronização de dados para drones offline.                              |
|                            | RF22    | Suporte a múltiplos canais de comunicação.                               |
|                            | RF23    | Verificação da qualidade do sinal e realocação dinâmica de servidores.   |
| Banco de Dados e Auditoria | RF24    | Logs de missões e eventos críticos.                                      |
|                            | RF25    | Criptografia dos dados e assinaturas digitais.                           |
|                            | RF26    | Banco NoSQL distribuído para dados em tempo real.                        |
| Sistemas Embarcados        | RF27    | Autenticação via biometria e multifator.                                 |
|                            | RF28    | Monitoramento de processos do SO embarcado.                              |

### Requisitos Não Funcionais

| Categoria       | Código  | Requisito                                                                 |
|----------------|---------|---------------------------------------------------------------------------|
| Segurança       | RNF01   | Criptografia de ponta a ponta na comunicação.                            |
|                 | RNF02   | Autenticação multifatorial para maior segurança.                         |
| Desempenho      | RNF03   | Baixa latência entre drones e central.                                   |
|                 | RNF04   | Processamento em tempo real com alta disponibilidade.                     |
| Escalabilidade  | RNF05   | Suporte a grande quantidade de drones simultâneos.                        |
|                 | RNF06   | Expansão eficiente dos servidores distribuídos.                           |
| Disponibilidade | RNF07   | Alta disponibilidade com redundância nos componentes críticos.            |
|                 | RNF08   | Mecanismos de fallback para garantir continuidade operacional.            |
| Usabilidade     | RNF09   | Interface operacional avançada e intuitiva.                               |
|                 | RNF10   | Gerenciamento e controle acessíveis e claros para o operador.             |
| Conformidade    | RNF11   | Conformidade com normas legais e de privacidade.                          |
|                 | RNF12   | Aderência a padrões de segurança e auditoria militar.                     |


# Diagrama de Atividades

![Diagrama de Atividades](diagrama-atividades01.png)
![Diagrama de Atividades](diagrama-atividades02.png)

# Diagrama de Casos de Uso

![Diagrama de Casos de Uso](casos-de-uso.png)

# Descrição dos Casos de Uso

### Autenticar operador
**Ator:** Militares  
**Descrição:** Valida o acesso do operador militar ao sistema através de autenticação com credenciais e/ou biometria.  
### Fluxo Principal - Autenticar operador

| Ações do Ator                     | Ações do Sistema                                      |
|----------------------------------|-------------------------------------------------------|
| 1. Inicia o sistema               |                                                       |
| 2. Informa suas credenciais      | 3. Solicita autenticação multifatorial (biometria)    |
| 4. Fornece a biometria           | 5. Valida os dados inseridos                          |
|                                  | 6. Concede acesso à Central de Controle               |

### Gerenciar frota
**Ator:** Militares  
**Descrição:** Permite o controle da frota de drones cadastrados, atribuindo funções e organizando grupos.  
**Inclusões:** Registro de missão  
**Dependência:** Autenticação válida.
### Fluxo Principal - gerenciar frota
| Ações do Ator                     | Ações do Sistema                                     |
|----------------------------------|------------------------------------------------------|
| 1. Seleciona "Gerenciar Frota"   | 2. Exibe lista de drones disponíveis                 |
| 3. Cria ou edita grupo de drones | 4. Salva alterações e associa drones aos grupos      |
| 5. Define atribuições            | 6. Exibe confirmação e envia dados aos drones        |


### Comandar e controlar drones
**Ator:** Militares  
**Descrição:** Envia comandos diretos para os drones ou inicia modo de operação autônoma.  
**Inclusões:** Comunicação segura  
### Fluxo Principal - Comandar e controlar drones

| Ações do Ator                     | Ações do Sistema                                     |
|----------------------------------|------------------------------------------------------|
| 1. Escolhe drone ou grupo        | 2. Exibe status e modo atual                         |
| 3. Seleciona modo (manual/autônomo) | 4. Estabelece conexão segura com os drones       |
| 5. Envia comandos ou ativa IA    | 6. Executa e exibe resposta da ação em tempo real    |


### Comunicação segura
**Ator:** Militares  
**Descrição:** Garante a troca de mensagens com criptografia entre o operador e os drones.
### Fluxo Principal - Comunicação segura

| Ações do Ator                 | Ações do Sistema                                     |
|------------------------------|------------------------------------------------------|
| 1. Envia comando              | 2. Aplica criptografia ao pacote de dados           |
|                              | 3. Estabelece canal seguro e transmite o pacote     |
|                              | 4. Aguarda confirmação de recebimento                |

### Registro de missão
**Atores:** Militares, IA  
**Descrição:** Armazena detalhes das missões, como localização, tempo, status e eventos ocorridos.
### Fluxo Principal - Registro de missão

| Ações do Ator     | Ações do Sistema                                           |
|------------------|------------------------------------------------------------|
| (automático)     | 1. Inicia gravação da missão ao início da operação         |
|                  | 2. Registra eventos, status e localização em tempo real    |
|                  | 3. Salva os dados no banco distribuído                     |
|                  | 4. Fecha e assina o registro ao fim da missão              |

### Monitorar em tempo real
**Ator:** Militares  
**Descrição:** Permite acompanhar ao vivo a operação dos drones durante a missão.  
**Extensão de:** Registro de missão
### Fluxo Principal - Monitorar em tempo real

| Ações do Ator               | Ações do Sistema                                |
|----------------------------|-------------------------------------------------|
| 1. Acessa tela de monitoramento | 2. Exibe mapa com posição em tempo real     |
| 3. Visualiza sensores, status e rota | 4. Atualiza dados automaticamente     |
|                            | 5. Permite zoom e troca de drone em exibição    |

### Auditoria de eventos
**Ator:** Militares  
**Descrição:** Acompanha eventos importantes durante a missão para posterior revisão e análise.
### Fluxo Principal - Auditoria de eventos

| Ações do Ator                   | Ações do Sistema                                  |
|--------------------------------|---------------------------------------------------|
| 1. Acessa histórico da missão   | 2. Recupera logs de eventos críticos              |
| 3. Filtra por tipo ou horário   | 4. Exibe registros com data/hora, local e status  |
| 5. Exporta ou imprime relatório | 6. Gera arquivo com assinatura digital            |

### Navegação Autônoma dos drones
**Ator:** IA  
**Descrição:** Controla o deslocamento automático dos drones, ajustando a rota com base nos dados de sensores e IA.
### Fluxo Principal - Navegação Autônoma dos drones

| Ações do Ator (IA)           | Ações do Sistema                                  |
|-----------------------------|---------------------------------------------------|
| (automático)                | 1. Processa dados de sensores (LIDAR, GPS, câmeras) |
|                             | 2. Calcula rota ideal                             |
|                             | 3. Ajusta direção e velocidade                    |
|                             | 4. Evita obstáculos e atualiza destino            |

### Gerenciar atualização/recuperação
**Ator:** IA  
**Descrição:** Permite que a IA realize atualizações automáticas ou recuperação de falhas no sistema do drone.
### Fluxo Principal - Gerenciar atualização/recuperação

| Ações do Ator (IA)             | Ações do Sistema                                      |
|-------------------------------|-------------------------------------------------------|
| (automático ou programado)    | 1. Detecta falha ou atualizações pendentes           |
|                               | 2. Inicia processo de atualização                     |
|                               | 3. Reinicia subsistemas conforme necessário          |
|                               | 4. Atualiza status e envia log ao servidor central   |

### Salva dados da missão
**Ator:** IA  
**Descrição:** Armazena todos os dados relevantes da missão de forma segura para posterior análise.
### Fluxo Principal - Salva dados da missão

| Ações do Ator (IA)       | Ações do Sistema                                          |
|--------------------------|-----------------------------------------------------------|
| (automático)             | 1. Coleta telemetria, rota, eventos, status              |
|                          | 2. Gera arquivo de missão com checksum                   |
|                          | 3. Envia para banco de dados NoSQL distribuído           |
|                          | 4. Marca como disponível para visualização e auditoria   |
|                          |                                                           | 
# Diagrama de Sequência

![Diagrama de Sequencia](diagrama-sequencia.png)

# Diagrama de Classes

![Diagrama de Classes](diagrama-classes.png)

# Diagrama de Estados

![Diagrama de Estados](diagrama-estados.png)

# Diagrama de Implantação

![Diagrama de Implantação](diagrama-implantacao.png)

