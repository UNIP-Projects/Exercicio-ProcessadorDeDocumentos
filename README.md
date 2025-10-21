# 📄 Processador de Documentos

## 🧠 Objetivo

Este projeto tem como objetivo demonstrar o uso de **polimorfismo** e **sobrescrita de métodos** na programação orientada a objetos por meio da criação de um sistema de processamento de documentos.

## 🏗️ Estrutura do Projeto

O sistema é composto por:

### 🔹 Classe base: `Documento`
Contém propriedades comuns a todos os documentos:
- `Título`
- `Autor`
- `Data de criação`

E métodos virtuais:
- `Imprimir()`
- `ConteudoFormatado()`

### 🔸 Classes derivadas

Cada tipo de documento implementa um comportamento específico:

- **`DocumentoTexto`**
  - Sobrescreve os métodos da classe base
  - Método específico: `ContarPalavras()`

- **`DocumentoHTML`**
  - Sobrescreve os métodos da classe base
  - Método específico: `AdicionarEstilo()`

- **`DocumentoPDF`**
  - Sobrescreve os métodos da classe base
  - Método específico: `AdicionarMarcaDagua()`

### ⚙️ Classe `ProcessadorDocumentos`

Responsável por processar uma lista de documentos e chamar o método `Imprimir()` de forma polimórfica, permitindo que documentos de diferentes tipos sejam tratados uniformemente.

## ✅ Funcionalidades

- Impressão personalizada de cada tipo de documento
- Processamento de uma coleção de documentos variados
- Métodos adicionais específicos em cada subtipo

## 💡 Uso de Polimorfismo

O método `Imprimir()` é chamado genericamente em uma lista de objetos do tipo `Documento`, sendo executado de forma diferente conforme o tipo real do objeto (Texto, HTML, PDF).

**Vantagens:**
- Redução de duplicação de código
- Código mais flexível e extensível
- Facilidade para adicionar novos tipos de documentos no futuro

## 🧪 Exemplo de Uso

```csharp
List<Documento> documentos = new List<Documento>
{
    new DocumentoTexto("Relatório", "Ana", DateTime.Now),
    new DocumentoHTML("Página Web", "Carlos", DateTime.Now),
    new DocumentoPDF("Contrato", "Beatriz", DateTime.Now)
};

ProcessadorDocumentos processador = new ProcessadorDocumentos();
processador.Processar(documentos);
