---
title: Mapear parâmetros de consulta para variáveis em uma tarefa Executar SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- queries [Integration Services], parameter mapping
- parameterized SQL commands [Integration Services]
- parameters [Integration Services]
- mapping query parameters to variables [Integration Services]
- Execute SQL task [Integration Services]
- variables [Integration Services], mapping parameters to
ms.assetid: 6a164349-dfcf-4995-80bc-d4e7aee52a83
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8511d70b40f2934680e1cb790763045c04e8204a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573168"
---
# <a name="map-query-parameters-to-variables-in-an-execute-sql-task"></a><span data-ttu-id="0b5f4-102">Mapear parâmetros de consulta para variáveis em uma tarefa Executar SQL</span><span class="sxs-lookup"><span data-stu-id="0b5f4-102">Map Query Parameters to Variables in an Execute SQL Task</span></span>

  <span data-ttu-id="0b5f4-103">Este tópico descreve como usar uma instrução SQL parametrizada na tarefa Executar SQL e criar mapeamentos entre variáveis e os parâmetros na instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="0b5f4-103">This topic describes how to use a parameterized SQL statement in the Execute SQL task and create mappings between variables and the parameters in the SQL statement.</span></span>  
  
 <span data-ttu-id="0b5f4-104">Para saber mais sobre a tarefa Executar SQL, os marcadores de parâmetro e os nomes de parâmetro usados com diferentes tipos de conexão, consulte [Tarefa Executar SQL](control-flow/execute-sql-task.md) e [Parâmetros e códigos de retorno na tarefa Executar SQL](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="0b5f4-104">To learn more about the Execute SQL task, the parameter markers, and parameter names you use with different connection types, see [Execute SQL Task](control-flow/execute-sql-task.md) and [Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span></span>  
  
### <a name="to-map-a-query-parameter-to-a-variable"></a><span data-ttu-id="0b5f4-105">Para mapear um parâmetro de consulta para uma variável</span><span class="sxs-lookup"><span data-stu-id="0b5f4-105">To map a query parameter to a variable</span></span>  
  
1.  <span data-ttu-id="0b5f4-106">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o pacote do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] com o qual você deseja trabalhar.</span><span class="sxs-lookup"><span data-stu-id="0b5f4-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package you want to work with.</span></span>  
  
2.  <span data-ttu-id="0b5f4-107">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="0b5f4-107">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="0b5f4-108">Clique na guia **Fluxo de Controle** .</span><span class="sxs-lookup"><span data-stu-id="0b5f4-108">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="0b5f4-109">Se o pacote ainda não incluir uma tarefa Executar SQL, adicione uma ao fluxo de controle do pacote.</span><span class="sxs-lookup"><span data-stu-id="0b5f4-109">If the package does not already include an Execute SQL task, add one to the control flow of the package.</span></span> <span data-ttu-id="0b5f4-110">Para obter mais informações, consulte [Adicionar ou excluir uma tarefa ou um contêiner em um fluxo de controle](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)</span><span class="sxs-lookup"><span data-stu-id="0b5f4-110">For more information, see [Add or Delete a Task or a Container in a Control Flow](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)</span></span>  
  <span data-ttu-id="0b5f4-111">.</span><span class="sxs-lookup"><span data-stu-id="0b5f4-111">.</span></span>  
  
5.  <span data-ttu-id="0b5f4-112">Clique duas vezes na tarefa Executar SQL.</span><span class="sxs-lookup"><span data-stu-id="0b5f4-112">Double-click the Execute SQL task.</span></span>  
  
6.  <span data-ttu-id="0b5f4-113">Forneça um comando SQL parametrizado de um dos seguintes modos:</span><span class="sxs-lookup"><span data-stu-id="0b5f4-113">Provide a parameterized SQL command in one of the following ways:</span></span>  
  
    -   <span data-ttu-id="0b5f4-114">Use a entrada direta e digite o comando SQL na propriedade SQLStatement.</span><span class="sxs-lookup"><span data-stu-id="0b5f4-114">Use direct input and type the SQL command in the SQLStatement property.</span></span>  
  
    -   <span data-ttu-id="0b5f4-115">Use a entrada direta, clique em **Construir Consulta**e crie um comando SQL usando as ferramentas gráficas que o Construtor de Consultas fornece.</span><span class="sxs-lookup"><span data-stu-id="0b5f4-115">Use direct input, click **Build Query**, and then create an SQL command using the graphical tools that the Query Builder provides.</span></span>  
  
    -   <span data-ttu-id="0b5f4-116">Use uma conexão de arquivo e depois faça referência ao arquivo que contém o comando SQL.</span><span class="sxs-lookup"><span data-stu-id="0b5f4-116">Use a file connection and then reference the file that contains the SQL command.</span></span>  
  
    -   <span data-ttu-id="0b5f4-117">Use uma variável e depois faça referência à variável que contém o comando SQL.</span><span class="sxs-lookup"><span data-stu-id="0b5f4-117">Use a variable and then reference the variable that contains the SQL command.</span></span>  
  
     <span data-ttu-id="0b5f4-118">Os marcadores de parâmetros que você usa nas instruções SQL parametrizadas dependem do tipo de conexão que a tarefa Executar SQL usa.</span><span class="sxs-lookup"><span data-stu-id="0b5f4-118">The parameter markers that you use in parameterized SQL statements depend on the connection type that the Execute SQL task uses.</span></span>  
  
    |<span data-ttu-id="0b5f4-119">Tipo de conexão</span><span class="sxs-lookup"><span data-stu-id="0b5f4-119">Connection type</span></span>|<span data-ttu-id="0b5f4-120">Marcador de parâmetro</span><span class="sxs-lookup"><span data-stu-id="0b5f4-120">Parameter marker</span></span>|  
    |---------------------|----------------------|  
    |<span data-ttu-id="0b5f4-121">ADO</span><span class="sxs-lookup"><span data-stu-id="0b5f4-121">ADO</span></span>|<span data-ttu-id="0b5f4-122">?</span><span class="sxs-lookup"><span data-stu-id="0b5f4-122">?</span></span>|  
    |<span data-ttu-id="0b5f4-123">ADO.NET e SQLMOBILE</span><span class="sxs-lookup"><span data-stu-id="0b5f4-123">ADO.NET and SQLMOBILE</span></span>|@\<parameter name>|  
    |<span data-ttu-id="0b5f4-124">ODBCODBC</span><span class="sxs-lookup"><span data-stu-id="0b5f4-124">ODBC</span></span>|<span data-ttu-id="0b5f4-125">?</span><span class="sxs-lookup"><span data-stu-id="0b5f4-125">?</span></span>|  
    |<span data-ttu-id="0b5f4-126">EXCEL e OLE DB</span><span class="sxs-lookup"><span data-stu-id="0b5f4-126">EXCEL and OLE DB</span></span>|<span data-ttu-id="0b5f4-127">?</span><span class="sxs-lookup"><span data-stu-id="0b5f4-127">?</span></span>|  
  
     <span data-ttu-id="0b5f4-128">A tabela a seguir lista exemplos do comando SELECT por tipo de gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="0b5f4-128">The following table lists examples of the SELECT command by connection manager type.</span></span> <span data-ttu-id="0b5f4-129">Os parâmetros fornecem os valores de filtro nas cláusulas WHERE.</span><span class="sxs-lookup"><span data-stu-id="0b5f4-129">Parameters provide the filter values in the WHERE clauses.</span></span> <span data-ttu-id="0b5f4-130">Os exemplos usam SELECT para retornar produtos da tabela **Produto** em [!INCLUDE[ssSampleDBUserInputNonLocal](../includes/sssampledbuserinputnonlocal-md.md)] que tenham uma **ProductID** maior e menor que os valores especificados pelos dois parâmetros.</span><span class="sxs-lookup"><span data-stu-id="0b5f4-130">The examples use SELECT to return products from the **Product** table in [!INCLUDE[ssSampleDBUserInputNonLocal](../includes/sssampledbuserinputnonlocal-md.md)] that have a **ProductID** greater than and less than the values specified by two parameters.</span></span>  
  
    |<span data-ttu-id="0b5f4-131">Tipo de conexão</span><span class="sxs-lookup"><span data-stu-id="0b5f4-131">Connection type</span></span>|<span data-ttu-id="0b5f4-132">Sintaxe de SELECT</span><span class="sxs-lookup"><span data-stu-id="0b5f4-132">SELECT syntax</span></span>|  
    |---------------------|-------------------|  
    |<span data-ttu-id="0b5f4-133">EXCEL, ODBC e OLEDB</span><span class="sxs-lookup"><span data-stu-id="0b5f4-133">EXCEL, ODBC, and OLEDB</span></span>|`SELECT* FROM Production.Product WHERE ProductId > ? AND ProductID < ?`|  
    |<span data-ttu-id="0b5f4-134">ADO</span><span class="sxs-lookup"><span data-stu-id="0b5f4-134">ADO</span></span>|`SELECT* FROM Production.Product WHERE ProductId > ? AND ProductID < ?`|  
    |[!INCLUDE[vstecado](../includes/vstecado-md.md)]|`SELECT* FROM Production.Product WHERE ProductId > @parmMinProductID AND ProductID < @parmMaxProductID`|  
  
     <span data-ttu-id="0b5f4-135">Para obter exemplos de como usar parâmetros com procedimentos armazenados, consulte [Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="0b5f4-135">For examples of using parameters with stored procedures, see [Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span></span>  
  
7.  <span data-ttu-id="0b5f4-136">Clique em **Mapeamento de Parâmetro**.</span><span class="sxs-lookup"><span data-stu-id="0b5f4-136">Click **Parameter Mapping**.</span></span>  
  
8.  <span data-ttu-id="0b5f4-137">Para adicionar um mapeamento de parâmetro, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="0b5f4-137">To add a parameter mapping, click **Add**.</span></span>  
  
9. <span data-ttu-id="0b5f4-138">Forneça um nome na caixa **Nome do Parâmetro** .</span><span class="sxs-lookup"><span data-stu-id="0b5f4-138">Provide a name in the **Parameter Name** box.</span></span>  
  
     <span data-ttu-id="0b5f4-139">Os nomes de parâmetros que você usa dependem do tipo de conexão que a tarefa Executar SQL usa.</span><span class="sxs-lookup"><span data-stu-id="0b5f4-139">The parameter names that you use depend on the connection type that the Execute SQL task uses.</span></span>  
  
    |<span data-ttu-id="0b5f4-140">Tipo de conexão</span><span class="sxs-lookup"><span data-stu-id="0b5f4-140">Connection type</span></span>|<span data-ttu-id="0b5f4-141">Nome do parâmetro</span><span class="sxs-lookup"><span data-stu-id="0b5f4-141">Parameter name</span></span>|  
    |---------------------|--------------------|  
    |<span data-ttu-id="0b5f4-142">ADO</span><span class="sxs-lookup"><span data-stu-id="0b5f4-142">ADO</span></span>|<span data-ttu-id="0b5f4-143">Param1, Param2, ...</span><span class="sxs-lookup"><span data-stu-id="0b5f4-143">Param1, Param2, ...</span></span>|  
    |<span data-ttu-id="0b5f4-144">ADO.NET e SQLMOBILE</span><span class="sxs-lookup"><span data-stu-id="0b5f4-144">ADO.NET and SQLMOBILE</span></span>|@\<parameter name>|  
    |<span data-ttu-id="0b5f4-145">ODBCODBC</span><span class="sxs-lookup"><span data-stu-id="0b5f4-145">ODBC</span></span>|<span data-ttu-id="0b5f4-146">1, 2, 3, ...</span><span class="sxs-lookup"><span data-stu-id="0b5f4-146">1, 2, 3, ...</span></span>|  
    |<span data-ttu-id="0b5f4-147">EXCEL e OLE DB</span><span class="sxs-lookup"><span data-stu-id="0b5f4-147">EXCEL and OLE DB</span></span>|<span data-ttu-id="0b5f4-148">0, 1, 2, 3, ...</span><span class="sxs-lookup"><span data-stu-id="0b5f4-148">0, 1, 2, 3, ...</span></span>|  
  
10. <span data-ttu-id="0b5f4-149">Na lista **Nome da Variável** , selecione uma variável.</span><span class="sxs-lookup"><span data-stu-id="0b5f4-149">From the **Variable Name** list, select a variable.</span></span> <span data-ttu-id="0b5f4-150">Para obter mais informações, consulte [Adicionar, excluir, alterar o escopo de uma variável definida pelo usuário em um pacote](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md).</span><span class="sxs-lookup"><span data-stu-id="0b5f4-150">For more information, see [Add, Delete, Change Scope of User-Defined Variable in a Package](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md).</span></span>  
  
11. <span data-ttu-id="0b5f4-151">Na lista **Direção** , especifique se o parâmetro é uma entrada, uma saída ou um valor de retorno.</span><span class="sxs-lookup"><span data-stu-id="0b5f4-151">In the **Direction** list, specify if the parameter is an input, an output, or a return value.</span></span>  
  
12. <span data-ttu-id="0b5f4-152">Na lista **Tipo de Dados** , defina o tipo de dados do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="0b5f4-152">In the **Data Type** list, set the data type of the parameter.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="0b5f4-153">O tipo de dados do parâmetro deve ser compatível com o tipo de dados da variável.</span><span class="sxs-lookup"><span data-stu-id="0b5f4-153">The data type of the parameter must be compatible with the data type of the variable.</span></span>  
  
13. <span data-ttu-id="0b5f4-154">Repita as etapas de 8 a 11 para cada parâmetro na instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="0b5f4-154">Repeat steps 8 through 11 for each parameter in the SQL statement.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="0b5f4-155">A ordem dos mapeamentos de parâmetros deve ser igual à ordem em que os parâmetros aparecem na instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="0b5f4-155">The order of parameter mappings must be the same as the order in which the parameters appear in the SQL statement.</span></span>  
  
14. <span data-ttu-id="0b5f4-156">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0b5f4-156">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b5f4-157">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0b5f4-157">See Also</span></span>  
 <span data-ttu-id="0b5f4-158">[Tarefa Executar SQL](control-flow/execute-sql-task.md) </span><span class="sxs-lookup"><span data-stu-id="0b5f4-158">[Execute SQL Task](control-flow/execute-sql-task.md) </span></span>  
 <span data-ttu-id="0b5f4-159">[Parâmetros e códigos de retorno na tarefa Executar SQL](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md) </span><span class="sxs-lookup"><span data-stu-id="0b5f4-159">[Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md) </span></span>  
 [<span data-ttu-id="0b5f4-160">Variáveis do SSIS &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0b5f4-160">Integration Services &#40;SSIS&#41; Variables</span></span>](integration-services-ssis-variables.md)  
  
  
