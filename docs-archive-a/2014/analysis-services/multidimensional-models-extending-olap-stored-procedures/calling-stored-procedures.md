---
title: Chamando procedimentos armazenados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- calling stored procedures
- stored procedures [Analysis Services], calling
- MDX queries [Analysis Services]
- CALL statement
ms.assetid: 96a9660d-875b-4ee4-b339-90020b1d9895
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5c9da6edef576a6ab25c183cbc87ff95cc056845
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680700"
---
# <a name="calling-stored-procedures"></a><span data-ttu-id="1b4c5-102">Chamando procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="1b4c5-102">Calling Stored Procedures</span></span>
  <span data-ttu-id="1b4c5-103">Procedimentos armazenados podem ser chamados no servidor ou a partir de um aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-103">Stored procedures can be called on the server or from client application.</span></span> <span data-ttu-id="1b4c5-104">Nos dois casos, os procedimentos armazenados são sempre executados no servidor, no contexto do servidor ou de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-104">In either case, stored procedures always run on the server, either the context of the server or of a database.</span></span> <span data-ttu-id="1b4c5-105">Não há permissões especiais necessárias para executar um procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-105">There are no special permissions required to execute a stored procedure.</span></span> <span data-ttu-id="1b4c5-106">Uma vez adicionado o procedimento armazenado por um assembly ao contexto do servidor ou do banco de dados, qualquer usuário pode executá-lo desde que a função do usuário permita as ações realizadas pelo procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-106">Once a stored procedure is added by an assembly to the server or database context, any user can execute the stored procedure as long as the role for the user permits the actions performed by the stored procedure.</span></span>  
  
 <span data-ttu-id="1b4c5-107">O procedimento armazenado em formato MDX é chamado da mesma forma que se chama uma função MDX intrínseca.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-107">Calling a stored procedure in MDX is done in the same manner as calling an intrinsic MDX function.</span></span> <span data-ttu-id="1b4c5-108">No caso de um procedimento armazenado sem-parâmetros, o nome do procedimento e um par de parênteses vazios são usados, como mostrado a seguir:</span><span class="sxs-lookup"><span data-stu-id="1b4c5-108">For a stored procedure that takes no parameters, the name of the procedure and an empty pair of parentheses are used, as shown here:</span></span>  
  
```  
MyStoredProcedure()  
```  
  
 <span data-ttu-id="1b4c5-109">Se o procedimento armazenado tiver um ou mais parâmetros, eles são fornecidos, em ordem, separados por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-109">If the stored procedure takes one or more parameters, then the parameters are supplied, in order, separated by commas.</span></span> <span data-ttu-id="1b4c5-110">Este é um exemplo de procedimento armazenado com três parâmetros:</span><span class="sxs-lookup"><span data-stu-id="1b4c5-110">The following example demonstrates a sample stored procedure with three parameters:</span></span>  
  
```  
MyStoredProcedure("Parameter1", 2, 800)  
```  
  
## <a name="calling-stored-procedures-in-mdx-queries"></a><span data-ttu-id="1b4c5-111">Chamando procedimentos armazenados em consultas MDX</span><span class="sxs-lookup"><span data-stu-id="1b4c5-111">Calling Stored Procedures in MDX Queries</span></span>  
 <span data-ttu-id="1b4c5-112">Em todas as consultas MDX, o procedimento armazenado deve retornar o tipo sintaticamente correto exigido por uma expressão MDX.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-112">In all MDX queries, the stored procedure must return the syntactically correct type required by an MDX expression.</span></span> <span data-ttu-id="1b4c5-113">Se um procedimento armazenado não retornar o tipo correto, ocorrerá um erro da linguagem MDX.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-113">If a stored procedure does not return the correct type, an MDX error occurs.</span></span> <span data-ttu-id="1b4c5-114">Os exemplos a seguir demonstram procedimentos armazenados que retornam um conjunto, um membro e o resultado de uma operação matemática.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-114">The following examples demonstrate stored procedures that return a set, a member, and the result of a mathematical operation.</span></span>  
  
### <a name="returning-a-set"></a><span data-ttu-id="1b4c5-115">Retornando um conjunto</span><span class="sxs-lookup"><span data-stu-id="1b4c5-115">Returning a Set</span></span>  
 <span data-ttu-id="1b4c5-116">Os exemplos a seguir implementam um procedimento armazenado, chamado MySproc, que retorna um conjunto.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-116">The following examples implement a stored procedure, called MySproc, that returns a set.</span></span> <span data-ttu-id="1b4c5-117">No primeiro exemplo, MySproc retorna o conjunto diretamente na expressão SELECT.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-117">In the first example, MySproc returns the set directly in the SELECT expression.</span></span> <span data-ttu-id="1b4c5-118">Nos dois segundos exemplos, MySproc retorna o conjunto como um argumento para as funções Crossjoin e DrilldownLevel.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-118">In the second two examples, MySproc returns the set as an argument for the Crossjoin and DrilldownLevel functions.</span></span>  
  
```  
SELECT MySetProcedure(a,b,c) ON 0 FROM Sales  
SELECT Crossjoin(MySetProcedure(a,b,c)) ON 0 FROM Sales  
SELECT DrilldownLevel(MySetProcedure(a,b,c)) ON 0 FROM Sales  
```  
  
### <a name="returning-a-member"></a><span data-ttu-id="1b4c5-119">Retornando um membro</span><span class="sxs-lookup"><span data-stu-id="1b4c5-119">Returning a Member</span></span>  
 <span data-ttu-id="1b4c5-120">O exemplo a seguir mostra uma função MySproc que retorna um membro:</span><span class="sxs-lookup"><span data-stu-id="1b4c5-120">The following example shows a function MySproc function that returns a member:</span></span>  
  
```  
SELECT Descendants(MySproc(a,b,c),3) ON 0 FROM Sales  
```  
  
### <a name="returning-the-result-of-a-math-operation"></a><span data-ttu-id="1b4c5-121">Retornando o resultado de uma operação matemática</span><span class="sxs-lookup"><span data-stu-id="1b4c5-121">Returning the Result of a Math Operation</span></span>  
  
```  
SELECT Country.Members on 0, MySproc(Measures.Sales) ON 1 FROM Sales  
```  
  
## <a name="calling-stored-procedures-with-the-call-statement"></a><span data-ttu-id="1b4c5-122">Chamando procedimentos armazenados com a instrução Call</span><span class="sxs-lookup"><span data-stu-id="1b4c5-122">Calling Stored Procedures with the Call Statement</span></span>  
 <span data-ttu-id="1b4c5-123">É possível chamar procedimentos armazenados fora do contexto de uma consulta MDX usando a instrução MDX `Call`.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-123">Stored procedures can be called outside of the context of an MDX query using the MDX `Call` statement.</span></span>  
  
 <span data-ttu-id="1b4c5-124">Use esse método para instanciar os efeitos colaterais de uma consulta armazenada ou para o aplicativo obter os resultados de uma consulta armazenada.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-124">You can use this method to either instantiate the side effects of a stored query or for the application to get the results of a stored query.</span></span> <span data-ttu-id="1b4c5-125">Um uso comum da instrução `Call` seria para usar o Analysis Management Objects (AMO) para executar funções administrativas que não têm um resultado retornado.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-125">A common use of the `Call` statement would be to use Analysis Management Objects (AMO) to perform administrative functions that do not have a return result.</span></span> <span data-ttu-id="1b4c5-126">Por exemplo, o comando a seguir chama um procedimento armazenado:</span><span class="sxs-lookup"><span data-stu-id="1b4c5-126">For example, the following command calls a stored procedure:</span></span>  
  
```  
Call MyStoredProcedure(a,b,c)  
```  
  
 <span data-ttu-id="1b4c5-127">O único tipo com suporte retornado a partir de um procedimento armazenado em uma instrução `Call` é um conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-127">The only supported type returned from stored procedure in a `Call` statement is a rowset.</span></span> <span data-ttu-id="1b4c5-128">A serialização de um conjunto de linhas é definido pelo XML for Analysis.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-128">The serialization for a rowset is defined by XML for Analysis.</span></span> <span data-ttu-id="1b4c5-129">Se um procedimento armazenado em uma instrução `Call` retornar qualquer outro tipo, ele será ignorado e não será retornado em XML para o aplicativo que o chamou.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-129">If a stored procedure in a `Call` statement returns any other type, it is ignored and not returned in XML to the calling application.</span></span> <span data-ttu-id="1b4c5-130">Para obter mais informações sobre conjuntos de linhas do XML for Analysis, consulte Conjuntos de linhas de esquema do XML for Analysis.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-130">For more information about XML for Analysis rowsets, see, XML for Analysis Schema Rowsets.</span></span>  
  
 <span data-ttu-id="1b4c5-131">Se o procedimento armazenado retornar um conjunto de linhas do .NET, o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] converterá o resultado no servidor em um conjunto de linhas do XML for Analysis.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-131">If a stored procedure returns a .NET rowset, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] converts the result on the server to an XML for Analysis rowset.</span></span> <span data-ttu-id="1b4c5-132">O conjunto de linhas do XML for Analysis é sempre retornado por um procedimento armazenado na função `Call`.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-132">The XML for Analysis rowset is always returned by a stored procedure in the `Call` function.</span></span> <span data-ttu-id="1b4c5-133">Se um conjunto de dados contiver recursos que não possam ser expressos no conjunto de linhas do XML for Analysis, ocorrerá uma falha.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-133">If a dataset contains features that cannot be expressed in the XML for Analysis rowset, a failure results.</span></span>  
  
 <span data-ttu-id="1b4c5-134">Também podem ser empregados procedimentos que retornam valores nulos (por exemplo, sub-rotinas em Visual Basic) com a palavra-chave CALL.</span><span class="sxs-lookup"><span data-stu-id="1b4c5-134">Procedures that return void values (for example, subroutines in Visual Basic) can also be employed with the CALL keyword.</span></span> <span data-ttu-id="1b4c5-135">Se, por exemplo, você quiser usar a função MyVoidFunction() em uma instrução MDX, a seguinte sintaxe será empregada:</span><span class="sxs-lookup"><span data-stu-id="1b4c5-135">If, for example, you wanted to use the function MyVoidFunction() in an MDX statement, the following syntax would be employed:</span></span>  
  
```  
CALL(MyVoidFunction)  
```  
  
## <a name="see-also"></a><span data-ttu-id="1b4c5-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1b4c5-136">See Also</span></span>  
 <span data-ttu-id="1b4c5-137">[Gerenciamento de assemblies de modelo multidimensional](../multidimensional-models/multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="1b4c5-137">[Multidimensional Model Assemblies Management](../multidimensional-models/multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="1b4c5-138">Definindo procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="1b4c5-138">Defining Stored Procedures</span></span>](../multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)  
  
  
