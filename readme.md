<h1 align="center">
  Teste da Celcoin para Estágio
</h1>

<p align="center">
  <a href="#-1">🖥️ Projeto</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
</p>


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

