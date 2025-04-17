🧱 **O que é um container?**

- Um **container** é uma forma de empacotar uma aplicação com tudo o que ela precisa para funcionar — código, bibliotecas, dependências, etc. Isto garante que a aplicação funcione da mesma forma em qualquer lugar: no teu computador, num servidor ou na cloud.

⚙️ **Partilha do Sistema Operativo (SO)**

- Todos os containers que estão a correr numa máquina (ou numa máquina virtual) **partilham o mesmo kernel** do sistema operativo.
- Ou seja, **não é criado um sistema operativo completo para cada container**, ao contrário do que acontece com máquinas virtuais.
- Isto torna os containers **mais leves e rápidos** do que as máquinas virtuais.

🔒 **Isolamento entre containers**

Apesar de partilharem o SO, os containers estão **isolados** uns dos outros. Isto significa que:

- Cada container tem acesso apenas aos **recursos que lhe são atribuídos** (CPU, memória, disco, rede, etc.).
- Um container **não consegue ver** os processos dos outros.
- É como se cada container fosse **uma mini-máquina independente**, mesmo estando todos a usar o mesmo sistema operativo por baixo.

🌐 **IP próprio e rede separada**

- Cada container pode ter um **endereço IP próprio**.
- Podem comunicar entre si através de uma **rede virtual** criada pela ferramenta de containers (como o Docker).
- Para o exterior, um container pode parecer uma máquina com o seu próprio IP e portas.

🧠 **Resumo**:

- O **sistema operativo** é o prédio (estrutura, eletricidade, canalização...).
- Cada **container** é um apartamento — tem tudo o que precisas lá dentro (cozinha, casa de banho, móveis), mas todos usam o **mesmo edifício**.
- Os apartamentos **não se veem uns aos outros** e cada um pode ter o seu **número e campainha** (IP).
- O edifício é partilhado, mas cada apartamento é **isolado e autónomo**.

