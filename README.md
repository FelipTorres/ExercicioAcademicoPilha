# Pilha
Exercício Acadêmico com o objetivo de fazer uma calculadora cientifica usando estrutura de pilha como classe
namespace ConsoleApp6
{
    class Program
    {
        static void Main(string[] args) 
        {
            Pilha Pilha = new Pilha(100);

            string v;
            int soma,sub, div, multi;

            while (Pilha.Cheia() == false)
            {
                Console.Write("Digite um valor ou operador: ");

                v = Console.ReadLine();

                if (v == "+")
                {
                    soma = Pilha.Desempilhar() + Pilha.Desempilhar();

                    Console.WriteLine(soma);
                    Pilha.Empilhar(soma);
                }

                else if (v == "-")
                {
                    int a = Pilha.Desempilhar();
                    int b = Pilha.Desempilhar();

                    sub = b - a;

                    Console.WriteLine(sub);
                    Pilha.Empilhar(sub);
                }

                else if (v == "*")
                {
                    multi = Pilha.Desempilhar() * Pilha.Desempilhar();

                    Console.WriteLine(multi);
                    Pilha.Empilhar(multi);
                }

                else if (v == "/")
                {
                    int c = Pilha.Desempilhar();
                    int d = Pilha.Desempilhar();

                    div = d / c;

                    Console.WriteLine(div);
                    Pilha.Empilhar(div);
                }

                else
                {
                    Pilha.Empilhar( Convert.ToInt32(v));
                }

            }
        }
    }
    
    class Pilha \\classe pilha para criar metódos
    {
        private int[] vet; // vetor para armazenar os elementos da pilha
        private int topo; // indica a posição do topo

        public Pilha(int tamanho) // CONSTRUTOR
        {
            vet = new int[tamanho];
            topo = 0;
        }
        public void Empilhar(int item)
        {
            vet[topo] = item;
            topo++;
        }
        public int Desempilhar()
        {
            topo--;
            return (vet[topo]);
        }
        public bool Cheia()
        {
            return (topo == vet.Length);
        }
        public bool Vazia()
        {
            return (topo == 0);
        }

    }
}
