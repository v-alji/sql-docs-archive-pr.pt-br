---
title: Analisar no Excel (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2f17b4df-eea2-48c7-a1f2-a3fb7748c15f
author: minewiskan
ms.author: owend
ms.openlocfilehash: ad46515f5710fa7e46b0beb8b3133e925973293a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572719"
---
# <a name="analyze-in-excel-ssas-tabular"></a><span data-ttu-id="bef1d-102">Analisar no Excel (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="bef1d-102">Analyze in Excel (SSAS Tabular)</span></span>
  <span data-ttu-id="bef1d-103">O recurso Analisar no Excel, no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], fornece a autores de modelos de tabela um modo de analisar projetos de modelo rapidamente durante o desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="bef1d-103">The Analyze in Excel feature, in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], provides tabular model authors a way to quickly analyze model projects during development.</span></span> <span data-ttu-id="bef1d-104">O recurso Analisar no Excel abre o Microsoft Excel, cria uma conexão da fonte de dados para o banco de dados de workspace modelo e automaticamente adiciona uma Tabela Dinâmica à planilha.</span><span class="sxs-lookup"><span data-stu-id="bef1d-104">The Analyze in Excel feature opens Microsoft Excel, creates a data source connection to the model workspace database, and automatically adds a PivotTable to the worksheet.</span></span> <span data-ttu-id="bef1d-105">Os objetos de banco de dados de workspace (tabelas, colunas e medidas) são incluídos como campos na Lista de campos da Tabela Dinâmica.</span><span class="sxs-lookup"><span data-stu-id="bef1d-105">Workspace database objects (tables, columns, and measures) are included as fields in the PivotTable Field List.</span></span> <span data-ttu-id="bef1d-106">Os objetos e os dados podem então ser exibidos dentro do contexto do usuário efetivo ou função e perspectiva.</span><span class="sxs-lookup"><span data-stu-id="bef1d-106">Objects and data can then be viewed within the context of the effective user or role and perspective.</span></span>  
  
 <span data-ttu-id="bef1d-107">Este tópico pressupõe que você já esteja familiarizado com o Microsoft Excel, Tabelas Dinâmicas e Gráficos Dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="bef1d-107">This topic assumes you are already familiar with Microsoft Excel, PivotTables, and PivotCharts.</span></span> <span data-ttu-id="bef1d-108">Para saber mais sobre o uso do Excel, consulte a Ajuda do Excel.</span><span class="sxs-lookup"><span data-stu-id="bef1d-108">To learn more about using Excel, see Excel Help.</span></span>  
  
 <span data-ttu-id="bef1d-109">Seções neste tópico:</span><span class="sxs-lookup"><span data-stu-id="bef1d-109">Sections in this topic:</span></span>  
  
-   [<span data-ttu-id="bef1d-110">Benefícios</span><span class="sxs-lookup"><span data-stu-id="bef1d-110">Benefits</span></span>](#bkmk_benefits)  
  
-   [<span data-ttu-id="bef1d-111">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="bef1d-111">Related Tasks</span></span>](#bkmk_rt)  
  
##  <a name="benefits"></a><a name="bkmk_benefits"></a> <span data-ttu-id="bef1d-112">Benefícios</span><span class="sxs-lookup"><span data-stu-id="bef1d-112">Benefits</span></span>  
 <span data-ttu-id="bef1d-113">O recurso Analisar no Excel fornece aos autores de modelo a capacidade para testar a eficácia de um projeto de modelo usando o aplicativo comum de análise de dados, Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="bef1d-113">The Analyze in Excel feature provides model authors the ability to test the efficacy of a model project by using the common data analysis application, Microsoft Excel.</span></span> <span data-ttu-id="bef1d-114">Para usar o recurso Analisar no Excel, você deve ter o Microsoft Office 2003 ou superior instalado no mesmo computador que o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bef1d-114">In order to use the Analyze in Excel feature, you must have Microsoft Office 2003 or later installed on the same computer as [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bef1d-115">Se o Office não estiver instalado no mesmo computador como [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], você poderá usar o Excel em outro computador para conectar-se ao banco de dados de workspace como uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="bef1d-115">If Office is not installed on the same computer as [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], you can use Excel on another computer to connect to the workspace database as a data source.</span></span> <span data-ttu-id="bef1d-116">Você pode então adicionar manualmente uma Tabela Dinâmica à planilha.</span><span class="sxs-lookup"><span data-stu-id="bef1d-116">You can then manually add a PivotTable to the worksheet.</span></span>  
  
 <span data-ttu-id="bef1d-117">O recurso Analisar no Excel abre o Excel e cria uma nova pasta de trabalho do Excel (.xls).</span><span class="sxs-lookup"><span data-stu-id="bef1d-117">The Analyze in Excel feature opens Excel and creates a new Excel workbook (.xls).</span></span> <span data-ttu-id="bef1d-118">Uma conexão de dados da pasta de trabalho para o banco de dados de workspace modelo é criada.</span><span class="sxs-lookup"><span data-stu-id="bef1d-118">A data connection from the workbook to the model workspace database is created.</span></span> <span data-ttu-id="bef1d-119">Uma Tabela Dinâmica em branco é adicionada à planilha e os metadados de objeto modelo são populados na lista de Campo de Tabela Dinâmica.</span><span class="sxs-lookup"><span data-stu-id="bef1d-119">A blank PivotTable is added to the worksheet and model object metadata is populated in the PivotTable Field list.</span></span> <span data-ttu-id="bef1d-120">Você pode então adicionar dados visíveis e segmentações de dados à Tabela Dinâmica.</span><span class="sxs-lookup"><span data-stu-id="bef1d-120">You can then add viewable data and slicers to the PivotTable.</span></span>  
  
 <span data-ttu-id="bef1d-121">Ao usar o recurso Analisar no Excel, por padrão, a conta de usuário atualmente conectada é o usuário efetivo.</span><span class="sxs-lookup"><span data-stu-id="bef1d-121">When using the Analyze in Excel feature, by default, the user account currently logged on is the effective user.</span></span> <span data-ttu-id="bef1d-122">Esta conta é geralmente um Administrador sem restrições de exibição para objetos modelo ou dados.</span><span class="sxs-lookup"><span data-stu-id="bef1d-122">This account is typically an Administrator with no view restrictions to model objects or data.</span></span> <span data-ttu-id="bef1d-123">Porém, você pode especificar um nome de usuário ou função efetivo diferente.</span><span class="sxs-lookup"><span data-stu-id="bef1d-123">You can, however, specify a different effective username or role.</span></span> <span data-ttu-id="bef1d-124">Isto permite que você navegue em um projeto de modelo no Excel dentro do contexto de um usuário ou função específico.</span><span class="sxs-lookup"><span data-stu-id="bef1d-124">This allows you to browse a model project in Excel within the context of a specific user or role.</span></span> <span data-ttu-id="bef1d-125">Especificar o usuário efetivo inclui as opções a seguir:</span><span class="sxs-lookup"><span data-stu-id="bef1d-125">Specifying the effective user includes the following options:</span></span>  
  
 <span data-ttu-id="bef1d-126">**Usuário do Windows atual**</span><span class="sxs-lookup"><span data-stu-id="bef1d-126">**Current Windows User**</span></span>  
 <span data-ttu-id="bef1d-127">Usa a conta de usuário com a qual você está conectado atualmente.</span><span class="sxs-lookup"><span data-stu-id="bef1d-127">Uses the user account with which you are currently logged on.</span></span>  
  
 <span data-ttu-id="bef1d-128">**Outro usuário do Windows**</span><span class="sxs-lookup"><span data-stu-id="bef1d-128">**Other Windows User**</span></span>  
 <span data-ttu-id="bef1d-129">Usa um nome de usuário do Windows especificado em vez do usuário conectado atualmente.</span><span class="sxs-lookup"><span data-stu-id="bef1d-129">Uses a specified Windows username rather than the user currently logged on.</span></span> <span data-ttu-id="bef1d-130">Usar um usuário do Windows diferente não exige uma senha.</span><span class="sxs-lookup"><span data-stu-id="bef1d-130">Using a different Windows user does not require a password.</span></span> <span data-ttu-id="bef1d-131">Os objetos e os dados podem somente ser exibidos no Excel dentro do contexto do nome do usuário efetivo.</span><span class="sxs-lookup"><span data-stu-id="bef1d-131">Objects and data can only be viewed in Excel within the context of the effective username.</span></span> <span data-ttu-id="bef1d-132">Nenhuma alteração a objetos modelo ou dados pode ser feita no Excel.</span><span class="sxs-lookup"><span data-stu-id="bef1d-132">No changes to model objects or data can be made in Excel.</span></span>  
  
 <span data-ttu-id="bef1d-133">**Função**</span><span class="sxs-lookup"><span data-stu-id="bef1d-133">**Role**</span></span>  
 <span data-ttu-id="bef1d-134">Uma função é usada para definir permissões de usuário nos metadados de objeto e nos dados.</span><span class="sxs-lookup"><span data-stu-id="bef1d-134">A role is used to define user permissions on the object metadata and data.</span></span> <span data-ttu-id="bef1d-135">As funções são normalmente definidas para um usuário ou grupo de usuário do Windows específico.</span><span class="sxs-lookup"><span data-stu-id="bef1d-135">Roles are usually defined for a particular Windows user or Windows user group.</span></span> <span data-ttu-id="bef1d-136">Determinadas funções podem incluir filtros em nível de linha adicionais definidos em uma fórmula DAX.</span><span class="sxs-lookup"><span data-stu-id="bef1d-136">Certain roles can include additional row-level filters defined in a DAX formula.</span></span> <span data-ttu-id="bef1d-137">Ao usar o recurso Analisar no Excel, você pode opcionalmente selecionar uma função a ser usada.</span><span class="sxs-lookup"><span data-stu-id="bef1d-137">When using the Analyze in Excel feature, you can optionally select a role to be used.</span></span> <span data-ttu-id="bef1d-138">Os metadados de objeto e as exibições de dados serão restringidas pela permissão e pelos filtros definidos para a função.</span><span class="sxs-lookup"><span data-stu-id="bef1d-138">Object metadata and data views will be restricted by the permission and filters defined for the role.</span></span> <span data-ttu-id="bef1d-139">Para obter mais informações, consulte [Criar e gerenciar funções &#40;SSAS de Tabela&#41;](roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="bef1d-139">For more information, see [Create and Manage Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="bef1d-140">Além do usuário efetivo ou função, você pode especificar uma perspectiva.</span><span class="sxs-lookup"><span data-stu-id="bef1d-140">In addition to the effective user or role, you can specify a perspective.</span></span> <span data-ttu-id="bef1d-141">As perspectivas permitem que os autores do modelo definam exibições de cenário comerciais específicas de objetos modelo e dados.</span><span class="sxs-lookup"><span data-stu-id="bef1d-141">Perspectives enable model authors to define particular business scenario views of model objects and data.</span></span> <span data-ttu-id="bef1d-142">Por padrão, nenhuma perspectiva é usada.</span><span class="sxs-lookup"><span data-stu-id="bef1d-142">By default, no perspective is used.</span></span> <span data-ttu-id="bef1d-143">Para usar uma perspectiva com o Analisar no Excel, as perspectivas já devem ser definidas usando a caixa de diálogo Perspectivas no [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bef1d-143">In order to use a perspective with Analyze in Excel, perspectives must already be defined by using the Perspectives dialog box in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span> <span data-ttu-id="bef1d-144">Se uma perspectiva for especificada, a Lista de campos da Tabela Dinâmica conterá somente esses objetos selecionados na perspectiva.</span><span class="sxs-lookup"><span data-stu-id="bef1d-144">If a perspective is specified, the PivotTable Field List will contain only those objects selected in the perspective.</span></span> <span data-ttu-id="bef1d-145">Para obter mais informações, consulte [criar e gerenciar perspectivas &#40;SSAS&#41;de tabela ](perspectives-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="bef1d-145">For more information, see [Create and Manage Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="bkmk_rt"></a> <span data-ttu-id="bef1d-146">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="bef1d-146">Related Tasks</span></span>  
  
|<span data-ttu-id="bef1d-147">**Tópico**</span><span class="sxs-lookup"><span data-stu-id="bef1d-147">**Topic**</span></span>|<span data-ttu-id="bef1d-148">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="bef1d-148">**Description**</span></span>|  
|---------------|---------------------|  
|[<span data-ttu-id="bef1d-149">Analisar um modelo de tabela no Excel &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="bef1d-149">Analyze a Tabular Model in Excel &#40;SSAS Tabular&#41;</span></span>](analyze-a-tabular-model-in-excel-ssas-tabular.md)|<span data-ttu-id="bef1d-150">Esse tópico descreve como usar o recurso Analisar no Excel no designer de modelo para abrir o Excel, criar uma conexão da fonte de dados para o banco de dados de workspace modelo e adicionar uma Tabela Dinâmica à planilha.</span><span class="sxs-lookup"><span data-stu-id="bef1d-150">This topic describes how to use the Analyze in Excel feature in the model designer to open Excel, create a data source connection to the model workspace database, and add a PivotTable to the worksheet.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bef1d-151">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bef1d-151">See Also</span></span>  
 <span data-ttu-id="bef1d-152">[Analisar um modelo de tabela no Excel &#40;SSAS de tabela&#41;](analyze-a-tabular-model-in-excel-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="bef1d-152">[Analyze a Tabular Model in Excel &#40;SSAS Tabular&#41;](analyze-a-tabular-model-in-excel-ssas-tabular.md) </span></span>  
 <span data-ttu-id="bef1d-153">[Funções &#40;SSAS de tabela&#41;](roles-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="bef1d-153">[Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="bef1d-154">Perspectivas &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="bef1d-154">Perspectives &#40;SSAS Tabular&#41;</span></span>](perspectives-ssas-tabular.md)  
  
  