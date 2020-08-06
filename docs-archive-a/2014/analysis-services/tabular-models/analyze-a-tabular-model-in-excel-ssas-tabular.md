---
title: Analisar um modelo de tabela no Excel (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.chooseperspect.f1
ms.assetid: 47fa45fc-60ab-41a1-bde3-5781c8462889
author: minewiskan
ms.author: owend
ms.openlocfilehash: fae542ffb5b470d23d9cf27fcc11367f571e7cec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581474"
---
# <a name="analyze-a-tabular-model-in-excel-ssas-tabular"></a><span data-ttu-id="e8617-102">Analisar um modelo tabular no Excel (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="e8617-102">Analyze a Tabular Model in Excel (SSAS Tabular)</span></span>
  <span data-ttu-id="e8617-103">O recurso Analisar no Excel no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] abre o Microsoft Excel, cria uma conexão da fonte de dados para o banco de dados de workspace modelo e adiciona uma Tabela Dinâmica à planilha.</span><span class="sxs-lookup"><span data-stu-id="e8617-103">The Analyze in Excel feature in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] opens Microsoft Excel, creates a data source connection to the model workspace database, and adds a PivotTable to the worksheet.</span></span> <span data-ttu-id="e8617-104">Os objetos de modelo (tabelas, colunas, medidas, hierarquias e KPIs) são incluídos como campos na lista de campos da Tabela Dinâmica.</span><span class="sxs-lookup"><span data-stu-id="e8617-104">Model objects (tables, columns, measures, hierarchies, and KPIs) are included as fields in the PivotTable field list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e8617-105">Para usar o recurso Analisar no Excel, você deve ter o Microsoft Office 2003 ou superior instalado no mesmo computador que o [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8617-105">To use the Analyze in Excel feature, you must have Microsoft Office 2003 or later installed on the same computer as [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span> <span data-ttu-id="e8617-106">Se o Office não estiver instalado no mesmo computador, você poderá usar o Excel em outro computador e conectar-se ao banco de dados de workspace do modelo como uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="e8617-106">If Office is not installed on the same computer, you can use Excel on another computer and connect to the model workspace database as a data source.</span></span> <span data-ttu-id="e8617-107">Você pode então adicionar manualmente uma Tabela Dinâmica à planilha.</span><span class="sxs-lookup"><span data-stu-id="e8617-107">You can then manually add a PivotTable to the worksheet.</span></span> <span data-ttu-id="e8617-108">Os objetos de modelo (tabelas, colunas, medidas e KPIs) são incluídos como campos na lista de campos da Tabela Dinâmica.</span><span class="sxs-lookup"><span data-stu-id="e8617-108">Model objects (tables, columns, measures, and KPIs) are included as fields in the PivotTable field list.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="e8617-109">Tarefas</span><span class="sxs-lookup"><span data-stu-id="e8617-109">Tasks</span></span>  
  
#### <a name="to-analyze-a-tabular-model-project-by-using-the-analyze-in-excel-feature"></a><span data-ttu-id="e8617-110">Para analisar um projeto de modelo tabular usando o recurso Analisar no Excel</span><span class="sxs-lookup"><span data-stu-id="e8617-110">To analyze a tabular model project by using the Analyze in Excel feature</span></span>  
  
1.  <span data-ttu-id="e8617-111">No [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], clique no menu **Modelo** e em **Analisar no Excel**.</span><span class="sxs-lookup"><span data-stu-id="e8617-111">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, and then click **Analyze in Excel**.</span></span>  
  
2.  <span data-ttu-id="e8617-112">Na caixa de diálogo **Escolher Credencial e Perspectiva**, selecione uma das opções de credencial a seguir para conectar-se à fonte de dados de workspace modelo:</span><span class="sxs-lookup"><span data-stu-id="e8617-112">In the **Choose Credential and Perspective** dialog box, select one of the following credential options to connect to the model workspace data source:</span></span>  
  
    -   <span data-ttu-id="e8617-113">Para usar a conta de usuário atual, selecione **Usuário atual do Windows**.</span><span class="sxs-lookup"><span data-stu-id="e8617-113">To use the current user account, select **Current Windows User**.</span></span>  
  
    -   <span data-ttu-id="e8617-114">Para usar uma conta de usuário diferente, selecione **Outro Usuário do Windows**.</span><span class="sxs-lookup"><span data-stu-id="e8617-114">To use a different user account, select **Other Windows User**.</span></span>  
  
         <span data-ttu-id="e8617-115">Normalmente, esta conta de usuário será membro de uma função.</span><span class="sxs-lookup"><span data-stu-id="e8617-115">Typically, this user account will be a member of a role.</span></span> <span data-ttu-id="e8617-116">Nenhuma senha é necessária.</span><span class="sxs-lookup"><span data-stu-id="e8617-116">No password is required.</span></span> <span data-ttu-id="e8617-117">A conta só pode ser usada no contexto de uma conexão do Excel com o banco de dados de workspace.</span><span class="sxs-lookup"><span data-stu-id="e8617-117">The account can only be used in the context of an Excel connection to the workspace database.</span></span>  
  
    -   <span data-ttu-id="e8617-118">Para usar uma função de segurança, selecione **Função**e, na caixa de listagem, selecione uma ou mais funções.</span><span class="sxs-lookup"><span data-stu-id="e8617-118">To use a security role, select **Role**, and then in the listbox, select one or more roles.</span></span>  
  
         <span data-ttu-id="e8617-119">As funções de segurança devem ser definidas usando o Gerenciador de Função.</span><span class="sxs-lookup"><span data-stu-id="e8617-119">Security roles must be defined using the Role Manager.</span></span> <span data-ttu-id="e8617-120">Para obter mais informações, consulte [Criar e gerenciar funções &#40;SSAS de Tabela&#41;](roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="e8617-120">For more information, see [Create and Manage Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md).</span></span>  
  
3.  <span data-ttu-id="e8617-121">Para usar uma perspectiva, na caixa de listagem **Perspectiva** , selecione uma perspectiva.</span><span class="sxs-lookup"><span data-stu-id="e8617-121">To use a perspective, in the **Perspective** listbox, select a perspective.</span></span>  
  
     <span data-ttu-id="e8617-122">As perspectivas (além das padrão) devem ser definidas usando a caixa de diálogo Perspectivas.</span><span class="sxs-lookup"><span data-stu-id="e8617-122">Perspectives (other than default) must be defined using the Perspectives dialog box.</span></span> <span data-ttu-id="e8617-123">Para obter mais informações, consulte [criar e gerenciar perspectivas &#40;SSAS&#41;de tabela ](perspectives-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="e8617-123">For more information, see [Create and Manage Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e8617-124">A Lista de campos Tabela Dinâmica no Excel não é atualizada automaticamente à medida que você faz alterações no projeto de modelo no designer modelo.</span><span class="sxs-lookup"><span data-stu-id="e8617-124">The PivotTable Field List in Excel does not refresh automatically as you make changes to the model project in the model designer.</span></span> <span data-ttu-id="e8617-125">Para atualizar a Lista de campos de Tabela Dinâmica, no Excel, na faixa de opções **Opções** , clique em **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="e8617-125">To refresh the PivotTable Field List, in Excel, on the **Options** ribbon, click **Refresh**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8617-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e8617-126">See Also</span></span>  
 [<span data-ttu-id="e8617-127">Analisar no Excel &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="e8617-127">Analyze in Excel &#40;SSAS Tabular&#41;</span></span>](analyze-in-excel-ssas-tabular.md)  
  
  
