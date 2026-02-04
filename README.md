## Processador de Documentos
# - Este projeto tem como objetivo demonstrar, de forma prática, a utilização de polimorfismo e sobrescrita de métodos na Programação Orientada a Objetos (POO), por meio da implementação de um sistema de processamento de documentos.

# - A aplicação simula diferentes tipos de documentos (Texto, HTML e PDF), permitindo que todos sejam tratados de maneira uniforme por meio de uma classe base comum.

## Estrutura do Projeto
# O sistema é composto pelos seguintes elementos:

Classe base: Documento

## Responsável por definir as propriedades e comportamentos comuns a todos os tipos de documentos:

Propriedades:
-  Título
-  Autor
-  Data de criação

Métodos virtuais:
- Imprimir()
- ConteudoFormatado()

## Classes derivadas
# - Cada tipo de documento herda da classe Documento e implementa comportamentos específicos:

DocumentoTexto
- Sobrescreve os métodos da classe base
- Método específico: ContarPalavras()

DocumentoHTML
- Sobrescreve os métodos da classe base
- Método específico: AdicionarEstilo()

DocumentoPDF
- Sobrescreve os métodos da classe base
- Método específico: AdicionarMarcaDagua()

Classe ProcessadorDocumentos
- Responsável por percorrer uma coleção de documentos e invocar o método Imprimir() de forma polimórfica, permitindo que objetos de diferentes tipos sejam tratados de maneira uniforme.

Funcionalidades
- Impressão personalizada conforme o tipo de documento
- Processamento de uma coleção heterogênea de documentos
- Implementação de métodos específicos em cada classe derivada

Uso de Polimorfismo
O método Imprimir() é chamado a partir de uma referência do tipo Documento, sendo executado de acordo com o tipo concreto do objeto (Texto, HTML ou PDF).

Benefícios do uso de polimorfismo:
- Redução de duplicação de código
- Maior flexibilidade e extensibilidade
- Facilidade para inclusão de novos tipos de documentos

## Exemplo de Uso
```
List<Documento> documentos = new List<Documento>
{
    new DocumentoTexto("Relatório", "Ana", DateTime.Now),
    new DocumentoHTML("Página Web", "Carlos", DateTime.Now),
    new DocumentoPDF("Contrato", "Beatriz", DateTime.Now)
};

ProcessadorDocumentos processador = new ProcessadorDocumentos();
processador.Processar(documentos);
```
