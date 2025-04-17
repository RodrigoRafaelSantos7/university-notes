# O que é um Sistema Distribuído

Um Sistema Distribuído (SD) é um conjunto de hardware e software interligados através de uma infraestrutura de comunicações, que **cooperam e se coordenam entre si** apenas pela troca de mensagens, para a execução de **aplicações distribuídas**.

# Motivações dos Sistemas Distribuídos

- Acesso generalizado **sem restrições de localização**
	- **Acessibilidade ubíqua (Suporte de utilizadores fixos, móveis, etc...)**
- **Partilha dos recursos distribuídos** pelos **diferente utilizadores**
- **Distribuição da carga** -> melhoria do desempenho
- **Tolerância a falhas** -> melhoria da disponibilidade (- outages)
- **Flexibilidade e adaptabilidade** -> decomposição em sistemas mais simples (modularidade)

# Características fundamentais de um Sistema Distribuído

- Os componentes do sistema **executam de forma concorrente**. Existe portanto paralelismo real o que leva à necessidade da coordenação entre os vários componentes.
- **Falhas independentes** das componentes e da comunicação
	- Impossível determinar se existe uma falha dum componente ou do sistema de comunicações
	- **Necessidade de tratar falhas**
- **Ausência de um relógio global**
	- Existem limites para a precisão dos relógios locais
	- **Impossível user relógios locais** para ordenar todos os eventos
- Nenhum componente tem uma versão exacta instantânea do estado global do sistema
- Os componentes tem uma **visão parcial do estado global** do sistema
	- Os sistemas cooperam através da troca de mensagens que levam tempo não nulo a propagar-se
- Quando ocorrem falhas o estado global pode tornar-se incoerente (mais concretamente as visões parciais do estado global podem tornar-se incoerentes)

# Desafios

## Heterogeneidade

- Lidar com os diferentes tipos de dispositivos, redes, sistemas de operação, linguagens de programação, etc...
- **Soluções que podem ajudar**
	- *Sistemas de Middleware* -> Interface homogénea
	- *Máquinas virtuais* -> permitir executar os mesmos programas em máquinas com diferentes características
	- *[[Container]]* -> permitir executar aplicações, incluindo todas as suas dependências

## Abertura

- A abertura de um sistema distribuído define como pode ser estendido e re-implementado. 
- **Sistemas abertos** possuem interfaces e modelos conhecidos, com evolução controlada por entidades de normalização, permitindo a interoperação de componentes com diferentes implementações. 
- Em contraste, **sistemas proprietários** podem ser **modificados pelo seu "dono"**.
- Uma aplicação de código aberto (open source) disponibiliza o código fonte. O uso da aplicação é regido por licenças que acompanham o código, existindo vários tipos como *Public domain*, *Permissive license*, *Copyleft*, *Noncommercial license* e *Proprietary license*, cada uma com diferentes direitos e restrições de utilização e modificação do código

## Transparência

- A transparência (da distribuição) é a **característica de ocultar do utilizador e do programador a separação física dos componentes de um sistema distribuído**. O **objetivo** é alcançar **simplicidade e flexibilidade**. No entanto, em certas situações, a transparência total pode ser indesejável, como em casos de falha

## Segurança

- Recursos têm valor para os utilizadores. A segurança compreende três aspetos principais: 
	- **confidencialidade** (impedir acesso não autorizado)
	- **integridade** (garantir que os dados não são alterados)
	- **disponibilidade** (assegurar o acesso contínuo aos dados).

## Escala

- A escala de um sistema distribuído refere-se ao seu âmbito e ao número de componentes, abrangendo aspetos como recursos e utilizadores, âmbito geográfico e administrativo.
- Um **sistema escalável** mantém a sua **eficácia mesmo com um aumento significativo no número de recursos e utilizadores**, sem necessitar de alterar a implementação ou a interação dos componentes.
- Para lidar com a escala, podem-se adotar estratégias como dividir e distribuir componentes, usar replicação e caching (abordando o problema da consistência), utilizar geo-replicação e replicação na edge para reduzir o tempo de acesso geográfico, empregar meios de comunicação assíncronos para diminuir dependências e simplificar o sistema através de uniformidade de acesso e mecanismos de designação universais.

## Avarias, Erros e Falhas

- Componentes de sistemas distribuídos podem falhar devido a erros ou avarias, resultando em comportamentos não previstos. Em sistemas distribuídos, as falhas são geralmente parciais e independentes, podendo uma falha num componente levar a um comportamento incorreto noutro e, eventualmente, à falha do sistema
- **Lidar com falhas**
	- Lidar com falhas envolve detetá-las (o que pode ser possível, como com checksums, ou impossível, como num crash remoto, levando à necessidade de funcionar com suspeita de falhas).
	- Outras estratégias incluem mascarar falhas através de re-transmissão ou redundância, tolerar falhas definindo o comportamento na sua presença (parar ou usar redundância), e recuperar componentes falhados, o que envolve recuperar o estado do serviço