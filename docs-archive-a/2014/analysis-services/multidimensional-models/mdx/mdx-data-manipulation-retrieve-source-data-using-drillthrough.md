---
title: Usando o DETALHAmento para recuperar dados de origem (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- DRILLTHROUGH statement
- retrieving data
- queries [MDX], DRILLTHROUGH statement
- data retrieval [MDX]
ms.assetid: fe0ab170-25a9-45a8-a377-f71a67f77018
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5601a3ddfa7075ed53330e12c260af88648db990
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574360"
---
# <a name="using-drillthrough-to-retrieve-source-data-mdx"></a><span data-ttu-id="c79e2-102">Usando DRILLTHROUGH para recuperar a fonte de dados (MDX)</span><span class="sxs-lookup"><span data-stu-id="c79e2-102">Using DRILLTHROUGH to Retrieve Source Data (MDX)</span></span>
  <span data-ttu-id="c79e2-103">As expressões multidimensionais (MDX) usam a instrução [DRILLTHROUGH](/sql/mdx/mdx-data-manipulation-drillthrough)para recuperar um conjunto de linhas dos dados de origem de uma célula de cubo.</span><span class="sxs-lookup"><span data-stu-id="c79e2-103">Multidimensional Expressions (MDX) uses the [DRILLTHROUGH](/sql/mdx/mdx-data-manipulation-drillthrough)statement to retrieve a rowset from the source data for a cube cell.</span></span>  
  
 <span data-ttu-id="c79e2-104">Para executar uma instrução `DRILLTHROUGH` em um cubo, uma ação de detalhamento deve ser definida para esse cubo.</span><span class="sxs-lookup"><span data-stu-id="c79e2-104">In order to run a `DRILLTHROUGH` statement on a cube, a drillthrough action must be defined for that cube.</span></span> <span data-ttu-id="c79e2-105">Para definir a ação de drillthrough, no [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], no Designer de Cubo, no painel **Ações** , na barra de ferramentas, clique em **Nova Ação de Drillthrough**.</span><span class="sxs-lookup"><span data-stu-id="c79e2-105">To define a drillthrough action, in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], in Cube Designer, on the **Actions** pane, on the toolbar, click **New Drillthrough Action**.</span></span> <span data-ttu-id="c79e2-106">Na nova ação de detalhamento, especifique o nome da ação, o destino, a condição e as colunas que serão retornadas pela instrução `DRILLTHROUGH`.</span><span class="sxs-lookup"><span data-stu-id="c79e2-106">In the new drillthrough action, specify the action name, target, condition, and the columns that are returned by a `DRILLTHROUGH` statement.</span></span>  
  
## <a name="drillthrough-statement-syntax"></a><span data-ttu-id="c79e2-107">Sintaxe da instrução DRILLTHROUGH</span><span class="sxs-lookup"><span data-stu-id="c79e2-107">DRILLTHROUGH Statement Syntax</span></span>  
 <span data-ttu-id="c79e2-108">A instrução `DRILLTHROUGH` utiliza esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c79e2-108">The `DRILLTHROUGH` statement uses the following syntax:</span></span>  
  
```  
<drillthrough> ::= DRILLTHROUGH [<Max_Rows>] [<First_Rowset>] <MDX select> [<Return_Columns>]  
   < Max_Rows> ::= MAXROWS <positive number>  
   <First_Rowset> ::= FIRSTROWSET <positive number>  
   <Return_Columns> ::= RETURN <member or attribute> [, <member or attribute>]  
```  
  
 <span data-ttu-id="c79e2-109">A cláusula `SELECT` identifica a célula de cubo que contém os dados de origem que serão recuperados.</span><span class="sxs-lookup"><span data-stu-id="c79e2-109">The `SELECT` clause identifies the cube cell that contains the source data to be retrieved.</span></span> <span data-ttu-id="c79e2-110">Essa cláusula `SELECT` é igual a uma instrução MDX `SELECT` comum, com exceção de que, na cláusula `SELECT`, apenas um membro pode ser especificado em cada eixo.</span><span class="sxs-lookup"><span data-stu-id="c79e2-110">This `SELECT` clause is the same to an ordinary MDX `SELECT` statement, except that in the `SELECT` clause only one member can be specified on each axis.</span></span> <span data-ttu-id="c79e2-111">Se mais de um membro for especificado em um eixo, ocorrerá um erro.</span><span class="sxs-lookup"><span data-stu-id="c79e2-111">If more than one member is specified on an axis, an error occurs.</span></span>  
  
 <span data-ttu-id="c79e2-112">A sintaxe de `<Max_Rows>` especifica o número de máximo de linhas em cada conjunto de linhas retornado.</span><span class="sxs-lookup"><span data-stu-id="c79e2-112">The `<Max_Rows>` syntax specifies the maximum number of the rows in each returned rowset.</span></span> <span data-ttu-id="c79e2-113">Se o provedor OLE DB usado para estabelecer a conexão com a fonte de dados não oferecer suporte a `DBPROP_MAXROWS`, a configuração `<Max_Rows>` será ignorada.</span><span class="sxs-lookup"><span data-stu-id="c79e2-113">If the OLE DB provider that is used to connect to the data source does not support `DBPROP_MAXROWS`, the `<Max_Rows>` setting is ignored.</span></span>  
  
 <span data-ttu-id="c79e2-114">A sintaxe de `<First_Rowset>` identifica a partição cujo conjunto de linhas será retornado primeiro.</span><span class="sxs-lookup"><span data-stu-id="c79e2-114">The `<First_Rowset>` syntax identifies the partition whose rowset is returned first.</span></span>  
  
 <span data-ttu-id="c79e2-115">A sintaxe de `<Return_Columns>` identifica as colunas do banco de dados subjacente que serão retornadas.</span><span class="sxs-lookup"><span data-stu-id="c79e2-115">The `<Return_Columns>` syntax identifies the underlying database columns to be returned.</span></span>  
  
## <a name="drillthrough-statement-example"></a><span data-ttu-id="c79e2-116">Exemplo da instrução DRILLTHROUGH</span><span class="sxs-lookup"><span data-stu-id="c79e2-116">DRILLTHROUGH Statement Example</span></span>  
 <span data-ttu-id="c79e2-117">O exemplo a seguir demonstra o uso da instrução `DRILLTHROUGH`.</span><span class="sxs-lookup"><span data-stu-id="c79e2-117">The following example demonstrates the use of the `DRILLTHROUGH` statement.</span></span> <span data-ttu-id="c79e2-118">Nesse exemplo, a instrução DRILLTHROUGH consulta as folhas das dimensões Loja, Produto e Tempo junto com a dimensão Lojas (o eixo de slicer) e, em seguida, retorna o grupo de medidas departamento, a identificação do departamento e o nome do funcionário.</span><span class="sxs-lookup"><span data-stu-id="c79e2-118">In this example, the DRILLTHROUGH statement queries the leaves of the Store, Product, and Time dimensions along the Stores dimension (the slicer axis), and then returns the department measure group, department ID, and employee's first name.</span></span>  
  
```  
DRILLTHROUGH  
Select {Leaves(Store), Leaves(Product), Leaves(Time),*} on 0  
From Stores  
RETURN [Department MeasureGroup].[Department Id], [Employee].[First Name]  
```  
  
## <a name="see-also"></a><span data-ttu-id="c79e2-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c79e2-119">See Also</span></span>  
 [<span data-ttu-id="c79e2-120">Manipulando dados &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="c79e2-120">Manipulating Data &#40;MDX&#41;</span></span>](mdx-data-manipulation-manipulating-data.md)  
  
  
