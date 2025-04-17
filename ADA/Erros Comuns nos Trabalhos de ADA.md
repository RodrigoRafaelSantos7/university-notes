## Constantes e Identificadores

O que fazer:
- Devemos Definir Constantes
- Escolher nomes apropriados para as variáveis, parâmetros, métodos, etc.

## Tipos e Interfaces
O que fazer: 
- Usar as interfaces para declarar os tipos dos objetos

### Exemplo

Declarar e criar um vetor de listas ligadas de inteiros, como comprimentos `vecLen`, e criar as `vecLen` listas.

1. **Declaração da variável**: um vetor de listas de inteiros.
	- `LinkedList<Integer>[] vec;` **ERRO**
	- `List<Integer>[] vec;` **CORRETO**
2. **Criação do vetor:** 
	- `vec = new LinkedList<>[vecLen];` **ERRO**
	- `vec = new List<>[vecLen];`**ERRO**

**Maneira Correta**
```java
List<Integer>[] vec;

createDataStructure();

@SupressWarnings("unchecked")
void createDataStructure( int vecLength ){
	vec = new List[vecLength];
	for (int i = 0; i < vecLength; i++)
		vec[i] = new LinkedList<>();
}
```




