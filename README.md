# AtividadepPoo
   class Aluno
   {
    public string RA, Nome;
    public double NotaProva, NotaTrabalho, NotaFinal;

    public void ReceberDados()
    {
        Console.Write("RA: ");
        RA = Console.ReadLine();

        Console.Write("Nome: ");
        Nome = Console.ReadLine();

        Console.Write("Nota Prova: ");
        NotaProva = double.Parse(Console.ReadLine());

        Console.Write("Nota Trabalho: ");
        NotaTrabalho = double.Parse(Console.ReadLine());
    }

    public void CalcularMedia()
    {
        NotaFinal = (NotaProva + NotaTrabalho) / 2;
    }

    public bool CalcularNotaFinal()
    {
        if (NotaFinal >= 60)
        {
            Console.WriteLine("Aprovado!");
            return true;
        }
        else
        {
            double precisa = 60 - NotaFinal;
            Console.WriteLine("Prova final. Precisa tirar: " + precisa);
            return false;
        }
    }

    public void ImprimirNotaFinal()
    {
        Console.WriteLine("Média: " + NotaFinal);
    }


class Program
{
    static void Main()
    {
        Aluno a = new Aluno();

        a.ReceberDados();
        a.CalcularMedia();
        a.ImprimirNotaFinal();
        a.CalcularNotaFinal();
    }
}

using System;

class ContaBancaria
{
    public string NumeroConta, NomeTitular;
    public double Saldo;

    public void ReceberDados()
    {
        Console.Write("Número da conta: ");
        NumeroConta = Console.ReadLine();

        Console.Write("Nome do titular: ");
        NomeTitular = Console.ReadLine();

        Console.Write("Saldo inicial: ");
        Saldo = double.Parse(Console.ReadLine());
    }

    public void Depositar()
    {
        Console.Write("Valor para depositar: ");
        double valor = double.Parse(Console.ReadLine());
        Saldo += valor;
    }

    public void Sacar()
    {
        Console.Write("Valor para sacar: ");
        double valor = double.Parse(Console.ReadLine());

        if (valor <= Saldo)
            Saldo -= valor;
        else
            Console.WriteLine("Saldo insuficiente!");
    }

    public void MostrarSaldo()
    {
        Console.WriteLine("Conta: " + NumeroConta);
        Console.WriteLine("Titular: " + NomeTitular);
        Console.WriteLine("Saldo: " + Saldo);
    }
}

class Program
{
    static void Main()
    {
        ContaBancaria c = new ContaBancaria();

        c.ReceberDados();
        c.Depositar();
        c.Sacar();
        c.MostrarSaldo();
    }
}

using System;

class Produto
{
    public string CodigoProduto, NomeProduto;
    public double Preco;
    public int QuantidadeEstoque;

    public void ReceberDados()
    {
        Console.Write("Código: ");
        CodigoProduto = Console.ReadLine();

        Console.Write("Nome: ");
        NomeProduto = Console.ReadLine();

        Console.Write("Preço: ");
        Preco = double.Parse(Console.ReadLine());

        Console.Write("Quantidade: ");
        QuantidadeEstoque = int.Parse(Console.ReadLine());
    }

    public void AdicionarEstoque()
    {
        Console.Write("Quantidade para adicionar: ");
        int qtd = int.Parse(Console.ReadLine());
        QuantidadeEstoque += qtd;
    }

    public void RemoverEstoque()
    {
        Console.Write("Quantidade para remover: ");
        int qtd = int.Parse(Console.ReadLine());

        if (qtd <= QuantidadeEstoque)
            QuantidadeEstoque -= qtd;
        else
            Console.WriteLine("Estoque insuficiente!");
    }

    public void MostrarProduto()
    {
        Console.WriteLine("Código: " + CodigoProduto);
        Console.WriteLine("Nome: " + NomeProduto);
        Console.WriteLine("Preço: " + Preco);
        Console.WriteLine("Estoque: " + QuantidadeEstoque);
    }
}

class Program
{
    static void Main()
    {
        Produto p = new Produto();

        p.ReceberDados();
        p.AdicionarEstoque();
        p.RemoverEstoque();
        p.MostrarProduto();
    }
}

using System;

class CalculadoraDeSalario
{
    public string NomeFuncionario;
    public double SalarioBase, SalarioFinal;

    public void ReceberDados()
    {
        Console.Write("Nome: ");
        NomeFuncionario = Console.ReadLine();

        Console.Write("Salário base: ");
        SalarioBase = double.Parse(Console.ReadLine());

        SalarioFinal = SalarioBase;
    }

    public void CalcularAumento(double percentual)
    {
        SalarioFinal += SalarioFinal * percentual / 100;
    }

    public void CalcularDesconto(double percentual)
    {
        SalarioFinal -= SalarioFinal * percentual / 100;
    }

    public void MostrarSalario()
    {
        Console.WriteLine("Nome: " + NomeFuncionario);
        Console.WriteLine("Salário base: " + SalarioBase);
        Console.WriteLine("Salário final: " + SalarioFinal);
    }
}

class Program
{
    static void Main()
    {
        CalculadoraDeSalario c = new CalculadoraDeSalario();

        c.ReceberDados();
        c.CalcularAumento(10);   
        c.CalcularDesconto(5);   
        c.MostrarSalario();
    }
}

using System;

class Hospede
{
    public string Nome, Cpf, Telefone;

    public void ReceberDados()
    {
        Console.Write("Nome: ");
        Nome = Console.ReadLine();

        Console.Write("CPF: ");
        Cpf = Console.ReadLine();

        Console.Write("Telefone: ");
        Telefone = Console.ReadLine();
    }

    public void MostrarDados()
    {
        Console.WriteLine("Nome: " + Nome);
        Console.WriteLine("CPF: " + Cpf);
        Console.WriteLine("Telefone: " + Telefone);
    }

    public void AtualizarTelefone(string novoTelefone)
    {
        Telefone = novoTelefone;
    }
}

class Reserva
{
    public string NumeroReserva;
    public int QuantidadeDiarias;
    public double ValorDiaria, ValorTotal;

    public void ReceberDadosReserva()
    {
        Console.Write("Número da reserva: ");
        NumeroReserva = Console.ReadLine();

        Console.Write("Diárias: ");
        QuantidadeDiarias = int.Parse(Console.ReadLine());

        Console.Write("Valor da diária: ");
        ValorDiaria = double.Parse(Console.ReadLine());
    }

    public void CalcularTotal()
    {
        ValorTotal = QuantidadeDiarias * ValorDiaria;
    }

    public void AplicarDesconto(double percentual)
    {
        ValorTotal -= ValorTotal * percentual / 100;
    }

    public void MostrarReserva()
    {
        Console.WriteLine("Reserva: " + NumeroReserva);
        Console.WriteLine("Diárias: " + QuantidadeDiarias);
        Console.WriteLine("Valor diária: " + ValorDiaria);
        Console.WriteLine("Total: " + ValorTotal);
    }
}

class Program
{
    static void Main()
    {
        Hospede h = new Hospede();
        Reserva r = new Reserva();

        h.ReceberDados();
        r.ReceberDadosReserva();

        r.CalcularTotal();
        r.AplicarDesconto(10); 

        Console.WriteLine("\n--- Hóspede ---");
        h.MostrarDados();

        Console.WriteLine("\n--- Reserva ---");
        r.MostrarReserva();
    }
}

using System;

class Cliente
{
    public string Nome { get; set; }
    public string Cpf { get; set; }
    public string Cidade { get; set; }

    public void ExibirDados()
    {
        Console.WriteLine($"Cliente: {Nome} | CPF: {Cpf} | Cidade: {Cidade}");
    }

    public string RetornarApresentacao()
    {
        return $"Cliente {Nome} de {Cidade}";
    }
}

class Vendedor
{
    private double percentualComissao;

    public string Nome { get; set; }
    public string Matricula { get; private set; }

    public double PercentualComissao
    {
        get { return percentualComissao; }
        set { if (value >= 0) percentualComissao = value; }
    }

    public Vendedor(string nome)
    {
        Nome = nome;
        Matricula = nome + "10";
    }

    public void ExibirDados()
    {
        Console.WriteLine($"Vendedor: {Nome} | Matricula: {Matricula} | Comissão: {PercentualComissao}%");
    }

    public double CalcularComissao(double valorPedido)
    {
        return valorPedido * PercentualComissao / 100;
    }
}

class Produto
{
    private double preco;
    private int quantidade;

    public string Descricao { get; set; }

    public double PrecoUnitario
    {
        get { return preco; }
        set { if (value >= 0) preco = value; }
    }

    public int Quantidade
    {
        get { return quantidade; }
        set { if (value > 0) quantidade = value; }
    }

    public void ExibirDados()
    {
        Console.WriteLine($"Produto: {Descricao} | Preço: {PrecoUnitario} | Qtd: {Quantidade}");
    }

    public double CalcularSubtotal()
    {
        return PrecoUnitario * Quantidade;
    }
}

class Pagamento
{
    private int parcelas;

    public string FormaPagamento { get; set; }

    public int Parcelas
    {
        get { return parcelas; }
        set { if (value >= 1) parcelas = value; }
    }

    public void ExibirDados()
    {
        Console.WriteLine($"Pagamento: {FormaPagamento} | Parcelas: {Parcelas}");
    }

    public bool ValidarPagamento()
    {
        return Parcelas >= 1;
    }

    public double CalcularAcrescimo(double valorBase)
    {
        if (Parcelas > 1)
            return valorBase * 0.1; 
        return 0;
    }
}

class Entrega
{
    private double distancia;

    public string Endereco { get; set; }

    public double DistanciaKm
    {
        get { return distancia; }
        set { if (value >= 0) distancia = value; }
    }

    public string TipoEntrega { get; set; }

    public void ExibirDados()
    {
        Console.WriteLine($"Entrega: {Endereco} | Distância: {DistanciaKm}km | Tipo: {TipoEntrega}");
    }

    public double CalcularTaxaEntrega()
    {
        return DistanciaKm * 2; 
    }
}

class Pedido
{
    public int Numero { get; private set; }
    public Cliente Cliente { get; set; }
    public Vendedor Vendedor { get; set; }
    public Produto Produto { get; set; }
    public Pagamento Pagamento { get; set; }
    public Entrega Entrega { get; set; }

    public Pedido(int numero)
    {
        Numero = numero;
    }

    public double CalcularValorFinal()
    {
        double subtotal = Produto.CalcularSubtotal();
        double taxa = Entrega.CalcularTaxaEntrega();
        double acrescimo = Pagamento.CalcularAcrescimo(subtotal);

        return subtotal + taxa + acrescimo;
    }

    public double CalcularComissaoVendedor()
    {
        return Vendedor.CalcularComissao(CalcularValorFinal());
    }

    public void ExibirResumo()
    {
        Console.WriteLine("\n===== RESUMO DO PEDIDO =====");

        Cliente.ExibirDados();
        Vendedor.ExibirDados();
        Produto.ExibirDados();
        Pagamento.ExibirDados();
        Entrega.ExibirDados();

        double total = CalcularValorFinal();

        Console.WriteLine($"Total: {total}");
        Console.WriteLine($"Comissão Vendedor: {CalcularComissaoVendedor()}");
    }
}

class Program
{
    static void Main()
    {
        Cliente c = new Cliente { Nome = "João", Cpf = "123", Cidade = "Araxá" };

        Vendedor v = new Vendedor("Maria");
        v.PercentualComissao = 5;

        Produto p = new Produto { Descricao = "Notebook", PrecoUnitario = 2000, Quantidade = 1 };

        Pagamento pg = new Pagamento { FormaPagamento = "Cartão", Parcelas = 2 };

        Entrega e = new Entrega { Endereco = "Rua A", DistanciaKm = 10, TipoEntrega = "Normal" };

        Pedido pedido = new Pedido(1);
        pedido.Cliente = c;
        pedido.Vendedor = v;
        pedido.Produto = p;
        pedido.Pagamento = pg;
        pedido.Entrega = e;

        pedido.ExibirResumo();
    }
}

using System;

class Filme
{
    public string Nome;
    public string Genero;
    public int Duracao;
    public int Classificacao;

    public Filme(string nome, string genero, int duracao, int classificacao)
    {
        Nome = string.IsNullOrEmpty(nome) ? "Sem nome" : nome;
        Genero = string.IsNullOrEmpty(genero) ? "Não informado" : genero;
        Duracao = duracao <= 0 ? 1 : duracao;
        Classificacao = classificacao < 0 ? 0 : classificacao;
    }

    public void ExibirResumo()
    {
        Console.WriteLine($"Filme: {Nome} | Gênero: {Genero} | Duração: {Duracao} min | Classificação: {Classificacao}");
    }

    public bool EhPermitido(int idade)
    {
        return idade >= Classificacao;
    }

    public void AlterarDuracao(int novaDuracao)
    {
        if (novaDuracao > 0)
            Duracao = novaDuracao;
        else
            Console.WriteLine("Duração inválida!");
    }
}

class Program
{
    static void Main()
    {
        Filme f1 = new Filme("Interestelar", "Ficção", 169, 12);
        Filme f2 = new Filme("", "", -30, -5);

        f1.ExibirResumo();
        f2.ExibirResumo();

        Console.WriteLine(f1.EhPermitido(10));
        Console.WriteLine(f1.EhPermitido(15));

        f2.AlterarDuracao(120);
        f2.AlterarDuracao(-10);

        f2.ExibirResumo();
    }
}

using System;

public class ReservaHotel
{
    public string NomeHospede;
    public int NumeroQuarto;
    public int QuantidadeDiarias;
    public double ValorDiaria;
    public string Status;

    public ReservaHotel(string nomeHospede, int numeroQuarto)
    {
        NomeHospede = string.IsNullOrWhiteSpace(nomeHospede) ? "Hóspede não informado" : nomeHospede;
        NumeroQuarto = numeroQuarto <= 0 ? 1 : numeroQuarto;

        QuantidadeDiarias = 1;
        ValorDiaria = 50;
        Status = "Ativa";
    }

    public ReservaHotel(string nomeHospede, int numeroQuarto, int quantidadeDiarias, double valorDiaria)
    {
        NomeHospede = string.IsNullOrWhiteSpace(nomeHospede) ? "Hóspede não informado" : nomeHospede;
        NumeroQuarto = numeroQuarto <= 0 ? 1 : numeroQuarto;
        QuantidadeDiarias = quantidadeDiarias <= 0 ? 1 : quantidadeDiarias;
        ValorDiaria = valorDiaria <= 0 ? 50 : valorDiaria;

        Status = "Ativa";
    }

    public double CalcularTotal()
    {
        return QuantidadeDiarias * ValorDiaria;
    }

    public void ExibirReserva()
    {
        Console.WriteLine("----- RESERVA -----");
        Console.WriteLine($"Hóspede: {NomeHospede}");
        Console.WriteLine($"Quarto: {NumeroQuarto}");
        Console.WriteLine($"Diárias: {QuantidadeDiarias}");
        Console.WriteLine($"Valor da diária: R$ {ValorDiaria}");
        Console.WriteLine($"Status: {Status}");
        Console.WriteLine("-------------------\n");
    }

    public void AdicionarDiarias(int quantidade)
    {
        if (quantidade > 0)
        {
            QuantidadeDiarias += quantidade;
        }
    }

    public void CancelarReserva()
    {
        Status = "Cancelada";
    }

    public void ReativarReserva()
    {
        Status = "Ativa";
    }
}
using System;

class Program
{
    static void Main(string[] args)
    {
        ReservaHotel r1 = new ReservaHotel("Carlos", 12);
        ReservaHotel r2 = new ReservaHotel("", -8, 0, -300);

        r1.ExibirReserva();
        r2.ExibirReserva();

        Console.WriteLine("Total r1: R$ " + r1.CalcularTotal());
        Console.WriteLine("Total r2: R$ " + r2.CalcularTotal());
        Console.WriteLine();

        r1.AdicionarDiarias(2);
        Console.WriteLine("Após adicionar diárias em r1:");
        r1.ExibirReserva();

        r2.CancelarReserva();
        Console.WriteLine("Após cancelar r2:");
        r2.ExibirReserva();

        r2.ReativarReserva();
        Console.WriteLine("Após reativar r2:");
        r2.ExibirReserva();
    }
}
