<h1 align="center">
  Teste da Celcoin para Estágio<br/>
  Candidato Elano Nunes
</h1>


## 01. Sequencias -  Continue as sequências: (1,0) 


| N0 | N1 | N2 | N3 | N4 | N5 | N6 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 2 | 4 | 6 | 8 | 10 | 12 | 14 |
| 1 | 1 | 2 | 3 | 5 | 8 | 13 |
| 3 | 5 | 9 | 17 | 33 | 65 | 129 |
| 1 | 3 | 5 | 7 | 9 | 11 | 13 |

## 02. Lógica de Programação. (3,0)

### a. Escreva um algoritmo que armazene o valor 4 na variável A e o valor 9 na variável B. A seguir, utilizando apenas atribuição entre variáveis, troque o seu conteúdo fazendo com que o valor que está em A passe para B e vice-versa. (0,5)

```c#

public class Swap
{
  public static void Main(string[] args)
  {
    int a, b, aux;
    
    a = 4;
    b = 9;
    
    Console.WriteLine ($"Variavel 'a': {a} e variavel 'b': {b}");
    
    aux = a;
    a = b;
    b = aux;
    
    Console.WriteLine ($"Variavel 'a': {a} e variavel 'b': {b}");
  }
}

```

### b. O Celcoin paga aos seus Agentes (revendedores) um valor fixo de R$0,35 e mais 5% por cada recarga por ele realizada através do aplicativo. Supondo que um Agente realizou a venda de 93 recargas totalizando R$118,00, escreva um algoritmo que calcule e retorne a comissão recebida por esse agente. (0,5)


```c#

public class Comissao
{
  public static void Main(string[] args)
  {
    double valor_vendas; // valor total da venda das recargas
    double valor_fixo = 0.35; // valor fixo recebido pelo Agente Celcoin pelas recargas
    double porcentagem = 0.05; // porcentagem recebida por esse agente
    double comissao;
    
    Console.WriteLine ("Digite o valor total das vendas do Agente Celcoin: ");
    
    valor_vendas = Convert.ToDouble(Console.ReadLine());
    
    comissao = (valor_vendas * porcentagem) + valor_fixo;
    
    Console.WriteLine ($"Valor da comissao do Agente Celcoin: {comissao}");
  }
}

```

### c. Dada a sequência de números: 3, 4, 9, 2, 5, faça um algoritmo que identifique e escreva o maior número desse array e escreva-o ao término da sua execução. (0,5)

````c#

public class MaiorNumero
{
  public static void Main(string[] args)
  {
  
    int[] numeros = { 3, 4, 9, 2, 5 };
    
    int maior = 0, index = 0 ;
    
    for( int i = 0; i < numeros.Length; i++ )
    {
        if( i == 0 )
        {
            maior = numeros[0];
        }
        else if( numeros[i] > maior )
        {
            maior = numeros[i];
            index = i;
        }
    }
    Console.WriteLine( $"O maior numero é o {maior}, que se encontra na posicao {index}. ");
  }
}

````

### d. Dada a sequência de números: 3, 4, 9, 2, 5. Faça um algoritmo que ordene-a em ordem crescente, apresentando a sequência obtida após cada passo. (1,0)

````c#
public class Ordenacao
{
  static void Main(string[] args)
  {
  	int[] numeros = { 3, 4, 9, 2, 5 };
  	
  	Console.WriteLine("Array original: ");
  	
  	imprimeArray(numeros);
  	
  	int[] arrayOrdenado = BubbleSort(numeros);
  
      Console.WriteLine("\nResultado da ordenacao:");
  
  	imprimeArray(arrayOrdenado);
  	
  	Console.ReadLine();
  }
  public static int[] BubbleSort(int[] array) 
  {
  	int tamanho = array.Length;
  	int count = 0;
   
  	for (int i = tamanho - 1; i >= 1; i--)
  	{
  	    for (int j = 0; j<i; j++)
  	    {
      		if (array[j] > array[j + 1])
      		{
      			int aux = array[j];
      			array[j] = array[j + 1];
      			array[j + 1] = aux;
      	 	}
  	    }
  	    
  	    count++;
  	    Console.Write($"\n{count}o passo: ");
  	    
          imprimeArray(array);
  	    
  	}
  	return array;
  }

  public static void imprimeArray(int[] array) 
  {
      foreach (int numero in array) 
      {    
          Console.Write($"{numero} ");
      }
  }
}

````

### e. Seja o seguinte algoritmo: (0,5)
````c#
  Decimal array [] = (5.2, 4.1, 7.5, 8.6);
  Decimal x = 0;
    for(int i = 0; i < array.length(); i++)
    {
      x = x  + array[i];
    }
  Console.write(x / array.length());
````

### O que esse algoritmo faz?

> R: O algoritmo calcula a média aritmética dos valores do array.
> Cada vez que o laço é executado, a variável x recebe o valor do array no index em que está o loop e soma com o valor armazenado nele mesmo.
> Após a execução do laço completamente, x terá como valor 25.4, que é a soma de todas as variavéis armazenadas no array.
> Ao fim, o algoritmo imprime a divisão de x pelo tamanho do array, que é 4.
> 25.4 / 4 = 6.35. 
> Portanto, pode-se afirmar que esse é um algoritmo que calcula a média aritmética dos valores de um array;

## 3. Estrutura de dados: (1,5)

### a. É correto afirmar que: No acesso a registros em um arquivo sequencial, todos os registros são percorridos desde o início até que se encontre o registro desejado? Justifique a sua resposta. 

> A afirmativa está correta. É comum associar os arquivos sequenciais a fitas magnéticas, onde um registro é armazenado ou lido, um após o outro, como na fita. 
> Portanto, ao realizar por exemplo uma busca, é necessário acessar sequencialmente as informações até que se encontre aquela que deseja-se obter.

### b. É correto afirmar que: As filas são estruturas com base no princípio LIFO (last in, first out), no qual os dados que forem inseridos primeiro na fila serão os últimos a serem removidos.

> A afirmativa está incorreta. As filas são estruturas de dados que recebem e removem elementos obedecendo a regra de o primeiro elemento a ser inserido na fila será o primeiro a ser removido. Essa regra é conhecida como FIFO (First in, first out). Portato, esse item está errado.

### c. Uma das formas mais simples e rápidas de busca em uma estrutura de dados ordenada é o método da pesquisa binária, que segue o paradigma da divisão e conquista. Essa afirmação está correta? Justifique sua resposta.

> A afirmação está correta. Suponha que o item que deseja ser obtido esteja no meio da estrutura, a busca já será feita com sucesso (melhor caso). Caso contrário, se o elemento for menor que o item do meio da estrutura, a busca continuará na metade anterior, e se for maior, a busca continuará na metade posterior da estrutura.

## 4. O Modelo Entidade Relacionamento (MER) é um modelo conceitual usado para descrever os objetos (entidades) envolvidos em domínios de negócio, com suas características (atributos) e como elas se relacionam entre si (relacionamento). Observe o MER abaixo e responda as questões abaixo. (3,0)

![image](https://drive.google.com/uc?export=view&id=1FQfHp6-pQHX0MnamLZD-dd_pjtr47hby)

### a. Quais são as entidades apresentadas no MER acima?(0,5)

> Produto, usuário, pedido e transação.

### b. Os relacionamentos geralmente são nomeados com verbos ou expressões que representam a forma como as entidades interagem, ou a ação que uma exerce sobre a outra. Essa nomenclatura pode variar de acordo com a direção em que se lê o relacionamento. Por exemplo: Um aluno cursa várias disciplinas, enquanto uma disciplina é cursada por, pelo menos, um aluno.  Como se dá o relacionamento entre as entidades apresentadas no modelo acima de acordo com a quantidade de objetos envolvidos de cada lado do relacionamento? (1,0)

* Usuário realiza um pedido, enquanto um pedido é realizado por um usuário;
* Um pedido solicita um produto, enquanto um produto é solicitado por um ou mais pedidos;
* Um pedido faz uma transação, enquanto uma transação é feita em um ou mais pedidos;
	
> Todos esses relacionamentos são binários.

### c. Faça o comando SQL para inserir um novo usuário com as suas informações. (0,5)

````SQL
INSERT INTO USUARIO VALUES(1, 'ELANO NUNES CAITANO', 'nunes.elano14@gmail.com', 18/01/2023);
````

### d. Faça uma query em SQL para selecionar todos os pedidos um usuário cujo email seja igual ao seu.(1,0)

````SQL
SELECT * FROM PEDIDOS WHERE usuarioid in (
	SELECT usuarioid FROM USUARIO WHERE email='nunes.elano14@gmail.com'
);
````

## 5. Observe a tabela abaixo e indique os problemas existentes no projeto dessa tabela e faça um Modelo Entidade Relacionamento que apresente as correções necessárias. (1,5) 

![image](https://drive.google.com/uc?export=view&id=16dTnawipFH6_yRxm_NsO4-ip4jRq3LYc)

<p>

  Primeiramente, a tabela não possui exatamente uma entidade. A tabela possui atributos de 3 outras entidades que pode-se supor que existem nesse MER, que seriam Funcionário, Cargo e Projeto. Uma evidência da baixa qualidade dessa tabela é que não há ID da tabela Além de que também há atributos na tabela que não parecem ter relação com outros atributos presentes, como DataFim, que seria a data do fim do projeto, que não tem relação com o nome do cargo e portanto podem pertencer a tabelas separadas.

  Para melhorar isso, eu separei em 4 tabelas: Funcionário, Cargo, Projeto e Alocação. A tabela alocação possui chaves de cada tabela de forma que as conecta. O restante das tabelas possui apenas atributos que dizem respeito às entidades..

</p>


Tabela Funcionário

| funcionarioID | cargoID  | nomeFuncionario |
| :--- | :--- | :--- |
| 1 | 1 | Malon |
| 22 | 1 | Marcos |
| 32 | 2 | José |
| 36 | 3 | Henrique |

Tabela Cargo

| cargoID | nomeCargo  |
| :--- | :--- | 
| 1 | Programador |
| 2 | Analista |
| 3 | UI/UX |

Tabela Projeto

| projetoID | dataFim  
| :--- | :--- | 
| 1 | 07/jul | 
| 3 | 14/jul |
| 8 | 14/jul |
| 12 | 14/jul |

Tabela Alocacao

alocacaoID | funcionarioID | projetoID  | esforco |
| :--- | :--- | :--- | :--- |
| 1 | 1 | 1 | 3 |
| 2 | 1 | 3 | 8 |
| 3 | 22 | 1 | 13 |
| 4 | 22 | 8 | 5 |
| 5 | 22 | 12 | 3 |
| 6 | 32 | 1 | 1 |
| 7 | 32 | 12 | 5 |
| 8 | 36 | 1 | 8 |


DER

![image](https://drive.google.com/uc?export=view&id=1YJ4kN6VPptY8gsd-33muLLrgYJ2aW0KR)

Relacionamentos nesse MER:

* Um Funcionario tem Alocação
* Alocação é feita um Projeto
* Um cargo pertence a um Funcionario