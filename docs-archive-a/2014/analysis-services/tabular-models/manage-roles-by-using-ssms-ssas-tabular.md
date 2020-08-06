---
title: Gerenciar funções usando o SSMS (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 652faac0-1cfc-438b-8119-2f4b090a2381
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4ee34d5e75d5d4ce3679d46d29af3215852d2bbe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679018"
---
# <a name="manage-roles-by-using-ssms-ssas-tabular"></a><span data-ttu-id="3ba78-102">Gerenciar funções usando SSMS (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="3ba78-102">Manage Roles by using SSMS (SSAS Tabular)</span></span>
  <span data-ttu-id="3ba78-103">Você pode criar, editar e gerenciar funções para um modelo de tabela implantado usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ba78-103">You can create, edit, and manage roles for a deployed tabular model by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="3ba78-104">Tarefas neste tópico:</span><span class="sxs-lookup"><span data-stu-id="3ba78-104">Tasks in this topic:</span></span>  
  
-   [<span data-ttu-id="3ba78-105">Para criar uma nova função</span><span class="sxs-lookup"><span data-stu-id="3ba78-105">To create a new role</span></span>](#bkmk_new_role)  
  
-   [<span data-ttu-id="3ba78-106">Para copiar uma função</span><span class="sxs-lookup"><span data-stu-id="3ba78-106">To copy a role</span></span>](#bkmk_copy_role)  
  
-   [<span data-ttu-id="3ba78-107">Para editar uma função</span><span class="sxs-lookup"><span data-stu-id="3ba78-107">To edit a role</span></span>](#bkmk_edit_role)  
  
-   [<span data-ttu-id="3ba78-108">Para excluir uma função</span><span class="sxs-lookup"><span data-stu-id="3ba78-108">To delete a role</span></span>](#bkmk_deletet_role)  
  
> [!CAUTION]  
>  <span data-ttu-id="3ba78-109">Reimplantar um projeto de modelo de tabela com funções definidas usando o Gerenciador de Função no [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] substituirá as funções definidas em um modelo de tabela implantado.</span><span class="sxs-lookup"><span data-stu-id="3ba78-109">Re-deploying a tabular model project with roles defined by using Role Manager in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] will overwrite roles defined in a deployed tabular model.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="3ba78-110">Usar o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para gerenciar um banco de dados de workspace de modelo de tabela enquanto o projeto de modelo está aberto no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] pode corromper o arquivo Model.bim.</span><span class="sxs-lookup"><span data-stu-id="3ba78-110">Using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to manage a tabular model workspace database while the model project is open in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] may cause the Model.bim file to become corrupted.</span></span> <span data-ttu-id="3ba78-111">Ao criar e gerenciar funções para um banco de dados de workspace de modelo de tabela, use o Gerenciador de Função no [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ba78-111">When creating and managing roles for a tabular model workspace database, use Role Manager in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
###  <a name="to-create-a-new-role"></a><a name="bkmk_new_role"></a> <span data-ttu-id="3ba78-112">Para criar uma nova função</span><span class="sxs-lookup"><span data-stu-id="3ba78-112">To create a new role</span></span>  
  
1.  <span data-ttu-id="3ba78-113">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expanda o modelo de banco de dados de tabela para o qual você quer criar uma nova função, clique com o botão direito do mouse em **Funções**e, em seguida, clique em **Nova Função**.</span><span class="sxs-lookup"><span data-stu-id="3ba78-113">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the tabular model database for which you want to create a new role, then right click on **Roles**, and then click **New Role**.</span></span>  
  
2.  <span data-ttu-id="3ba78-114">Na caixa de diálogo **Criar Função** , na janela Selecionar uma página, clique em **Geral**.</span><span class="sxs-lookup"><span data-stu-id="3ba78-114">In the **Create Role** dialog box, in the Select a page window, click **General**.</span></span>  
  
3.  <span data-ttu-id="3ba78-115">Na janela de configurações gerais, no campo **Nome** , digite um nome para a função.</span><span class="sxs-lookup"><span data-stu-id="3ba78-115">In the general settings window, in the **Name** field, type a name for the role.</span></span>  
  
     <span data-ttu-id="3ba78-116">Por padrão, o nome da função padrão será numerado incrementalmente para cada nova função.</span><span class="sxs-lookup"><span data-stu-id="3ba78-116">By default, the name of the default role will be incrementally numbered for each new role.</span></span> <span data-ttu-id="3ba78-117">É recomendado que você digite um nome que claramente identifique o tipo de membro, por exemplo, Gerentes Financeiros ou Especialistas de Recursos Humanos.</span><span class="sxs-lookup"><span data-stu-id="3ba78-117">It is recommended you type a name that clearly identifies the member type, for example, Finance Managers or Human Resources Specialists.</span></span>  
  
4.  <span data-ttu-id="3ba78-118">Em **Defina as permissões de banco de dados para essa função**, selecione uma das opções de permissão a seguir:</span><span class="sxs-lookup"><span data-stu-id="3ba78-118">In **Set the database permissions for this role**, select one of the following permissions options:</span></span>  
  
    |<span data-ttu-id="3ba78-119">Permissão</span><span class="sxs-lookup"><span data-stu-id="3ba78-119">Permission</span></span>|<span data-ttu-id="3ba78-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="3ba78-120">Description</span></span>|  
    |----------------|-----------------|  
    |<span data-ttu-id="3ba78-121">**Controle total (Administrador)**</span><span class="sxs-lookup"><span data-stu-id="3ba78-121">**Full control (Administrator)**</span></span>|<span data-ttu-id="3ba78-122">Os membros podem fazer modificações ao esquema modelo e podem exibir todos os dados.</span><span class="sxs-lookup"><span data-stu-id="3ba78-122">Members can make modifications to the model schema and can view all data.</span></span>|  
    |<span data-ttu-id="3ba78-123">**Processar Banco de Dados**</span><span class="sxs-lookup"><span data-stu-id="3ba78-123">**Process database**</span></span>|<span data-ttu-id="3ba78-124">Membros podem executar operações de Processar e Processar Tudo.</span><span class="sxs-lookup"><span data-stu-id="3ba78-124">Members can run Process and Process All operations.</span></span> <span data-ttu-id="3ba78-125">Não é possível modificar o esquema modelo e não é possível exibir dados.</span><span class="sxs-lookup"><span data-stu-id="3ba78-125">Cannot modify the model schema and cannot view data.</span></span>|  
    |<span data-ttu-id="3ba78-126">**Ler**</span><span class="sxs-lookup"><span data-stu-id="3ba78-126">**Read**</span></span>|<span data-ttu-id="3ba78-127">Os membros têm permissão de exibir dados (com base em filtros de linha) mas não podem fazer nenhuma alteração ao esquema modelo.</span><span class="sxs-lookup"><span data-stu-id="3ba78-127">Members are allowed to view data (based on row filters) but cannot make any changes to the model schema.</span></span>|  
  
5.  <span data-ttu-id="3ba78-128">Na caixa de diálogo **Criar Função** , na janela Selecionar uma página, clique em **Associação**.</span><span class="sxs-lookup"><span data-stu-id="3ba78-128">In the **Create Role** dialog box, in the Select a page window, click **Membership**.</span></span>  
  
6.  <span data-ttu-id="3ba78-129">Na janela de configurações de associação, clique em **Adicionar**e, na caixa de diálogo **Selecionar Usuários ou Grupos** , adicione os usuários ou grupos do Windows que você deseja adicionar como membros.</span><span class="sxs-lookup"><span data-stu-id="3ba78-129">In the membership settings window, click **Add**, and then in the **Select Users or Groups** dialog box, add the Windows users or groups you want to add as members.</span></span>  
  
7.  <span data-ttu-id="3ba78-130">Se a função que você está criando tem permissões de Leitura, você pode adicionar filtros de linha para qualquer tabela usando uma fórmula DAX.</span><span class="sxs-lookup"><span data-stu-id="3ba78-130">If the role you are creating has Read permissions, you can add row filters for any table using a DAX formula.</span></span> <span data-ttu-id="3ba78-131">Para adicionar filtros de linha, na caixa de diálogo **Propriedades \<rolename> da função** , em **selecionar uma página**, clique em **filtros de linha**.</span><span class="sxs-lookup"><span data-stu-id="3ba78-131">To add row filters, in the **Role Properties - \<rolename>** dialog box, in **Select a page**, click on **Row Filters**.</span></span>  
  
8.  <span data-ttu-id="3ba78-132">Na janela filtros de linha, selecione uma tabela, clique no campo **filtro Dax** e, em seguida, no campo \*\* \<tablename> filtro Dax\*\* , digite uma fórmula DAX.</span><span class="sxs-lookup"><span data-stu-id="3ba78-132">In the row filters window, select a table, then click on the **DAX Filter** field, and then in the **DAX Filter - \<tablename>** field, type a DAX formula.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3ba78-133">O campo filtro DAX não \<tablename> contém um editor de consulta de preenchimento automático ou recurso de função INSERT.</span><span class="sxs-lookup"><span data-stu-id="3ba78-133">The DAX Filter - \<tablename> field does not contain an AutoComplete query editor or insert function feature.</span></span> <span data-ttu-id="3ba78-134">Para usar o Preenchimento Automático ao escrever uma fórmula DAX, você deverá usar um editor de fórmula DAX no [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ba78-134">To use AutoComplete when writing a DAX formula, you must use a DAX formula editor in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
9. <span data-ttu-id="3ba78-135">Clique em **OK** para salvar a função.</span><span class="sxs-lookup"><span data-stu-id="3ba78-135">Click **Ok** to save the role.</span></span>  
  
###  <a name="to-copy-a-role"></a><a name="bkmk_copy_role"></a> <span data-ttu-id="3ba78-136">Para copiar uma função</span><span class="sxs-lookup"><span data-stu-id="3ba78-136">To copy a role</span></span>  
  
1.  <span data-ttu-id="3ba78-137">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expanda o modelo de banco de dados de tabela que contém a função que você deseja copiar, expanda **Funções**e, em seguida, clique com o botão direito do mouse na função e clique em **Duplicar**.</span><span class="sxs-lookup"><span data-stu-id="3ba78-137">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the tabular model database that contains the role you want to copy, then expand **Roles**, then right click on the role, and then click **Duplicate**.</span></span>  
  
###  <a name="to-edit-a-role"></a><a name="bkmk_edit_role"></a><span data-ttu-id="3ba78-138">Para editar uma função</span><span class="sxs-lookup"><span data-stu-id="3ba78-138">To edit a role</span></span>  
  
-   <span data-ttu-id="3ba78-139">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expanda o modelo de banco de dados de tabela que contém a função que você deseja editar, expanda **Funções**e, em seguida, clique com o botão direito do mouse na função e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="3ba78-139">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the tabular model database that contains the role you want to edit, then expand **Roles**, then right click on the role, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="3ba78-140">Na caixa de diálogo **Propriedades da função** \<rolename> , você pode alterar permissões, adicionar ou remover membros e adicionar/editar filtros de linha.</span><span class="sxs-lookup"><span data-stu-id="3ba78-140">In the **Role Properties** \<rolename> dialog box, you can change permissions, add or remove members, and add/edit row filters.</span></span>  
  
###  <a name="to-delete-a-role"></a><a name="bkmk_deletet_role"></a><span data-ttu-id="3ba78-141">Para excluir uma função</span><span class="sxs-lookup"><span data-stu-id="3ba78-141">To delete a role</span></span>  
  
-   <span data-ttu-id="3ba78-142">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expanda o modelo de banco de dados de tabela que contém a função que você deseja excluir, expanda **Funções**e, em seguida, clique com o botão direito do mouse na função e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="3ba78-142">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the tabular model database that contains the role you want to delete, then expand **Roles**, then right click on the role, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ba78-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3ba78-143">See Also</span></span>  
 [<span data-ttu-id="3ba78-144">Funções &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="3ba78-144">Roles &#40;SSAS Tabular&#41;</span></span>](roles-ssas-tabular.md)  
  
  
