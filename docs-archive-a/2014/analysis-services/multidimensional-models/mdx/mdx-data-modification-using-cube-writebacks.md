---
title: Usando o cubo write-backs (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- writeback [Analysis Services], cubes
- cubes [Analysis Services], modifying
- modifying cubes
- UPDATE CUBE statement
- cubes [Analysis Services], writeback
ms.assetid: ae2385fc-7fa0-4f8e-98d7-dcb0a5f0eeea
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3ac43e9206619117c1fc090a594ca32ccbeeeb31
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572739"
---
# <a name="using-cube-writebacks-mdx"></a><span data-ttu-id="d7d74-102">Usando Cube Writebacks (MDX)</span><span class="sxs-lookup"><span data-stu-id="d7d74-102">Using Cube Writebacks (MDX)</span></span>
  <span data-ttu-id="d7d74-103">Você atualiza um cubo usando a instrução [UPDATE CUBE](/sql/mdx/mdx-data-manipulation-update-cube) .</span><span class="sxs-lookup"><span data-stu-id="d7d74-103">You update a cube by using the [UPDATE CUBE](/sql/mdx/mdx-data-manipulation-update-cube) statement.</span></span> <span data-ttu-id="d7d74-104">Essa instrução permite que você atualize uma tupla com um valor específico.</span><span class="sxs-lookup"><span data-stu-id="d7d74-104">This statement lets you update a tuple with a specific value.</span></span> <span data-ttu-id="d7d74-105">Para usar a instrução UPDATE CUBE de forma eficiente para atualizar um cubo, você precisa entender a sintaxe da instrução, as condições de erro que podem acontecer, e como as atualizações podem afetar um cubo.</span><span class="sxs-lookup"><span data-stu-id="d7d74-105">To effectively use the UPDATE CUBE statement to update a cube, you have to understand the syntax for the statement, the error conditions that can occur, and the affect that updates can have on a cube.</span></span>  
  
## <a name="update-cube-statement-syntax"></a><span data-ttu-id="d7d74-106">Sintaxe da instrução UPDATE CUBE</span><span class="sxs-lookup"><span data-stu-id="d7d74-106">UPDATE CUBE Statement Syntax</span></span>  
 <span data-ttu-id="d7d74-107">A seguinte sintaxe descreve a instrução UPDATE CUBE:</span><span class="sxs-lookup"><span data-stu-id="d7d74-107">The following syntax describes the UPDATE CUBE statement:</span></span>  
  
```  
UPDATE [CUBE] <Cube_Name> SET <tuple>.VALUE = <value> [,<tuple>.VALUE = <value>...]  
 [ USE_EQUAL_ALLOCATION | USE_EQUAL_INCREMENT |  
  USE_WEIGHTED_ALLOCATION [BY <weight value_expression>] |  
  USE_WEIGHTED_INCREMENT [BY <weight value_expression>] ]   
```  
  
 <span data-ttu-id="d7d74-108">Se um conjunto completo de coordenadas não for especificado para a tupla, as coordenadas não especificadas usarão o membro padrão da hierarquia.</span><span class="sxs-lookup"><span data-stu-id="d7d74-108">If a full set of coordinates is not specified for the tuple, the unspecified coordinates will use the default member of the hierarchy.</span></span> <span data-ttu-id="d7d74-109">A tupla identificada deve fazer referência a uma célula que seja agregada com a função [Sum](/sql/mdx/sum-mdx) , e não deve usar um membro calculado como uma das coordenadas da célula.</span><span class="sxs-lookup"><span data-stu-id="d7d74-109">The tuple identified must reference a cell that is aggregated with the [Sum](/sql/mdx/sum-mdx) function, and must not use a calculated member as one of the cell's coordinates.</span></span>  
  
 <span data-ttu-id="d7d74-110">Você pode pensar na instrução UPDATE CUBE como uma sub-rotina que gera uma série de operações de write-back individuais a células atômicas.</span><span class="sxs-lookup"><span data-stu-id="d7d74-110">You can think of the UPDATE CUBE statement as a subroutine that generates a series of individual writeback operations to atomic cells.</span></span> <span data-ttu-id="d7d74-111">Todas essas operações de write-back individuais são acumuladas à soma especificada.</span><span class="sxs-lookup"><span data-stu-id="d7d74-111">All these individual writeback operations then roll up into the specified sum.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d7d74-112">Quando células atualizadas não se sobrepõem, a propriedade de cadeia de caracteres da conexão `Update Isolation Level` pode ser usada para aprimorar o desempenho de UPDATE CUBE.</span><span class="sxs-lookup"><span data-stu-id="d7d74-112">When updated cells do not overlap, the `Update Isolation Level` connection string property can be used to enhance performance for UPDATE CUBE.</span></span> <span data-ttu-id="d7d74-113">Para obter mais informações, consulte <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.ConnectionString%2A>.</span><span class="sxs-lookup"><span data-stu-id="d7d74-113">For more information, see <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.ConnectionString%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7d74-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d7d74-114">Example</span></span>  
 <span data-ttu-id="d7d74-115">Você pode testar o UPDATE CUBE usando o grupo de medidas Público-Alvo das Vendas no cubo do Adventure Works.</span><span class="sxs-lookup"><span data-stu-id="d7d74-115">You can test UPDATE CUBE using the Sales Targets measure group in the Adventure Works cube.</span></span> <span data-ttu-id="d7d74-116">Esse grupo de medidas consiste em medidas agregadas por SUM, que é uma exigência para UPDATE CUBE.</span><span class="sxs-lookup"><span data-stu-id="d7d74-116">This measure group consists of measures aggregated by SUM, which is a requirement for UPDATE CUBE.</span></span>  
  
1.  <span data-ttu-id="d7d74-117">Habilite o write-back para o grupo de medidas Público-Alvo das Vendas no banco de dados do Adventure Works.</span><span class="sxs-lookup"><span data-stu-id="d7d74-117">Enable writeback for the Sales Targets measure group in the Adventure Works database.</span></span> <span data-ttu-id="d7d74-118">No Management Studio, clique com o botão direito do mouse em um grupo de medidas, aponte para **Opções de Write-back**, escolha **Habilitar Write-back**.</span><span class="sxs-lookup"><span data-stu-id="d7d74-118">In Management Studio, right-click a measure group, point to **Write Back Options**, choose **Enable Writeback**.</span></span>  
  
     <span data-ttu-id="d7d74-119">Você deve ver uma nova tabela de write-back na pasta Write-back.</span><span class="sxs-lookup"><span data-stu-id="d7d74-119">You should see a new writeback table in the Writeback folder.</span></span> <span data-ttu-id="d7d74-120">O nome da tabela é WriteTable_Fact Sales Quota.</span><span class="sxs-lookup"><span data-stu-id="d7d74-120">The table name is WriteTable_Fact Sales Quota.</span></span>  
  
2.  <span data-ttu-id="d7d74-121">Abra uma janela de consulta MDX.</span><span class="sxs-lookup"><span data-stu-id="d7d74-121">Open an MDX query window.</span></span> <span data-ttu-id="d7d74-122">Execute a seguinte instrução select para exibir o valor original:</span><span class="sxs-lookup"><span data-stu-id="d7d74-122">Run the following select statement to view the original value:</span></span>  
  
    ```  
    SELECT [Measures].[Sales Amount Quota] on 0 ,  
    [Employee].[Employee Department].[Title].&[Sales Representative].children on 1  
    FROM [Adventure Works]  
  
    ```  
  
     <span data-ttu-id="d7d74-123">Você deve ver as contas do valor de vendas para cada representante.</span><span class="sxs-lookup"><span data-stu-id="d7d74-123">You should see sales amount quotas for each representative.</span></span>  
  
3.  <span data-ttu-id="d7d74-124">Execute a instrução update cube para fazer write-back de um novo valor.</span><span class="sxs-lookup"><span data-stu-id="d7d74-124">Run the update cube statement to write back a new value.</span></span> <span data-ttu-id="d7d74-125">Neste exemplo, estamos definindo a cota do valor de vendas como 0.</span><span class="sxs-lookup"><span data-stu-id="d7d74-125">In this example, we are setting the sales amount quota to 0.</span></span> <span data-ttu-id="d7d74-126">Como o novo valor é 0, não especifique um método de alocação.</span><span class="sxs-lookup"><span data-stu-id="d7d74-126">Because the new value is 0, do not specify an allocation method.</span></span>  
  
    ```  
    UPDATE CUBE [Adventure Works]   
    SET ([Measures].[Sales Amount Quota], [Employee].[Employee Department].[Department].&[Sales]) = 0  
  
    ```  
  
4.  <span data-ttu-id="d7d74-127">Reexecute a instrução SELECT.</span><span class="sxs-lookup"><span data-stu-id="d7d74-127">Re-run the SELECT statement.</span></span> <span data-ttu-id="d7d74-128">Agora você deve ver zero para as cotas.</span><span class="sxs-lookup"><span data-stu-id="d7d74-128">You should now see zero for the quotas.</span></span>  
  
 <span data-ttu-id="d7d74-129">O valor de write-back é restrito à sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d7d74-129">The writeback value is constrained to the current session.</span></span> <span data-ttu-id="d7d74-130">Para manter o valor em usuários e sessões, processe a tabela de write-back.</span><span class="sxs-lookup"><span data-stu-id="d7d74-130">To persist the value across users and sessions, process the writeback table.</span></span> <span data-ttu-id="d7d74-131">No Management Studio, clique com o botão direito do mouse em Cota de Vendas de WriteTable_Fact e escolha **Processar**.</span><span class="sxs-lookup"><span data-stu-id="d7d74-131">In Management Studio, right-click WriteTable_Fact Sales Quota and choose **Process**.</span></span>  
  
 <span data-ttu-id="d7d74-132">Para especificar um método de alocação, o novo valor deve ser maior que zero.</span><span class="sxs-lookup"><span data-stu-id="d7d74-132">To specify an allocation method, the new value must be greater than zero.</span></span> <span data-ttu-id="d7d74-133">Neste exemplo, o novo valor de Cota do Valor de Vendas é dois milhões e o método de alocação distribui o valor por todos os representantes de vendas.</span><span class="sxs-lookup"><span data-stu-id="d7d74-133">In this example, the new value for Sales Amount Quota is two million and the allocation method distributes the amount across all sales representatives.</span></span>  
  
```  
UPDATE CUBE [Adventure Works]   
SET ([Measures].[Sales Amount Quota], [Employee].[Employee Department].[Department].&[Sales]) = 2000000   
USE_EQUAL_ALLOCATION  
```  
  
## <a name="error-conditions"></a><span data-ttu-id="d7d74-134">Condições de erro</span><span class="sxs-lookup"><span data-stu-id="d7d74-134">Error Conditions</span></span>  
 <span data-ttu-id="d7d74-135">A tabela a seguir descreve a causa de falha dos write-backs e o resultado desses erros.</span><span class="sxs-lookup"><span data-stu-id="d7d74-135">The following table describes both what can cause writebacks to fail and the result of those errors.</span></span>  
  
|<span data-ttu-id="d7d74-136">Condição de erro</span><span class="sxs-lookup"><span data-stu-id="d7d74-136">Error Condition</span></span>|<span data-ttu-id="d7d74-137">Result</span><span class="sxs-lookup"><span data-stu-id="d7d74-137">Result</span></span>|  
|---------------------|------------|  
|<span data-ttu-id="d7d74-138">A atualização inclui membros da mesma dimensão que não existem um com o outro.</span><span class="sxs-lookup"><span data-stu-id="d7d74-138">Update includes members from the same dimension that do not exist with one another.</span></span>|<span data-ttu-id="d7d74-139">Haverá falha na atualização.</span><span class="sxs-lookup"><span data-stu-id="d7d74-139">Update will fail.</span></span> <span data-ttu-id="d7d74-140">O espaço do cubo não conterá a célula mencionada.</span><span class="sxs-lookup"><span data-stu-id="d7d74-140">The cube space will not contain the referenced cell.</span></span>|  
|<span data-ttu-id="d7d74-141">A atualização inclui uma medida com origem em uma medida de um tipo não atribuído.</span><span class="sxs-lookup"><span data-stu-id="d7d74-141">Update includes a measure sourced to a measure of an unsigned type.</span></span>|<span data-ttu-id="d7d74-142">Haverá falha na atualização.</span><span class="sxs-lookup"><span data-stu-id="d7d74-142">Update will fail.</span></span> <span data-ttu-id="d7d74-143">Os incrementos requerem que a medida possa receber um valor negativo.</span><span class="sxs-lookup"><span data-stu-id="d7d74-143">Increments require that the measure be able to take a negative value.</span></span>|  
|<span data-ttu-id="d7d74-144">A atualização inclui uma medida que agrega um item diferente da soma.</span><span class="sxs-lookup"><span data-stu-id="d7d74-144">Update includes a measure that aggregates other than sum.</span></span>|<span data-ttu-id="d7d74-145">Foi gerado um erro.</span><span class="sxs-lookup"><span data-stu-id="d7d74-145">An error is raised.</span></span>|  
|<span data-ttu-id="d7d74-146">Foi tentada uma atualização em um subcubo.</span><span class="sxs-lookup"><span data-stu-id="d7d74-146">Update was tried on a subcube.</span></span>|<span data-ttu-id="d7d74-147">Foi gerado um erro.</span><span class="sxs-lookup"><span data-stu-id="d7d74-147">An error is raised.</span></span>|  
  
## <a name="affect-of-cube-changes"></a><span data-ttu-id="d7d74-148">Efeito das mudanças do cubo</span><span class="sxs-lookup"><span data-stu-id="d7d74-148">Affect of Cube Changes</span></span>  
 <span data-ttu-id="d7d74-149">As seguintes mudanças não vão afetar um write-back:</span><span class="sxs-lookup"><span data-stu-id="d7d74-149">The following changes will not have an effect on a writeback:</span></span>  
  
-   <span data-ttu-id="d7d74-150">Processamento de um cubo, dos grupos de medidas do cubo ou das dimensões do cubo.</span><span class="sxs-lookup"><span data-stu-id="d7d74-150">Processing of a cube, the cube's measure groups, or the cube's dimensions.</span></span>  
  
-   <span data-ttu-id="d7d74-151">Adicionando atributos a qualquer dimensão.</span><span class="sxs-lookup"><span data-stu-id="d7d74-151">Adding attributes to any dimension.</span></span>  
  
-   <span data-ttu-id="d7d74-152">Adicionando uma nova dimensão.</span><span class="sxs-lookup"><span data-stu-id="d7d74-152">Adding a new dimension.</span></span>  
  
-   <span data-ttu-id="d7d74-153">Excluindo uma dimensão que não inclui o write-back.</span><span class="sxs-lookup"><span data-stu-id="d7d74-153">Deleting a dimension that does not include the writeback.</span></span>  
  
-   <span data-ttu-id="d7d74-154">Adicionando, modificando ou removendo uma hierarquia.</span><span class="sxs-lookup"><span data-stu-id="d7d74-154">Adding, modifying, or removing a hierarchy.</span></span>  
  
-   <span data-ttu-id="d7d74-155">Adicionando uma nova medida.</span><span class="sxs-lookup"><span data-stu-id="d7d74-155">Adding a new measure.</span></span>  
  
 <span data-ttu-id="d7d74-156">As seguintes mudanças não podem ser feitas sem remover os dados de write-back:</span><span class="sxs-lookup"><span data-stu-id="d7d74-156">The following changes cannot be made without removing the writeback data:</span></span>  
  
-   <span data-ttu-id="d7d74-157">Excluindo um atributo, ou sua hierarquia de atributo, se o atributo estiver incluído no write-back.</span><span class="sxs-lookup"><span data-stu-id="d7d74-157">Deleting an attribute, or its attribute hierarchy, if the attribute is included in the writeback.</span></span> <span data-ttu-id="d7d74-158">Isso inclui explicitamente remover o atributo, ou sua hierarquia de atributo, ou remover a dimensão pai do atributo.</span><span class="sxs-lookup"><span data-stu-id="d7d74-158">This includes explicitly removing the attribute, or its attribute hierarchy, or removing the attribute's parent dimension.</span></span>  
  
-   <span data-ttu-id="d7d74-159">Excluindo uma medida incluída no write-back.</span><span class="sxs-lookup"><span data-stu-id="d7d74-159">Deleting a measure included in the writeback.</span></span>  
  
-   <span data-ttu-id="d7d74-160">Adicionando um atributo sem um nível `(All)` a uma dimensão incluída no write-back.</span><span class="sxs-lookup"><span data-stu-id="d7d74-160">Adding an attribute without an `(All)` level to a dimension included in the writeback.</span></span>  
  
-   <span data-ttu-id="d7d74-161">Alterando a granularidade da dimensão da dimensão incluída no write-back.</span><span class="sxs-lookup"><span data-stu-id="d7d74-161">Changing the dimension granularity for a dimension included in the writeback.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7d74-162">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d7d74-162">See Also</span></span>  
 [<span data-ttu-id="d7d74-163">Modificando dados &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="d7d74-163">Modifying Data &#40;MDX&#41;</span></span>](mdx-data-modification-modifying-data.md)  
  
  
