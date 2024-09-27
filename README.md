# Controle-de-produto
O código é um exemplo simples de uma aplicação console em C# que simula o gerenciamento de um produto, permitindo ao usuário inserir dados sobre o produto e atualizar sua quantidade.


Primeira criação : 
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Produto p = new Produto();
            Console.WriteLine(" Entre os dados do produto : ");
            Console.WriteLine("Nome : ");
            p.Nome = Console.ReadLine();
            Console.WriteLine("Preço: ");
            p.Preço = double.Parse(Console.ReadLine(), CultureInfo.InvariantCulture);
            Console.WriteLine("Quantidade : ");
            p.Quantidade = int.Parse(Console.ReadLine());

            Console.WriteLine(" Dados do produto " + p);


            Console.WriteLine();
            Console.WriteLine(" Digite o número de produtos a ser adicionados");
            int qte = int.Parse(Console.ReadLine());
            p.AdicionarProdutos(qte);
            Console.WriteLine("Dados atualizados : "+ p);

        }
    }
}

Criação de classe : 

    internal class Produto
    {
        public String Nome;
        public Double Preço;
        public int Quantidade;

        public double Valortotalemestoque()
        {
            return Quantidade * Preço;


        }
        public void AdicionarProdutos(int quantidade)
        {
            Quantidade += quantidade;
        }
                    

        public override string ToString()
        {
            return Nome + ",$ " + Preço.ToString("F2",CultureInfo.InvariantCulture);
        }
    }
}

