---
title: Opções de solicitação do perfil Distribuição de Comprimento de Coluna (tarefa Criação de Perfil de Dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Data Profiling Task Editor
ms.assetid: 1a4de41f-f38d-40ea-ba1b-6c0ef67ea52a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4c0ebb6f1e0a6df2c0e47311f7b8217c5ce6f2df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573240"
---
# <a name="column-length-distribution-profile-request-options-data-profiling-task"></a><span data-ttu-id="95fbb-102">Opções de solicitação do perfil Distribuição de Comprimento de Coluna (tarefa Criação de Perfil de Dados)</span><span class="sxs-lookup"><span data-stu-id="95fbb-102">Column Length Distribution Profile Request Options (Data Profiling Task)</span></span>
  <span data-ttu-id="95fbb-103">Use o painel **Propriedades da Solicitação** da página **Solicitações de Perfil** para definir as opções da **Solicitação de Perfil de Distribuição de Comprimento de Coluna** selecionada no painel de solicitações.</span><span class="sxs-lookup"><span data-stu-id="95fbb-103">Use the **Request Properties** pane of the **Profile Requests** page to set the options for the **Column Length Distribution Profile Request** selected in the requests pane.</span></span> <span data-ttu-id="95fbb-104">Um Perfil de Distribuição de Comprimento de Coluna reporta todos os comprimentos distintos de valores de cadeia de caracteres na coluna selecionada e a porcentagem de linhas na tabela que cada comprimento representa.</span><span class="sxs-lookup"><span data-stu-id="95fbb-104">A Column Length Distribution profile reports all the distinct lengths of string values in the selected column and the percentage of rows in the table that each length represents.</span></span> <span data-ttu-id="95fbb-105">Esse perfil pode ajudá-lo a identificar problemas em seus dados, como valores inválidos.</span><span class="sxs-lookup"><span data-stu-id="95fbb-105">This profile can help you identify problems in your data such as invalid values.</span></span> <span data-ttu-id="95fbb-106">Por exemplo, você cria o perfil de uma coluna com códigos de estados dos Estados Unidos com dois caracteres e descobre valores maiores que dois caracteres.</span><span class="sxs-lookup"><span data-stu-id="95fbb-106">For example, you profile a column of two-character United States state codes and discover values longer than two characters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="95fbb-107">As opções descritas neste tópico são exibidas na página **Solicitações de Perfil** do **Editor da Tarefa Criação de Perfil de Dados**.</span><span class="sxs-lookup"><span data-stu-id="95fbb-107">The options described in this topic appear on the **Profile Requests page** of the **Data Profiling Task Editor**.</span></span> <span data-ttu-id="95fbb-108">Para obter mais informações sobre essa página do editor, consulte [Editor da Tarefa Criação de Perfil de Dados &#40;Página Solicitações de perfil&#41;](data-profiling-task-editor-profile-requests-page.md).</span><span class="sxs-lookup"><span data-stu-id="95fbb-108">For more information about this page of the editor, see [Data Profiling Task Editor &#40;Profile Requests Page&#41;](data-profiling-task-editor-profile-requests-page.md).</span></span>  
  
 <span data-ttu-id="95fbb-109">Para obter mais informações sobre como usar a Tarefa Criação de Perfil de Dados, consulte [Configuração da Tarefa Criação de Perfil de Dados](data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="95fbb-109">For more information about how to use the Data Profiling Task, see [Setup of the Data Profiling Task](data-profiling-task.md).</span></span> <span data-ttu-id="95fbb-110">Para obter mais informações sobre como usar o Visualizador de Perfil de Dados para analisar a saída da Tarefa Criação de Perfil de Dados, consulte [Visualizador de Perfil de Dados](data-profile-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="95fbb-110">For more information about how to use the Data Profile Viewer to analyze the output of the Data Profiling Task, see [Data Profile Viewer](data-profile-viewer.md).</span></span>  
  
## <a name="request-properties-options"></a><span data-ttu-id="95fbb-111">Opções de Propriedades da Solicitação</span><span class="sxs-lookup"><span data-stu-id="95fbb-111">Request Properties Options</span></span>  
 <span data-ttu-id="95fbb-112">Em uma **Solicitação de Perfil de Distribuição de Comprimento de Coluna**, o painel **Propriedades da Solicitação** exibe os seguintes grupos de opções:</span><span class="sxs-lookup"><span data-stu-id="95fbb-112">For a **Column Length Distribution Profile Request**, the **Request Properties** pane displays the following groups of options:</span></span>  
  
-   <span data-ttu-id="95fbb-113">**Dados**que incluem as opções **TableOrView** e **Column**</span><span class="sxs-lookup"><span data-stu-id="95fbb-113">**Data**, which includes the **TableOrView** and **Column** options</span></span>  
  
-   <span data-ttu-id="95fbb-114">**Geral**</span><span class="sxs-lookup"><span data-stu-id="95fbb-114">**General**</span></span>  
  
-   <span data-ttu-id="95fbb-115">**Opções**</span><span class="sxs-lookup"><span data-stu-id="95fbb-115">**Options**</span></span>  
  
### <a name="data-options"></a><span data-ttu-id="95fbb-116">Opções de dados</span><span class="sxs-lookup"><span data-stu-id="95fbb-116">Data Options</span></span>  
 <span data-ttu-id="95fbb-117">**ConnectionManager**</span><span class="sxs-lookup"><span data-stu-id="95fbb-117">**ConnectionManager**</span></span>  
 <span data-ttu-id="95fbb-118">Selecione o gerente de conexões do [!INCLUDE[vstecado](../../includes/vstecado-md.md)] que usa o Provedor de Dados .NET para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) para conexão com o banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que contém a tabela ou a exibição que você deseja analisar.</span><span class="sxs-lookup"><span data-stu-id="95fbb-118">Select the existing [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that uses the .NET Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database that contains the table or view to be profiled.</span></span>  
  
 <span data-ttu-id="95fbb-119">**TableOrView**</span><span class="sxs-lookup"><span data-stu-id="95fbb-119">**TableOrView**</span></span>  
 <span data-ttu-id="95fbb-120">Selecione a tabela ou exibição existente que contêm a coluna para a qual será criado um perfil.</span><span class="sxs-lookup"><span data-stu-id="95fbb-120">Select the existing table or view that contains the column to be profiled.</span></span>  
  
 <span data-ttu-id="95fbb-121">Para obter mais informações, consulte a seção "Opções TableOrView" neste tópico.</span><span class="sxs-lookup"><span data-stu-id="95fbb-121">For more information, see the section, "TableorView Options," in this topic.</span></span>  
  
 <span data-ttu-id="95fbb-122">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="95fbb-122">**Column**</span></span>  
 <span data-ttu-id="95fbb-123">Selecione a coluna existente para a qual um perfil será criado.</span><span class="sxs-lookup"><span data-stu-id="95fbb-123">Select the existing column to be profiled.</span></span> <span data-ttu-id="95fbb-124">Selecione **(\*)** para analisar todas as colunas.</span><span class="sxs-lookup"><span data-stu-id="95fbb-124">Select **(\*)** to profile all columns.</span></span>  
  
 <span data-ttu-id="95fbb-125">Para obter mais informações, consulte a seção “Opções Column” neste tópico.</span><span class="sxs-lookup"><span data-stu-id="95fbb-125">For more information, see the section, "Column Options," in this topic.</span></span>  
  
#### <a name="tableorview-options"></a><span data-ttu-id="95fbb-126">Opções TableOrView</span><span class="sxs-lookup"><span data-stu-id="95fbb-126">TableOrView Options</span></span>  
 <span data-ttu-id="95fbb-127">**Esquema**</span><span class="sxs-lookup"><span data-stu-id="95fbb-127">**Schema**</span></span>  
 <span data-ttu-id="95fbb-128">Especifique o esquema ao qual a tabela selecionada pertence.</span><span class="sxs-lookup"><span data-stu-id="95fbb-128">Specify the schema to which the selected table belongs.</span></span> <span data-ttu-id="95fbb-129">Esta opção é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="95fbb-129">This option is read-only.</span></span>  
  
 <span data-ttu-id="95fbb-130">**Table**</span><span class="sxs-lookup"><span data-stu-id="95fbb-130">**Table**</span></span>  
 <span data-ttu-id="95fbb-131">Exibe o nome da tabela selecionada.</span><span class="sxs-lookup"><span data-stu-id="95fbb-131">Displays the name of the selected table.</span></span> <span data-ttu-id="95fbb-132">Esta opção é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="95fbb-132">This option is read-only.</span></span>  
  
#### <a name="column-options"></a><span data-ttu-id="95fbb-133">Opções de Coluna</span><span class="sxs-lookup"><span data-stu-id="95fbb-133">Column Options</span></span>  
 <span data-ttu-id="95fbb-134">**IsWildCard**</span><span class="sxs-lookup"><span data-stu-id="95fbb-134">**IsWildCard**</span></span>  
 <span data-ttu-id="95fbb-135">Especifica se o curinga **(\*)** foi selecionado.</span><span class="sxs-lookup"><span data-stu-id="95fbb-135">Specifies whether the **(\*)** wildcard has been selected.</span></span> <span data-ttu-id="95fbb-136">Esta opção será definida como **True** se você tiver selecionado **(\*)** para analisar todas as colunas.</span><span class="sxs-lookup"><span data-stu-id="95fbb-136">This option is set to **True** if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="95fbb-137">Será **Falso** se você selecionou uma coluna individual para a criação de um perfil.</span><span class="sxs-lookup"><span data-stu-id="95fbb-137">It is **False** if you have selected an individual column to be profiled.</span></span> <span data-ttu-id="95fbb-138">Esta opção é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="95fbb-138">This option is read-only.</span></span>  
  
 <span data-ttu-id="95fbb-139">**ColumnName**</span><span class="sxs-lookup"><span data-stu-id="95fbb-139">**ColumnName**</span></span>  
 <span data-ttu-id="95fbb-140">Exibe o nome da coluna selecionada.</span><span class="sxs-lookup"><span data-stu-id="95fbb-140">Displays the name of the selected column.</span></span> <span data-ttu-id="95fbb-141">Esta opção estará em branco se você tiver selecionado **(\*)** para analisar todas as colunas.</span><span class="sxs-lookup"><span data-stu-id="95fbb-141">This option is blank if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="95fbb-142">Esta opção é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="95fbb-142">This option is read-only.</span></span>  
  
 <span data-ttu-id="95fbb-143">**StringCompareOptions**</span><span class="sxs-lookup"><span data-stu-id="95fbb-143">**StringCompareOptions**</span></span>  
 <span data-ttu-id="95fbb-144">Esta opção não se aplica ao Perfil de Distribuição de Comprimento de Coluna.</span><span class="sxs-lookup"><span data-stu-id="95fbb-144">This option does not apply to the Column Length Distribution Profile.</span></span>  
  
### <a name="general-options"></a><span data-ttu-id="95fbb-145">Opções gerais</span><span class="sxs-lookup"><span data-stu-id="95fbb-145">General Options</span></span>  
 <span data-ttu-id="95fbb-146">**RequestID**</span><span class="sxs-lookup"><span data-stu-id="95fbb-146">**RequestID**</span></span>  
 <span data-ttu-id="95fbb-147">Digite um nome descritivo para identificar esta solicitação de perfil.</span><span class="sxs-lookup"><span data-stu-id="95fbb-147">Type a descriptive name to identify this profile request.</span></span> <span data-ttu-id="95fbb-148">Normalmente, não é necessário alterar o valor gerado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="95fbb-148">Typically, you do not have to change the autogenerated value.</span></span>  
  
### <a name="options"></a><span data-ttu-id="95fbb-149">Opções</span><span class="sxs-lookup"><span data-stu-id="95fbb-149">Options</span></span>  
 <span data-ttu-id="95fbb-150">**IgnoreLeadingSpaces**</span><span class="sxs-lookup"><span data-stu-id="95fbb-150">**IgnoreLeadingSpaces**</span></span>  
 <span data-ttu-id="95fbb-151">Indique se espaços à esquerda devem ser ignorados quando o perfil comparar valores da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="95fbb-151">Indicate whether to ignore leading spaces when the profile compares string values.</span></span> <span data-ttu-id="95fbb-152">O valor padrão desta opção é **False**.</span><span class="sxs-lookup"><span data-stu-id="95fbb-152">The default value of this option is **False**.</span></span>  
  
 <span data-ttu-id="95fbb-153">**IgnoreTrailingSpaces**</span><span class="sxs-lookup"><span data-stu-id="95fbb-153">**IgnoreTrailingSpaces**</span></span>  
 <span data-ttu-id="95fbb-154">Indique se espaços à direita devem ser ignorados quando o perfil comparar valores da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="95fbb-154">Indicate whether to ignore trailing spaces when the profile compares string values.</span></span> <span data-ttu-id="95fbb-155">O valor padrão desta opção é **Verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="95fbb-155">The default value of this option is **True**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95fbb-156">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="95fbb-156">See Also</span></span>  
 <span data-ttu-id="95fbb-157">[Editor da tarefa Criação de Perfil de Dados &#40;Página Geral&#41;](../general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="95fbb-157">[Data Profiling Task Editor &#40;General Page&#41;](../general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="95fbb-158">Formulário de Perfil Rápido de Tabela Única &#40;Tarefa Criação de Perfil de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="95fbb-158">Single Table Quick Profile Form &#40;Data Profiling Task&#41;</span></span>](single-table-quick-profile-form-data-profiling-task.md)  
  
  
