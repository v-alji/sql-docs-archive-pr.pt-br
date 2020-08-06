---
title: Criar e gerenciar funções (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.rolemanager.f1
- sql12.asvs.bidtoolset.roledb.f1
ms.assetid: e23d27a8-e968-4082-9dbe-963fc724b5d9
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 335e0e311d97ea452449cd0c5d6550f6dbcca4f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570299"
---
# <a name="create-and-manage-roles-ssas-tabular"></a><span data-ttu-id="c6ef7-102">Criar e Gerenciar Funções (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="c6ef7-102">Create and Manage Roles (SSAS Tabular)</span></span>
  <span data-ttu-id="c6ef7-103">Funções, em modelos tabulares, definem permissões de membro para um modelo.</span><span class="sxs-lookup"><span data-stu-id="c6ef7-103">Roles, in tabular models, define member permissions for a model.</span></span> <span data-ttu-id="c6ef7-104">As funções são definidas para um projeto de modelo usando a caixa de diálogo Gerenciador de Funções no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6ef7-104">Roles are defined for a model project by using the Role Manager dialog box in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="c6ef7-105">Quando um modelo é implantado, os administradores de banco de dados podem gerenciar funções usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6ef7-105">When a model is deployed, database administrators can manage roles by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="c6ef7-106">As tarefas neste tópico descrevem como criar e gerenciar funções durante a criação do modelo usando a caixa de diálogo Gerenciador de Funções no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6ef7-106">The tasks in this topic describe how to create and manage roles during model authoring by using the Role Manager dialog box in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="c6ef7-107">Para obter informações sobre como gerenciar as funções em um modelo de banco de dados implantado, consulte [Funções de modelo tabular &#40;SSAS Tabular&#41;](roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="c6ef7-107">For information about managing roles in a deployed model database, see [Tabular Model Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md).</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="c6ef7-108">Tarefas</span><span class="sxs-lookup"><span data-stu-id="c6ef7-108">Tasks</span></span>  
 <span data-ttu-id="c6ef7-109">Para criar, editar, copiar e excluir funções, você usará a caixa de diálogo **Gerenciador de Funções** .</span><span class="sxs-lookup"><span data-stu-id="c6ef7-109">To create, edit, copy, and delete roles, you will use the **Role Manager** dialog box.</span></span> <span data-ttu-id="c6ef7-110">Para exibir a caixa de diálogo **Gerenciador de Funções** , no [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], clique no menu **Modelo** e em **Gerenciador de Funções**.</span><span class="sxs-lookup"><span data-stu-id="c6ef7-110">To view the **Role Manager** dialog box, in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, and then click **Role Manager**.</span></span>  
  
###  <a name="to-create-a-new-role"></a><a name="bkmk_new_role"></a> <span data-ttu-id="c6ef7-111">Para criar uma nova função</span><span class="sxs-lookup"><span data-stu-id="c6ef7-111">To create a new role</span></span>  
  
1.  <span data-ttu-id="c6ef7-112">No [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], clique no menu **Modelo** e em **Gerenciador de Funções**.</span><span class="sxs-lookup"><span data-stu-id="c6ef7-112">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, and then click **Role Manager**.</span></span>  
  
2.  <span data-ttu-id="c6ef7-113">Na caixa de diálogo **Gerenciador de Funções** , clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c6ef7-113">In the **Role Manager** dialog box, click **New**.</span></span>  
  
     <span data-ttu-id="c6ef7-114">Uma nova função realçada é adicionada à lista de Funções.</span><span class="sxs-lookup"><span data-stu-id="c6ef7-114">A new highlighted role is added to the Roles list.</span></span>  
  
3.  <span data-ttu-id="c6ef7-115">Na lista de **Funções** , no campo **Nome** , digite um nome para a função.</span><span class="sxs-lookup"><span data-stu-id="c6ef7-115">In the **Roles** list, in the **Name** field, type a name for the role.</span></span>  
  
     <span data-ttu-id="c6ef7-116">Por padrão, o nome da função padrão será numerado incrementalmente para cada nova função.</span><span class="sxs-lookup"><span data-stu-id="c6ef7-116">By default, the name of the default role will be incrementally numbered for each new role.</span></span> <span data-ttu-id="c6ef7-117">É recomendado que você digite um nome que claramente identifique o tipo de membro, por exemplo, Gerentes Financeiros ou Especialistas de Recursos Humanos.</span><span class="sxs-lookup"><span data-stu-id="c6ef7-117">It is recommended you type a name that clearly identifies the member type, for example, Finance Managers or Human Resources Specialists.</span></span>  
  
4.  <span data-ttu-id="c6ef7-118">No campo **Permissões** , clique na seta para baixo e selecione um dos tipos de permissão a seguir:</span><span class="sxs-lookup"><span data-stu-id="c6ef7-118">In the **Permissions** field, click the down arrow and then select one of the following permission types:</span></span>  
  
    |<span data-ttu-id="c6ef7-119">Permissão</span><span class="sxs-lookup"><span data-stu-id="c6ef7-119">Permission</span></span>|<span data-ttu-id="c6ef7-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="c6ef7-120">Description</span></span>|  
    |----------------|-----------------|  
    |<span data-ttu-id="c6ef7-121">**Nenhuma**</span><span class="sxs-lookup"><span data-stu-id="c6ef7-121">**None**</span></span>|<span data-ttu-id="c6ef7-122">Os membros não podem fazer modificações ao esquema modelo e não podem consultar dados.</span><span class="sxs-lookup"><span data-stu-id="c6ef7-122">Members cannot make any modifications to the model schema and cannot query data.</span></span>|  
    |<span data-ttu-id="c6ef7-123">**Ler**</span><span class="sxs-lookup"><span data-stu-id="c6ef7-123">**Read**</span></span>|<span data-ttu-id="c6ef7-124">Os membros têm permissão de consultar dados (com base em filtros de linha) mas não podem fazer nenhuma alteração ao esquema modelo.</span><span class="sxs-lookup"><span data-stu-id="c6ef7-124">Members are allowed to query data (based on row filters) but cannot make any changes to the model schema.</span></span>|  
    |<span data-ttu-id="c6ef7-125">**Leitura e processo**</span><span class="sxs-lookup"><span data-stu-id="c6ef7-125">**Read and Process**</span></span>|<span data-ttu-id="c6ef7-126">Os membros têm permissão de consultar dados (com base em filtros de nível de linha) e executar operações de Processar e Processar Tudo, mas não podem fazer nenhuma alteração ao esquema modelo.</span><span class="sxs-lookup"><span data-stu-id="c6ef7-126">Members are allowed to query data (based on row-level filters) and run Process and Process All operations, but cannot make any changes to the model schema.</span></span>|  
    |<span data-ttu-id="c6ef7-127">**Processo**</span><span class="sxs-lookup"><span data-stu-id="c6ef7-127">**Process**</span></span>|<span data-ttu-id="c6ef7-128">Membros podem executar operações de Processar e Processar Tudo.</span><span class="sxs-lookup"><span data-stu-id="c6ef7-128">Members can run Process and Process All operations.</span></span> <span data-ttu-id="c6ef7-129">Não é possível modificar o esquema modelo e não é possível consultar dados.</span><span class="sxs-lookup"><span data-stu-id="c6ef7-129">Cannot modify the model schema and cannot query data.</span></span>|  
    |<span data-ttu-id="c6ef7-130">**Administrador**</span><span class="sxs-lookup"><span data-stu-id="c6ef7-130">**Administrator**</span></span>|<span data-ttu-id="c6ef7-131">Os membros podem fazer modificações ao esquema modelo e podem consultar todos os dados.</span><span class="sxs-lookup"><span data-stu-id="c6ef7-131">Members can make modifications to the model schema and can query all data.</span></span>|  
  
5.  <span data-ttu-id="c6ef7-132">Para inserir uma descrição para a função, clique no campo **Descrição** e digite uma descrição.</span><span class="sxs-lookup"><span data-stu-id="c6ef7-132">To enter a description for the role, click the **Description** field, and then type a description.</span></span>  
  
6.  <span data-ttu-id="c6ef7-133">Se a função que você está criando tem permissão de Leitura ou Leitura e Processamento, você pode adicionar filtros de linha usando uma fórmula DAX.</span><span class="sxs-lookup"><span data-stu-id="c6ef7-133">If the role you are creating has Read or Read and Process permission, you can add row filters using a DAX formula.</span></span> <span data-ttu-id="c6ef7-134">Para adicionar filtros de linha, clique na guia **Filtros de Linha** , selecione uma tabela, clique no campo **Filtro DAX** e digite uma fórmula DAX.</span><span class="sxs-lookup"><span data-stu-id="c6ef7-134">To add row filters, click the **Row Filters** tab, then select a table, then click the **DAX Filter** field, and then type a DAX formula.</span></span>  
  
7.  <span data-ttu-id="c6ef7-135">Para adicionar membros à função, clique na guia **Membros** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c6ef7-135">To add members to the role, click the **Members** tab, and then click **Add**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c6ef7-136">Os membros de função também podem ser adicionados a um modelo implantado usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6ef7-136">Role members can also be added to a deployed model by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="c6ef7-137">Para obter mais informações, consulte [Gerenciar funções usando SSMS &#40;SSAS Tabular&#41;](manage-roles-by-using-ssms-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="c6ef7-137">For more information, see [Manage Roles by using SSMS &#40;SSAS Tabular&#41;](manage-roles-by-using-ssms-ssas-tabular.md).</span></span>  
  
8.  <span data-ttu-id="c6ef7-138">Na caixa de diálogo **Selecionar Usuários ou Grupos** , insira os objetos usuário do Windows ou grupo do Windows como membros.</span><span class="sxs-lookup"><span data-stu-id="c6ef7-138">In the **Select Users or Groups** dialog box, enter Windows user or Windows group objects as members.</span></span>  
  
9. <span data-ttu-id="c6ef7-139">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6ef7-139">Click **Ok**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6ef7-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c6ef7-140">See Also</span></span>  
 <span data-ttu-id="c6ef7-141">[Funções &#40;SSAS de tabela&#41;](roles-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="c6ef7-141">[Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md) </span></span>  
 <span data-ttu-id="c6ef7-142">[Perspectivas &#40;SSAS de tabela&#41;](perspectives-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="c6ef7-142">[Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md) </span></span>  
 <span data-ttu-id="c6ef7-143">[Analisar no Excel &#40;SSAS de tabela&#41;](analyze-in-excel-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="c6ef7-143">[Analyze in Excel &#40;SSAS Tabular&#41;](analyze-in-excel-ssas-tabular.md) </span></span>  
 <span data-ttu-id="c6ef7-144">[Função de nome de usuário &#40;DAX&#41;](/dax/username-function-dax) </span><span class="sxs-lookup"><span data-stu-id="c6ef7-144">[USERNAME Function &#40;DAX&#41;](/dax/username-function-dax) </span></span>  
 [<span data-ttu-id="c6ef7-145">Função CUSTOMDATA &#40;DAX&#41;</span><span class="sxs-lookup"><span data-stu-id="c6ef7-145">CUSTOMDATA Function &#40;DAX&#41;</span></span>](/dax/customdata-function-dax)  
  
  
