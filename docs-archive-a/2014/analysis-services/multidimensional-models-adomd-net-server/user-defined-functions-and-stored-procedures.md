---
title: Funções definidas pelo usuário e procedimentos armazenados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- stored procedures [ADOMD.NET]
- ADOMD.NET, user defined functions
- user defined functions [ADOMD.NET]
- ADOMD.NET, UDFs
- ADOMD.NET, stored procedures
ms.assetid: 07e8aa47-37d4-4bbc-8bff-49e422d12897
author: minewiskan
ms.author: owend
ms.openlocfilehash: a49aa41d158bf2c9fd1ebb1a711d6ff35c0df98b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678337"
---
# <a name="user-defined-functions-and-stored-procedures"></a><span data-ttu-id="4f39c-102">Funções e procedimentos armazenados definidos pelo usuário</span><span class="sxs-lookup"><span data-stu-id="4f39c-102">User Defined Functions and Stored Procedures</span></span>
  <span data-ttu-id="4f39c-103">Com os objetos do ADOMD.NET Server, você pode criar uma UDF (função definida pelo usuário) ou procedimentos armazenados para [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que interajam com metadados e dados do servidor.</span><span class="sxs-lookup"><span data-stu-id="4f39c-103">With ADOMD.NET server objects, you can create user defined function (UDF) or stored procedures for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that interact with metadata and data from the server.</span></span> <span data-ttu-id="4f39c-104">Esses métodos em processo são chamados por meio de instruções MDX (Multidimensional Expressions), DMX (Data Mining Extensions) para fornecerem funcionalidade agregada sem as latências associadas às comunicações de rede.</span><span class="sxs-lookup"><span data-stu-id="4f39c-104">These in-process methods are called through Multidimensional Expressions (MDX) or Data Mining Extensions (DMX) statements to provide added functionality without the latencies associated with network communications.</span></span>  
  
## <a name="udf-examples"></a><span data-ttu-id="4f39c-105">Exemplos de UDF</span><span class="sxs-lookup"><span data-stu-id="4f39c-105">UDF Examples</span></span>  
 <span data-ttu-id="4f39c-106">Um UDF é um método que pode ser chamado no contexto de uma instrução MDX ou DMX, pode conter qualquer número de parâmetros e pode retornar qualquer tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="4f39c-106">A UDF is a method that can be called in the context of an MDX or DMX statement, can take any number of parameters, and can return any type of data.</span></span>  
  
 <span data-ttu-id="4f39c-107">Um UDF criado com MDX é semelhante a um criado para DMX.</span><span class="sxs-lookup"><span data-stu-id="4f39c-107">A UDF created using MDX is similar to one created for DMX.</span></span> <span data-ttu-id="4f39c-108">A principal diferença é que determinadas propriedades do objeto [Microsoft. AnalysisServices. AdomdServer. Context](/previous-versions/sql/sql-server-2014/ms143353(v=sql.120)) , como as propriedades [Microsoft. AnalysisServices. AdomdServer. Context. CURRENTCUBE \*](/previous-versions/sql/sql-server-2014/ms137081(v=sql.120)) e [Microsoft. AnalysisServices. AdomdServer. Context. CurrentMiningModel \*](/previous-versions/sql/sql-server-2014/ms137178(v=sql.120)) , estão disponíveis apenas para uma linguagem de script ou para a outra.</span><span class="sxs-lookup"><span data-stu-id="4f39c-108">The main difference is that certain properties of the [Microsoft.AnalysisServices.AdomdServer.Context](/previous-versions/sql/sql-server-2014/ms143353(v=sql.120)) object, such as the [Microsoft.AnalysisServices.AdomdServer.Context.CurrentCube\*](/previous-versions/sql/sql-server-2014/ms137081(v=sql.120)) and [Microsoft.AnalysisServices.AdomdServer.Context.CurrentMiningModel\*](/previous-versions/sql/sql-server-2014/ms137178(v=sql.120)) properties, are available only for one scripting language or the other.</span></span>  
  
 <span data-ttu-id="4f39c-109">Os exemplos a seguir mostram como usar um UDF para retornar uma descrição de nó, filtrar tuplas e aplicar um filtro a uma tupla.</span><span class="sxs-lookup"><span data-stu-id="4f39c-109">The following examples show how to use a UDF to return a node description, filter tuples, and apply a filter to a tuple.</span></span>  
  
### <a name="returning-a-node-description"></a><span data-ttu-id="4f39c-110">Retornando uma descrição de nó</span><span class="sxs-lookup"><span data-stu-id="4f39c-110">Returning a Node Description</span></span>  
 <span data-ttu-id="4f39c-111">O exemplo a seguir cria um UDF que retorna a descrição de um nó especificado.</span><span class="sxs-lookup"><span data-stu-id="4f39c-111">The following example creates a UDF that returns the node description for a specified node.</span></span> <span data-ttu-id="4f39c-112">O UDF usa o contexto atual em que está sendo executado e usa uma cláusula FROM do DMX para recuperar o nó do modelo de mineração atual.</span><span class="sxs-lookup"><span data-stu-id="4f39c-112">The UDF uses the current context in which it is being run, and uses a DMX FROM clause to retrieve the node from the current mining model.</span></span>  
  
```  
public string GetNodeDescription(string nodeUniqueName)  
{  
   return Context.CurrentMiningModel.GetNodeFromUniqueName(nodeUniqueName).Description;  
}  
```  
  
 <span data-ttu-id="4f39c-113">Uma vez implantado, o exemplo de UDF anterior pode ser chamado pela expressão DMX a seguir, que recupera o nó de previsão mais provável.</span><span class="sxs-lookup"><span data-stu-id="4f39c-113">Once deployed, the previous UDF example can be called by the following DMX expression, which retrieves the most-likely prediction node.</span></span> <span data-ttu-id="4f39c-114">A descrição contém informações que descrevem as condições que compõem o nó de previsão.</span><span class="sxs-lookup"><span data-stu-id="4f39c-114">The description contains information that describes the conditions that make up the prediction node.</span></span>  
  
```  
select Cluster(), SampleAssembly.GetNodeDescription( PredictNodeId(Cluster()) ) FROM [Customer Clusters]  
```  
  
### <a name="returning-tuples"></a><span data-ttu-id="4f39c-115">Retornando tuplas</span><span class="sxs-lookup"><span data-stu-id="4f39c-115">Returning Tuples</span></span>  
 <span data-ttu-id="4f39c-116">O exemplo a seguir obtém um conjunto e uma contagem de retorno e recupera tuplas do conjunto de forma aleatória, retornando um subconjunto final:</span><span class="sxs-lookup"><span data-stu-id="4f39c-116">The following example takes a set and a return count, and randomly retrieves tuples from the set, returning a final subset:</span></span>  
  
```  
public Set RandomSample(Set set, int returnCount)  
{  
   //Return the original set if there are fewer tuples  
   //in the set than the number requested.  
   if (set.Tuples.Count <= returnCount)  
      return set;  
  
   System.Random r = new System.Random();  
   SetBuilder returnSet = new SetBuilder();  
  
   //Retrieve random tuples until the return set is filled.  
   int i = set.Tuples.Count;  
   foreach (Tuple t in set.Tuples)  
   {  
      if (r.Next(i) < returnCount)  
      {  
         returnCount--;  
         returnSet.Add(t);  
      }  
      i--;  
      //Stop the loop if we have enough tuples.  
      if (returnCount == 0)  
         break;  
   }  
   return returnSet.ToSet();  
}  
```  
  
 <span data-ttu-id="4f39c-117">O exemplo anterior é chamado no exemplo de MDX a seguir.</span><span class="sxs-lookup"><span data-stu-id="4f39c-117">The previous example is called in the following MDX example.</span></span> <span data-ttu-id="4f39c-118">Neste exemplo de MDX, cinco Estados aleatórios ou províncias são recuperados do banco de dados **Adventure Works** .</span><span class="sxs-lookup"><span data-stu-id="4f39c-118">In this MDX example, five random states or provinces are retrieved from the **Adventure Works** database.</span></span>  
  
```  
SELECT SampleAssembly.RandomSample([Geography].[State-Province].Members, 5) on ROWS,   
[Date].[Calendar].[Calendar Year] on COLUMNS  
FROM [Adventure Works]  
WHERE [Measures].[Reseller Freight Cost]  
```  
  
### <a name="applying-a-filter-to-a-tuple"></a><span data-ttu-id="4f39c-119">Aplicando um filtro a uma tupla</span><span class="sxs-lookup"><span data-stu-id="4f39c-119">Applying a Filter to a Tuple</span></span>  
 <span data-ttu-id="4f39c-120">No exemplo a seguir, um UDF é definido para obter um conjunto, e aplicar um filtro a cada tupla no conjunto, usando o objeto Expression.</span><span class="sxs-lookup"><span data-stu-id="4f39c-120">In the following example, a UDF is defined that takes a set, and applies a filter to each tuple in the set, using the Expression object.</span></span> <span data-ttu-id="4f39c-121">Qualquer tupla compatível com o filtro será adicionada a um conjunto retornado.</span><span class="sxs-lookup"><span data-stu-id="4f39c-121">Any tuples that conform to the filter will be added to a set that is returned.</span></span>  
  
 [!code-csharp[Adomd.NetServer#FilterSet](../../snippets/csharp/SQL14/adomd.net/adomd.netserver/cs/class1.cs#filterset)]  
  
 <span data-ttu-id="4f39c-122">O exemplo anterior é chamado no exemplo de MDX a seguir, que filtra o conjunto para cidades com nomes começando com 'A'.</span><span class="sxs-lookup"><span data-stu-id="4f39c-122">The previous example is called in the following MDX example, which filters the set to cities with names beginning with 'A'.</span></span>  
  
```  
Select Measures.Members on Rows,  
SampleAssembly.FilterSet([Customer].[Customer Geography].[City], "[Customer].[Customer Geography].[City].CurrentMember.Name < 'B'") on Columns  
From [Adventure Works]  
```  
  
## <a name="stored-procedure-example"></a><span data-ttu-id="4f39c-123">Exemplo de procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="4f39c-123">Stored Procedure Example</span></span>  
 <span data-ttu-id="4f39c-124">No exemplo a seguir, um procedimento armazenado baseado em MDX usa AMO para criar partições, se necessário, para Vendas na Internet.</span><span class="sxs-lookup"><span data-stu-id="4f39c-124">In the following example, an MDX-based stored procedure uses AMO to create partitions, if needed, for Internet Sales.</span></span>  
  
 [!code-csharp[Adomd.NetServer#CreateInternetSalesMeasureGroupPartitions](../../snippets/csharp/SQL14/adomd.net/adomd.netserver/cs/class1.cs#createinternetsalesmeasuregrouppartitions)]  
  
  
