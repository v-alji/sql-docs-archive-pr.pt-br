---
title: Opções da solicitação do perfil Estatísticas de Coluna (tarefa Criação de Perfil de Dados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Data Profiling Task Editor
ms.assetid: 87205984-507a-49f3-b27c-36a0075c234d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9ce5c062a12e38d147f3cef95ea09b4c80f7c256
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573235"
---
# <a name="column-statistics-profile-request-options-data-profiling-task"></a><span data-ttu-id="32adf-102">Opções da solicitação do perfil Estatísticas de Coluna (tarefa Criação de Perfil de Dados)</span><span class="sxs-lookup"><span data-stu-id="32adf-102">Column Statistics Profile Request Options (Data Profiling Task)</span></span>
  <span data-ttu-id="32adf-103">Use o painel **Propriedades da Solicitação** da página **Solicitações de Perfil** para definir as opções da **Solicitação de Perfil de Estatísticas de Coluna** selecionada no painel de solicitações.</span><span class="sxs-lookup"><span data-stu-id="32adf-103">Use the **Request Properties** pane of the **Profile Requests** page to set the options for the **Column Statistics Profile Request** selected in the requests pane.</span></span> <span data-ttu-id="32adf-104">Um perfil de Estatísticas de Coluna informa estatísticas como mínimo, máximo, média e desvio padrão para colunas numéricas, além de mínimo e máximo para colunas `datetime`.</span><span class="sxs-lookup"><span data-stu-id="32adf-104">A Column Statistics profile reports statistics such as minimum, maximum, average, and standard deviation for numeric columns, and minimum and maximum for `datetime` columns.</span></span> <span data-ttu-id="32adf-105">Este perfil pode ajudá-lo a identificar problemas em seus dados, como datas inválidas.</span><span class="sxs-lookup"><span data-stu-id="32adf-105">This profile can help you identify problems in your data such as invalid dates.</span></span> <span data-ttu-id="32adf-106">Por exemplo, você cria o perfil de uma coluna de datas de histórico e descobre uma data máxima no futuro.</span><span class="sxs-lookup"><span data-stu-id="32adf-106">For example, you profile a column of historical dates and discover a maximum date that is in the future.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="32adf-107">As opções descritas neste tópico são exibidas na página **Solicitações de Perfil** do **Editor da Tarefa Criação de Perfil de Dados**.</span><span class="sxs-lookup"><span data-stu-id="32adf-107">The options described in this topic appear on the **Profile Requests page** of the **Data Profiling Task Editor**.</span></span> <span data-ttu-id="32adf-108">Para obter mais informações sobre essa página do editor, consulte [Editor da Tarefa Criação de Perfil de Dados &#40;Página Solicitações de perfil&#41;](data-profiling-task-editor-profile-requests-page.md).</span><span class="sxs-lookup"><span data-stu-id="32adf-108">For more information about this page of the editor, see [Data Profiling Task Editor &#40;Profile Requests Page&#41;](data-profiling-task-editor-profile-requests-page.md).</span></span>  
  
 <span data-ttu-id="32adf-109">Para obter mais informações sobre como usar a Tarefa Criação de Perfil de Dados, consulte [Configuração da Tarefa Criação de Perfil de Dados](data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="32adf-109">For more information about how to use the Data Profiling Task, see [Setup of the Data Profiling Task](data-profiling-task.md).</span></span> <span data-ttu-id="32adf-110">Para obter mais informações sobre como usar o Visualizador de Perfil de Dados para analisar a saída da Tarefa Criação de Perfil de Dados, consulte [Visualizador de Perfil de Dados](data-profile-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="32adf-110">For more information about how to use the Data Profile Viewer to analyze the output of the Data Profiling Task, see [Data Profile Viewer](data-profile-viewer.md).</span></span>  
  
## <a name="request-properties-options"></a><span data-ttu-id="32adf-111">Opções de Propriedades da Solicitação</span><span class="sxs-lookup"><span data-stu-id="32adf-111">Request Properties Options</span></span>  
 <span data-ttu-id="32adf-112">Para uma **Solicitação de Perfil de Estatísticas de Coluna**, o painel **Propriedades da Solicitação** exibe os seguintes grupos de opções:</span><span class="sxs-lookup"><span data-stu-id="32adf-112">For a **Column Statistics Profile Request**, the **Request Properties** pane displays the following groups of options:</span></span>  
  
-   <span data-ttu-id="32adf-113">**Dados**que incluem as opções **TableOrView** e **Column**</span><span class="sxs-lookup"><span data-stu-id="32adf-113">**Data**, which includes the **TableOrView** and **Column** options</span></span>  
  
-   <span data-ttu-id="32adf-114">**Geral**</span><span class="sxs-lookup"><span data-stu-id="32adf-114">**General**</span></span>  
  
### <a name="data-options"></a><span data-ttu-id="32adf-115">Opções de dados</span><span class="sxs-lookup"><span data-stu-id="32adf-115">Data Options</span></span>  
 <span data-ttu-id="32adf-116">**ConnectionManager**</span><span class="sxs-lookup"><span data-stu-id="32adf-116">**ConnectionManager**</span></span>  
 <span data-ttu-id="32adf-117">Selecione o gerente de conexões do [!INCLUDE[vstecado](../../includes/vstecado-md.md)] que usa o Provedor de Dados .NET para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) para conexão com o banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que contém a tabela ou a exibição que você deseja analisar.</span><span class="sxs-lookup"><span data-stu-id="32adf-117">Select the existing [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that uses the .NET Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database that contains the table or view to be profiled.</span></span>  
  
 <span data-ttu-id="32adf-118">**TableOrView**</span><span class="sxs-lookup"><span data-stu-id="32adf-118">**TableOrView**</span></span>  
 <span data-ttu-id="32adf-119">Selecione a tabela ou exibição existente que contêm a coluna para a qual será criado um perfil.</span><span class="sxs-lookup"><span data-stu-id="32adf-119">Select the existing table or view that contains the column to be profiled.</span></span>  
  
 <span data-ttu-id="32adf-120">Para obter mais informações, consulte a seção "Opções TableOrView" neste tópico.</span><span class="sxs-lookup"><span data-stu-id="32adf-120">For more information, see the section, "TableorView Options," in this topic.</span></span>  
  
 <span data-ttu-id="32adf-121">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="32adf-121">**Column**</span></span>  
 <span data-ttu-id="32adf-122">Selecione a coluna existente para a qual um perfil será criado.</span><span class="sxs-lookup"><span data-stu-id="32adf-122">Select the existing column to be profiled.</span></span> <span data-ttu-id="32adf-123">Selecione **(\*)** para analisar todas as colunas.</span><span class="sxs-lookup"><span data-stu-id="32adf-123">Select **(\*)** to profile all columns.</span></span>  
  
 <span data-ttu-id="32adf-124">Para obter mais informações, consulte a seção “Opções Column” neste tópico.</span><span class="sxs-lookup"><span data-stu-id="32adf-124">For more information, see the section, "Column Options," in this topic.</span></span>  
  
#### <a name="tableorview-options"></a><span data-ttu-id="32adf-125">Opções TableOrView</span><span class="sxs-lookup"><span data-stu-id="32adf-125">TableOrView Options</span></span>  
 <span data-ttu-id="32adf-126">**Esquema**</span><span class="sxs-lookup"><span data-stu-id="32adf-126">**Schema**</span></span>  
 <span data-ttu-id="32adf-127">Especifica o esquema ao qual a tabela selecionada pertence.</span><span class="sxs-lookup"><span data-stu-id="32adf-127">Specifies the schema to which the selected table belongs.</span></span> <span data-ttu-id="32adf-128">Esta opção é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="32adf-128">This option is read-only.</span></span>  
  
 <span data-ttu-id="32adf-129">**Table**</span><span class="sxs-lookup"><span data-stu-id="32adf-129">**Table**</span></span>  
 <span data-ttu-id="32adf-130">Exibe o nome da tabela selecionada.</span><span class="sxs-lookup"><span data-stu-id="32adf-130">Displays the name of the selected table.</span></span> <span data-ttu-id="32adf-131">Esta opção é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="32adf-131">This option is read-only.</span></span>  
  
#### <a name="column-options"></a><span data-ttu-id="32adf-132">Opções de Coluna</span><span class="sxs-lookup"><span data-stu-id="32adf-132">Column Options</span></span>  
 <span data-ttu-id="32adf-133">**IsWildCard**</span><span class="sxs-lookup"><span data-stu-id="32adf-133">**IsWildCard**</span></span>  
 <span data-ttu-id="32adf-134">Especifica se o curinga **(\*)** foi selecionado.</span><span class="sxs-lookup"><span data-stu-id="32adf-134">Specifies whether the **(\*)** wildcard has been selected.</span></span> <span data-ttu-id="32adf-135">Esta opção será definida como **True** se você tiver selecionado **(\*)** para analisar todas as colunas.</span><span class="sxs-lookup"><span data-stu-id="32adf-135">This option is set to **True** if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="32adf-136">Será **Falso** se você selecionou uma coluna individual para a criação de um perfil.</span><span class="sxs-lookup"><span data-stu-id="32adf-136">It is **False** if you have selected an individual column to be profiled.</span></span> <span data-ttu-id="32adf-137">Esta opção é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="32adf-137">This option is read-only.</span></span>  
  
 <span data-ttu-id="32adf-138">**ColumnName**</span><span class="sxs-lookup"><span data-stu-id="32adf-138">**ColumnName**</span></span>  
 <span data-ttu-id="32adf-139">Exibe o nome da coluna selecionada.</span><span class="sxs-lookup"><span data-stu-id="32adf-139">Displays the name of the selected column.</span></span> <span data-ttu-id="32adf-140">Esta opção estará em branco se você tiver selecionado **(\*)** para analisar todas as colunas.</span><span class="sxs-lookup"><span data-stu-id="32adf-140">This option is blank if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="32adf-141">Esta opção é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="32adf-141">This option is read-only.</span></span>  
  
 <span data-ttu-id="32adf-142">**StringCompareOptions**</span><span class="sxs-lookup"><span data-stu-id="32adf-142">**StringCompareOptions**</span></span>  
 <span data-ttu-id="32adf-143">Esta opção não é aplicável ao Perfil de Estatísticas de Coluna.</span><span class="sxs-lookup"><span data-stu-id="32adf-143">This option does not apply to the Column Statistics Profile.</span></span>  
  
### <a name="general-options"></a><span data-ttu-id="32adf-144">Opções gerais</span><span class="sxs-lookup"><span data-stu-id="32adf-144">General Options</span></span>  
 <span data-ttu-id="32adf-145">**RequestID**</span><span class="sxs-lookup"><span data-stu-id="32adf-145">**RequestID**</span></span>  
 <span data-ttu-id="32adf-146">Digite um nome descritivo para identificar esta solicitação de perfil.</span><span class="sxs-lookup"><span data-stu-id="32adf-146">Type a descriptive name to identify this profile request.</span></span> <span data-ttu-id="32adf-147">Normalmente, não é necessário alterar o valor gerado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="32adf-147">Typically, you do not have to change the autogenerated value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32adf-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="32adf-148">See Also</span></span>  
 <span data-ttu-id="32adf-149">[Editor da tarefa Criação de Perfil de Dados &#40;Página Geral&#41;](../general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="32adf-149">[Data Profiling Task Editor &#40;General Page&#41;](../general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="32adf-150">Formulário de Perfil Rápido de Tabela Única &#40;Tarefa Criação de Perfil de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="32adf-150">Single Table Quick Profile Form &#40;Data Profiling Task&#41;</span></span>](single-table-quick-profile-form-data-profiling-task.md)  
  
  
