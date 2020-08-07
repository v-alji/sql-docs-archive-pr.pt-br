---
title: Criando, alterando e removendo regras | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- rules [SMO]
ms.assetid: 16981459-524e-4b39-a899-4370eaf763cc
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7742a9cb718bdde4f268d5226c45eba475f44ddd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576260"
---
# <a name="creating-altering-and-removing-rules"></a><span data-ttu-id="b0e23-102">Criando, alterando e removendo regras</span><span class="sxs-lookup"><span data-stu-id="b0e23-102">Creating, Altering, and Removing Rules</span></span>
  <span data-ttu-id="b0e23-103">No SMO, as regras são representadas pelo objeto <xref:Microsoft.SqlServer.Management.Smo.Rule>.</span><span class="sxs-lookup"><span data-stu-id="b0e23-103">In SMO, rules are represented by the <xref:Microsoft.SqlServer.Management.Smo.Rule> object.</span></span> <span data-ttu-id="b0e23-104">A regra é definida pela propriedade <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A> que é uma cadeia de caracteres de texto que contém uma expressão de condição que usa operadores ou predicados, como IN, LIKE ou BETWEEN.</span><span class="sxs-lookup"><span data-stu-id="b0e23-104">The rule is defined by the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A> property, which is a text string that contains a condition expression that uses operators or predicates, such as IN, LIKE, or BETWEEN.</span></span> <span data-ttu-id="b0e23-105">Uma regra não pode fazer referência a colunas ou a outros objetos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b0e23-105">A rule cannot reference columns or other database objects.</span></span> <span data-ttu-id="b0e23-106">É possível incluir funções internas que não fazem referência a objetos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b0e23-106">Built-in functions that do not reference database objects can be included.</span></span>  
  
 <span data-ttu-id="b0e23-107">A definição na propriedade <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A> deve conter uma variável relativa ao valor de dados digitados.</span><span class="sxs-lookup"><span data-stu-id="b0e23-107">The definition in the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A> property must contain a variable that refers to the data value entered.</span></span> <span data-ttu-id="b0e23-108">Qualquer nome ou símbolo pode ser usado para representar o valor ao criar a regra, mas o primeiro caractere deve ser o \@ símbolo.</span><span class="sxs-lookup"><span data-stu-id="b0e23-108">Any name or symbol can be used to represent the value when creating the rule, but the first character must be the \@ symbol.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0e23-109">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b0e23-109">Example</span></span>  
 <span data-ttu-id="b0e23-110">Para usar qualquer exemplo de código fornecido, será necessário escolher o ambiente de programação, o modelo de programação e a linguagem de programação para criar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b0e23-110">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="b0e23-111">Para obter mais informações, consulte [criar um projeto Visual Basic Smo no Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) ou [criar um projeto do Visual C&#35; Smo no Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="b0e23-111">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-altering-and-removing-a-rule-in-visual-basic"></a><span data-ttu-id="b0e23-112">Criando, alterando e removendo uma regra no Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b0e23-112">Creating, Altering, and Removing a Rule in Visual Basic</span></span>  
 <span data-ttu-id="b0e23-113">Este exemplo de código mostra como criar uma regra, anexá-la a uma coluna, modificar propriedades do objeto <xref:Microsoft.SqlServer.Management.Smo.Rule>, desanexá-la da coluna e, em seguida, descartá-la.</span><span class="sxs-lookup"><span data-stu-id="b0e23-113">This code sample shows how to create a rule, attach it to a column, modify properties of the <xref:Microsoft.SqlServer.Management.Smo.Rule> object, detach it from the column, and then drop it.</span></span>  
  
 <span data-ttu-id="b0e23-114">A instrução `Dim` do objeto <xref:Microsoft.SqlServer.Management.Smo.Rule> é especificada com o caminho completo do assembly para evitar ambiguidades com um objeto <xref:Microsoft.SqlServer.Management.Smo.Rule> no assembly System.Data.</span><span class="sxs-lookup"><span data-stu-id="b0e23-114">The `Dim` statement for the <xref:Microsoft.SqlServer.Management.Smo.Rule> object is specified with the full assembly path to avoid ambiguity with a <xref:Microsoft.SqlServer.Management.Smo.Rule> object in the System.Data assembly.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBRules1](SMO How to#SMO_VBRules1)]  -->  
  
## <a name="creating-altering-and-removing-a-rule-in-visual-c"></a><span data-ttu-id="b0e23-115">Criando, alterando e removendo uma regra no Visual C#</span><span class="sxs-lookup"><span data-stu-id="b0e23-115">Creating, Altering, and Removing a Rule in Visual C#</span></span>  
 <span data-ttu-id="b0e23-116">Este exemplo de código mostra como criar uma regra, anexá-la a uma coluna, modificar propriedades do objeto <xref:Microsoft.SqlServer.Management.Smo.Rule>, desanexá-la da coluna e, em seguida, descartá-la.</span><span class="sxs-lookup"><span data-stu-id="b0e23-116">This code sample shows how to create a rule, attach it to a column, modify properties of the <xref:Microsoft.SqlServer.Management.Smo.Rule> object, detach it from the column, and then drop it.</span></span>  
  
 <span data-ttu-id="b0e23-117">A instrução `Dim` do objeto <xref:Microsoft.SqlServer.Management.Smo.Rule> é especificada com o caminho completo do assembly para evitar ambiguidades com um objeto <xref:Microsoft.SqlServer.Management.Smo.Rule> no assembly System.Data.</span><span class="sxs-lookup"><span data-stu-id="b0e23-117">The `Dim` statement for the <xref:Microsoft.SqlServer.Management.Smo.Rule> object is specified with the full assembly path to avoid ambiguity with a <xref:Microsoft.SqlServer.Management.Smo.Rule> object in the System.Data assembly.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
            Server srv;  
            srv = new Server();  
            //Reference the AdventureWorks2012 database.   
            Database db;  
            db = srv.Databases["AdventureWorks2012"];  
  
            //Define a Rule object variable by supplying the parent database, name and schema in the constructor.   
            //Note that the full namespace must be given for the Rule type to differentiate it from other Rule types.   
            Microsoft.SqlServer.Management.Smo.Rule ru;  
            ru = new Rule(db, "TestRule", "Production");  
            //Set the TextHeader and TextBody properties to define the rule.   
            ru.TextHeader = "CREATE RULE [Production].[TestRule] AS";  
            ru.TextBody = "@value BETWEEN GETDATE() AND DATEADD(year,4,GETDATE())";  
            //Create the rule on the instance of SQL Server.   
            ru.Create();  
            //Bind the rule to a column in the Product table by supplying the table, schema, and   
            //column as arguments in the BindToColumn method.   
            ru.BindToColumn("Product", "SellEndDate", "Production");  
            //Unbind from the column before removing the rule from the database.   
            ru.UnbindFromColumn("Product", "SellEndDate", "Production");  
            ru.Drop();  
  
        }  
```  
  
## <a name="creating-altering-and-removing-a-rule-in-powershell"></a><span data-ttu-id="b0e23-118">Criando, alterando e removendo uma regra no PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0e23-118">Creating, Altering, and Removing a Rule in PowerShell</span></span>  
 <span data-ttu-id="b0e23-119">Este exemplo de código mostra como criar uma regra, anexá-la a uma coluna, modificar propriedades do objeto <xref:Microsoft.SqlServer.Management.Smo.Rule>, desanexá-la da coluna e, em seguida, descartá-la.</span><span class="sxs-lookup"><span data-stu-id="b0e23-119">This code sample shows how to create a rule, attach it to a column, modify properties of the <xref:Microsoft.SqlServer.Management.Smo.Rule> object, detach it from the column, and then drop it.</span></span>  
  
 <span data-ttu-id="b0e23-120">A instrução `Dim` do objeto <xref:Microsoft.SqlServer.Management.Smo.Rule> é especificada com o caminho completo do assembly para evitar ambiguidades com um objeto <xref:Microsoft.SqlServer.Management.Smo.Rule> no assembly System.Data.</span><span class="sxs-lookup"><span data-stu-id="b0e23-120">The `Dim` statement for the <xref:Microsoft.SqlServer.Management.Smo.Rule> object is specified with the full assembly path to avoid ambiguity with a <xref:Microsoft.SqlServer.Management.Smo.Rule> object in the System.Data assembly.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server and get a reference to AdventureWorks2012  
CD \sql\localhost\default\databases  
$db = Get-Item Adventureworks2012  
  
# Define a Rule object variable by supplying the parent database, name and schema in the constructor.
$ru = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Rule -argumentlist $db, "TestRule", "Production"  
  
#Set the TextHeader and TextBody properties to define the rule.
$ru.TextHeader = "CREATE RULE [Production].[TestRule] AS"  
$ru.TextBody = "@value BETWEEN GETDATE() AND DATEADD(year,4,GETDATE())"  
  
#Create the rule on the instance of SQL Server.
$ru.Create()  
  
# Bind the rule to a column in the Product table by supplying the table, schema, and column as arguments in the BindToColumn method.
$ru.BindToColumn("Product", "SellEndDate", "Production")  
  
#Unbind from the column before removing the rule from the database.
$ru.UnbindFromColumn("Product", "SellEndDate", "Production")  
$ru.Drop()  
```  
  
## <a name="see-also"></a><span data-ttu-id="b0e23-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b0e23-121">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Rule>  
