---
title: Opções da solicitação do perfil Razão Nula de Coluna (Tarefa Criação de Perfil de Dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Data Profiling Task Editor
ms.assetid: 157ef8e4-fd23-4f81-8194-eebf74e9fd86
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0e47c09a9a19eae4aed21c0c518430bc19a45648
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573238"
---
# <a name="column-null-ratio-profile-request-options-data-profiling-task"></a><span data-ttu-id="ab200-102">Opções da solicitação do perfil Razão Nula de Coluna (tarefa Criação de Perfil de Dados)</span><span class="sxs-lookup"><span data-stu-id="ab200-102">Column Null Ratio Profile Request Options (Data Profiling Task)</span></span>
  <span data-ttu-id="ab200-103">Use o painel **Propriedades da Solicitação** da página **Solicitações de Perfil** para definir as opções da **Solicitação de Razão Nula de Coluna** selecionada no painel de solicitações.</span><span class="sxs-lookup"><span data-stu-id="ab200-103">Use the **Request Properties** pane of the **Profile Requests** page to set the options for the **Column Null Ratio Request** selected in the requests pane.</span></span> <span data-ttu-id="ab200-104">O perfil Razão Nula de Coluna informa a porcentagem de valores nulos na coluna selecionada.</span><span class="sxs-lookup"><span data-stu-id="ab200-104">A Column Null Ratio profile reports the percentage of null values in the selected column.</span></span> <span data-ttu-id="ab200-105">Este perfil pode ajudar a identificar problemas em seus dados, como uma inesperada razão alta de valores nulos em uma coluna.</span><span class="sxs-lookup"><span data-stu-id="ab200-105">This profile can help you identify problems in your data such as an unexpectedly high ratio of null values in a column.</span></span> <span data-ttu-id="ab200-106">Por exemplo, um perfil Razão Nula de Coluna pode criar um perfil de uma coluna Código Postal/CEP e descobrir uma porcentagem excessivamente elevada de códigos postais ausentes.</span><span class="sxs-lookup"><span data-stu-id="ab200-106">For example, a Column Null Ratio profile can profile a ZIP Code/Postal Code column and discover an unacceptably high percentage of missing postal codes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ab200-107">As opções descritas neste tópico são exibidas na página **Solicitações de Perfil** do **Editor da Tarefa Criação de Perfil de Dados**.</span><span class="sxs-lookup"><span data-stu-id="ab200-107">The options described in this topic appear on the **Profile Requests page** of the **Data Profiling Task Editor**.</span></span> <span data-ttu-id="ab200-108">Para obter mais informações sobre essa página do editor, consulte [Editor da Tarefa Criação de Perfil de Dados &#40;Página Solicitações de perfil&#41;](data-profiling-task-editor-profile-requests-page.md).</span><span class="sxs-lookup"><span data-stu-id="ab200-108">For more information about this page of the editor, see [Data Profiling Task Editor &#40;Profile Requests Page&#41;](data-profiling-task-editor-profile-requests-page.md).</span></span>  
  
 <span data-ttu-id="ab200-109">Para obter mais informações sobre como usar a Tarefa Criação de Perfil de Dados, consulte [Configuração da Tarefa Criação de Perfil de Dados](data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="ab200-109">For more information about how to use the Data Profiling Task, see [Setup of the Data Profiling Task](data-profiling-task.md).</span></span> <span data-ttu-id="ab200-110">Para obter mais informações sobre como usar o Visualizador de Perfil de Dados para analisar a saída da Tarefa Criação de Perfil de Dados, consulte [Visualizador de Perfil de Dados](data-profile-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="ab200-110">For more information about how to use the Data Profile Viewer to analyze the output of the Data Profiling Task, see [Data Profile Viewer](data-profile-viewer.md).</span></span>  
  
## <a name="request-properties-options"></a><span data-ttu-id="ab200-111">Opções de Propriedades da Solicitação</span><span class="sxs-lookup"><span data-stu-id="ab200-111">Request Properties Options</span></span>  
 <span data-ttu-id="ab200-112">Para uma **Solicitação de Razão Nula de Coluna**, o painel **Propriedades da Solicitação** exibe os seguintes grupos de opções:</span><span class="sxs-lookup"><span data-stu-id="ab200-112">For a **Column Null Ratio Request**, the **Request Properties** pane displays the following groups of options:</span></span>  
  
-   <span data-ttu-id="ab200-113">**Dados**que incluem as opções **TableOrView** e **Column**</span><span class="sxs-lookup"><span data-stu-id="ab200-113">**Data**, which includes the **TableOrView** and **Column** options</span></span>  
  
-   <span data-ttu-id="ab200-114">**Geral**</span><span class="sxs-lookup"><span data-stu-id="ab200-114">**General**</span></span>  
  
### <a name="data-options"></a><span data-ttu-id="ab200-115">Opções de dados</span><span class="sxs-lookup"><span data-stu-id="ab200-115">Data Options</span></span>  
 <span data-ttu-id="ab200-116">**ConnectionManager**</span><span class="sxs-lookup"><span data-stu-id="ab200-116">**ConnectionManager**</span></span>  
 <span data-ttu-id="ab200-117">Selecione o gerenciador de conexões do [!INCLUDE[vstecado](../../includes/vstecado-md.md)] que usa o Provedor de Dados .NET para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) para conexão com o banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que contém a tabela ou a exibição cujo perfil será criado.</span><span class="sxs-lookup"><span data-stu-id="ab200-117">Select the existing [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that uses the.NET Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database that contains the table or view to be profiled.</span></span>  
  
 <span data-ttu-id="ab200-118">**TableOrView**</span><span class="sxs-lookup"><span data-stu-id="ab200-118">**TableOrView**</span></span>  
 <span data-ttu-id="ab200-119">Selecione a tabela ou exibição existente que contêm a coluna para a qual será criado um perfil.</span><span class="sxs-lookup"><span data-stu-id="ab200-119">Select the existing table or view that contains the column to be profiled.</span></span>  
  
 <span data-ttu-id="ab200-120">Para obter mais informações, consulte a seção "Opções TableOrView" neste tópico.</span><span class="sxs-lookup"><span data-stu-id="ab200-120">For more information, see the section, "TableorView Options," in this topic.</span></span>  
  
 <span data-ttu-id="ab200-121">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="ab200-121">**Column**</span></span>  
 <span data-ttu-id="ab200-122">Selecione a coluna existente para a qual um perfil será criado.</span><span class="sxs-lookup"><span data-stu-id="ab200-122">Select the existing column to be profiled.</span></span> <span data-ttu-id="ab200-123">Selecione **(\*)** para analisar todas as colunas.</span><span class="sxs-lookup"><span data-stu-id="ab200-123">Select **(\*)** to profile all columns.</span></span>  
  
 <span data-ttu-id="ab200-124">Para obter mais informações, consulte a seção “Opções Column” neste tópico.</span><span class="sxs-lookup"><span data-stu-id="ab200-124">For more information, see the section, "Column Options," in this topic.</span></span>  
  
#### <a name="tableorview-options"></a><span data-ttu-id="ab200-125">Opções TableOrView</span><span class="sxs-lookup"><span data-stu-id="ab200-125">TableOrView Options</span></span>  
 <span data-ttu-id="ab200-126">**Esquema**</span><span class="sxs-lookup"><span data-stu-id="ab200-126">**Schema**</span></span>  
 <span data-ttu-id="ab200-127">Especifica o esquema ao qual a tabela selecionada pertence.</span><span class="sxs-lookup"><span data-stu-id="ab200-127">Specifies the schema to which the selected table belongs.</span></span> <span data-ttu-id="ab200-128">Esta opção é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="ab200-128">This option is read-only.</span></span>  
  
 <span data-ttu-id="ab200-129">**Table**</span><span class="sxs-lookup"><span data-stu-id="ab200-129">**Table**</span></span>  
 <span data-ttu-id="ab200-130">Exibe o nome da tabela selecionada.</span><span class="sxs-lookup"><span data-stu-id="ab200-130">Displays the name of the selected table.</span></span> <span data-ttu-id="ab200-131">Esta opção é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="ab200-131">This option is read-only.</span></span>  
  
#### <a name="column-options"></a><span data-ttu-id="ab200-132">Opções de Coluna</span><span class="sxs-lookup"><span data-stu-id="ab200-132">Column Options</span></span>  
 <span data-ttu-id="ab200-133">**IsWildCard**</span><span class="sxs-lookup"><span data-stu-id="ab200-133">**IsWildCard**</span></span>  
 <span data-ttu-id="ab200-134">Especifica se o curinga **(\*)** foi selecionado.</span><span class="sxs-lookup"><span data-stu-id="ab200-134">Specifies whether the **(\*)** wildcard has been selected.</span></span> <span data-ttu-id="ab200-135">Esta opção será definida como **True** se você tiver selecionado **(\*)** para analisar todas as colunas.</span><span class="sxs-lookup"><span data-stu-id="ab200-135">This option is set to **True** if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="ab200-136">Será **Falso** se você selecionou uma coluna individual para a criação de um perfil.</span><span class="sxs-lookup"><span data-stu-id="ab200-136">It is **False** if you have selected an individual column to be profiled.</span></span> <span data-ttu-id="ab200-137">Esta opção é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="ab200-137">This option is read-only.</span></span>  
  
 <span data-ttu-id="ab200-138">**ColumnName**</span><span class="sxs-lookup"><span data-stu-id="ab200-138">**ColumnName**</span></span>  
 <span data-ttu-id="ab200-139">Exibe o nome da coluna selecionada.</span><span class="sxs-lookup"><span data-stu-id="ab200-139">Displays the name of the selected column.</span></span> <span data-ttu-id="ab200-140">Esta opção estará em branco se você tiver selecionado **(\*)** para analisar todas as colunas.</span><span class="sxs-lookup"><span data-stu-id="ab200-140">This option is blank if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="ab200-141">Esta opção é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="ab200-141">This option is read-only.</span></span>  
  
 <span data-ttu-id="ab200-142">**StringCompareOptions**</span><span class="sxs-lookup"><span data-stu-id="ab200-142">**StringCompareOptions**</span></span>  
 <span data-ttu-id="ab200-143">Esta opção não é aplicável ao Perfil de Razão Nula de Coluna.</span><span class="sxs-lookup"><span data-stu-id="ab200-143">This option does not apply to the Column Null Ratio Profile.</span></span>  
  
### <a name="general-options"></a><span data-ttu-id="ab200-144">Opções gerais</span><span class="sxs-lookup"><span data-stu-id="ab200-144">General Options</span></span>  
 <span data-ttu-id="ab200-145">**RequestID**</span><span class="sxs-lookup"><span data-stu-id="ab200-145">**RequestID**</span></span>  
 <span data-ttu-id="ab200-146">Digite um nome descritivo para identificar esta solicitação de perfil.</span><span class="sxs-lookup"><span data-stu-id="ab200-146">Type a descriptive name to identify this profile request.</span></span> <span data-ttu-id="ab200-147">Normalmente, não é necessário alterar o valor gerado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ab200-147">Typically, you do not have to change the autogenerated value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab200-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ab200-148">See Also</span></span>  
 <span data-ttu-id="ab200-149">[Editor da tarefa Criação de Perfil de Dados &#40;Página Geral&#41;](../general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="ab200-149">[Data Profiling Task Editor &#40;General Page&#41;](../general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="ab200-150">Formulário de Perfil Rápido de Tabela Única &#40;Tarefa Criação de Perfil de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="ab200-150">Single Table Quick Profile Form &#40;Data Profiling Task&#41;</span></span>](single-table-quick-profile-form-data-profiling-task.md)  
  
  
