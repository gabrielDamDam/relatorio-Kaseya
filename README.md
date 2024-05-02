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


## 5. O Incidente

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
