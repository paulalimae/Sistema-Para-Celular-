# Sistema-Para-Celular-
using System;

// Classe abstrata para representar um celular genérico
public abstract class Celular
{
    public string Marca { get; set; }
    public string Modelo { get; set; }

    // Método abstrato para fazer chamadas
    public abstract void FazerChamada(string numero);

    // Método abstrato para enviar mensagens
    public abstract void EnviarMensagem(string numero, string mensagem);
}

// Classe que representa um celular Android
public class CelularAndroid : Celular
{
    public string SistemaOperacional { get; set; }

    public override void FazerChamada(string numero)
    {
        Console.WriteLine($"Chamando {numero} via Android...");
    }

    public override void EnviarMensagem(string numero, string mensagem)
    {
        Console.WriteLine($"Enviando mensagem para {numero} via Android: {mensagem}");
    }
}

// Classe que representa um celular iOS
public class CelularIOS : Celular
{
    public string VersaoIOS { get; set; }

    public override void FazerChamada(string numero)
    {
        Console.WriteLine($"Chamando {numero} via iOS...");
    }

    public override void EnviarMensagem(string numero, string mensagem)
    {
        Console.WriteLine($"Enviando mensagem para {numero} via iOS: {mensagem}");
    }
}

// Classe principal do programa
class Program
{
    static void Main(string[] args)
    {
        // Exemplo de uso dos celulares

        // Criando e utilizando um celular Android
        CelularAndroid android = new CelularAndroid()
        {
            Marca = "Samsung",
            Modelo = "Galaxy S20",
            SistemaOperacional = "Android 11"
        };

        android.FazerChamada("123456789");
        android.EnviarMensagem("987654321", "Olá, tudo bem?");

        // Criando e utilizando um celular iOS
        CelularIOS ios = new CelularIOS()
        {
            Marca = "Apple",
            Modelo = "iPhone 12",
            VersaoIOS = "iOS 14"
        };

        ios.FazerChamada("123456789");
        ios.EnviarMensagem("987654321", "Oi, como vai?");
    }
}
