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

-