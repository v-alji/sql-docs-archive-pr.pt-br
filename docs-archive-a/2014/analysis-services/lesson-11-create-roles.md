---
title: 'Lição 12: criar funções | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 984face4-00fc-46d3-8ae1-9755bf737bdf
author: minewiskan
ms.author: owend
ms.openlocfilehash: 962cd19726a5404de81e20a2209b25b9cc277e21
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568841"
---
# <a name="lesson-12-create-roles"></a><span data-ttu-id="8d069-102">Lição 12: Criar Funções</span><span class="sxs-lookup"><span data-stu-id="8d069-102">Lesson 12: Create Roles</span></span>
  <span data-ttu-id="8d069-103">Nesta lição, você criará funções.</span><span class="sxs-lookup"><span data-stu-id="8d069-103">In this lesson, you will create roles.</span></span> <span data-ttu-id="8d069-104">As funções fornecem objeto de banco de dados modelo e segurança de dados, limitando o acesso somente a esses usuários do Windows, que são os membros da função.</span><span class="sxs-lookup"><span data-stu-id="8d069-104">Roles provide model database object and data security by limiting access to only those Windows users which are role members.</span></span> <span data-ttu-id="8d069-105">Cada função é definida com uma única permissão: Nenhum, Leitura, Leitura e Processo, Processo ou Administrador.</span><span class="sxs-lookup"><span data-stu-id="8d069-105">Each role is defined with a single permission: None, Read, Read and Process, Process, or Administrator.</span></span> <span data-ttu-id="8d069-106">As funções podem ser definidas durante a criação do modelo usando a caixa de diálogo Gerenciador de Funções no [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d069-106">Roles can be defined during model authoring by using the Role Manager dialog box in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span></span> <span data-ttu-id="8d069-107">Depois que um modelo foi implantado, você pode gerenciar funções usando o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d069-107">After a model has been deployed, you can manage roles by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="8d069-108">Para obter mais informações, consulte [Funções &#40;SSAS Tabular&#41;](tabular-models/roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="8d069-108">To learn more, see [Roles &#40;SSAS Tabular&#41;](tabular-models/roles-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8d069-109">A criação de funções não é necessária para concluir este tutorial.</span><span class="sxs-lookup"><span data-stu-id="8d069-109">Creating roles is not necessary to complete this tutorial.</span></span> <span data-ttu-id="8d069-110">Por padrão, a conta com a qual você está conectado terá privilégios de Administrador no modelo.</span><span class="sxs-lookup"><span data-stu-id="8d069-110">By default, the account you are currently logged in with will have Administrator privileges on the model.</span></span> <span data-ttu-id="8d069-111">No entanto, para que outros usuários da organização procurem o modelo usando um aplicativo cliente de relatório, você deve criar pelo menos uma função com permissões Leitura e adicionar esses usuários como membros.</span><span class="sxs-lookup"><span data-stu-id="8d069-111">However, to allow other users in your organization to browse the model by using a reporting client application, you must create at least one role with Read permissions and add those users as members.</span></span>  
  
 <span data-ttu-id="8d069-112">Você criará três funções:</span><span class="sxs-lookup"><span data-stu-id="8d069-112">You will create three roles:</span></span>  
  
-   <span data-ttu-id="8d069-113">Gerente de vendas-essa função pode incluir usuários em sua organização para os quais você deseja ter permissão de leitura para todos os objetos de modelo e dados.</span><span class="sxs-lookup"><span data-stu-id="8d069-113">Sales Manager - This role can include users in your organization for which you want to have Read permission to all model objects and data.</span></span>  
  
-   <span data-ttu-id="8d069-114">Analista de vendas dos EUA-essa função pode incluir usuários em sua organização para os quais você deseja apenas procurar dados relacionados a vendas nos EUA (Estados Unidos).</span><span class="sxs-lookup"><span data-stu-id="8d069-114">Sales Analyst US - This role can include users in your organization for which you want only to be able to browse data related to sales in the US (United States).</span></span> <span data-ttu-id="8d069-115">Para esta função, você usará uma fórmula DAX para definir um *Filtro de Linha*, que restringe os membros procurar somente dados dos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="8d069-115">For this role, you will use a DAX formula to define a *Row Filter*, which restricts members to browse data only for the United States.</span></span>  
  
-   <span data-ttu-id="8d069-116">Administrador – essa função pode incluir os usuários para os quais você deseja ter permissão de administrador, o que permite acesso ilimitado e permissões para executar tarefas administrativas no banco de dados modelo.</span><span class="sxs-lookup"><span data-stu-id="8d069-116">Administrator - This role can include users for which you want to have Administrator permission, which allows unlimited access and permissions to perform administrative tasks on the model database.</span></span>  
  
 <span data-ttu-id="8d069-117">Como o usuário e as contas de grupo do Windows da sua organização são exclusivas, você pode adicionar contas da sua organização específica a membros.</span><span class="sxs-lookup"><span data-stu-id="8d069-117">Because Windows user and group accounts in your organization are unique, you can add accounts from your particular organization to members.</span></span> <span data-ttu-id="8d069-118">Porém, para este tutorial, você também pode deixar os membros em branco.</span><span class="sxs-lookup"><span data-stu-id="8d069-118">However, for this tutorial, you can also leave the members blank.</span></span> <span data-ttu-id="8d069-119">Você ainda poderá testar o efeito de cada função posteriormente na Lição 12: Analisar no Excel.</span><span class="sxs-lookup"><span data-stu-id="8d069-119">You will still be able to test the effect of each role later in Lesson 12: Analyze in Excel.</span></span>  
  
 <span data-ttu-id="8d069-120">Tempo estimado para conclusão desta lição: **15 minutos**</span><span class="sxs-lookup"><span data-stu-id="8d069-120">Estimated time to complete this lesson: **15 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8d069-121">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="8d069-121">Prerequisites</span></span>  
 <span data-ttu-id="8d069-122">Este tópico faz parte de um tutorial de modelagem tabular, que deve ser concluído na devida ordem.</span><span class="sxs-lookup"><span data-stu-id="8d069-122">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="8d069-123">Antes de executar as tarefas desta lição, você deverá ter concluído a lição anterior: [Lição 11: Criar partições](lesson-10-create-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="8d069-123">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 11: Create Partitions](lesson-10-create-partitions.md).</span></span>  
  
## <a name="create-roles"></a><span data-ttu-id="8d069-124">Criar Funções</span><span class="sxs-lookup"><span data-stu-id="8d069-124">Create Roles</span></span>  
  
#### <a name="to-create-a-sales-manager-user-role"></a><span data-ttu-id="8d069-125">Para criar uma função de usuário de Gerente de Vendas</span><span class="sxs-lookup"><span data-stu-id="8d069-125">To create a Sales Manager user role</span></span>  
  
1.  <span data-ttu-id="8d069-126">No [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], clique no menu **Modelo** e em **Funções**.</span><span class="sxs-lookup"><span data-stu-id="8d069-126">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click on the **Model** menu, and then click **Roles**.</span></span>  
  
2.  <span data-ttu-id="8d069-127">Na caixa de diálogo **Gerenciador de Funções** , clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="8d069-127">In the **Role Manager** dialog box, click **New**.</span></span>  
  
     <span data-ttu-id="8d069-128">Uma nova função com a permissão Nenhum é adicionada à lista.</span><span class="sxs-lookup"><span data-stu-id="8d069-128">A new role with the None permission is added to the list.</span></span>  
  
3.  <span data-ttu-id="8d069-129">Clique na nova função e, na coluna **nome** , renomeie a função como `Internet Sales Manager` .</span><span class="sxs-lookup"><span data-stu-id="8d069-129">Click on the new role, and then in the **Name** column, rename the role to `Internet Sales Manager`.</span></span>  
  
4.  <span data-ttu-id="8d069-130">Na coluna **Permissões**, clique na lista suspensa e, em seguida, selecione a permissão **Leitura**.</span><span class="sxs-lookup"><span data-stu-id="8d069-130">In the **Permissions** column, click the dropdown list, and then select the **Read** permission.</span></span>  
  
5.  <span data-ttu-id="8d069-131">Opcional: clique na guia **Membros** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="8d069-131">Optional: Click on the **Members** tab, and then click **Add**.</span></span>  
  
6.  <span data-ttu-id="8d069-132">Na caixa de diálogo **Selecionar Usuários ou Grupos**, digite os grupos os usuários do Windows da sua organização que você deseja incluir na função.</span><span class="sxs-lookup"><span data-stu-id="8d069-132">In the **Select Users or Groups** dialog box, enter the Windows users or groups from your organization you want to include in the role.</span></span>  
  
7.  <span data-ttu-id="8d069-133">Verifique suas seleções e clique em **OK**</span><span class="sxs-lookup"><span data-stu-id="8d069-133">Verify your selections, and then click **OK**</span></span>  
  
#### <a name="to-create-a-sales-analyst-us-user-role"></a><span data-ttu-id="8d069-134">Para criar a função de usuário Analista de Vendas dos EUA</span><span class="sxs-lookup"><span data-stu-id="8d069-134">To create a Sales Analyst US user role</span></span>  
  
1.  <span data-ttu-id="8d069-135">No [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], clique no menu **Modelo** e em **Funções**.</span><span class="sxs-lookup"><span data-stu-id="8d069-135">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click on the **Model** menu, and then click **Roles**.</span></span>  
  
2.  <span data-ttu-id="8d069-136">Na caixa de diálogo **Gerenciador de Funções** , clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="8d069-136">In the **Role Manager** dialog box, click **New**.</span></span>  
  
     <span data-ttu-id="8d069-137">Uma nova função com a permissão Nenhum é adicionada à lista.</span><span class="sxs-lookup"><span data-stu-id="8d069-137">A new role with the None permission is added to the list.</span></span>  
  
3.  <span data-ttu-id="8d069-138">Clique na nova função e, na coluna **nome** , renomeie a função como `Internet Sales US` .</span><span class="sxs-lookup"><span data-stu-id="8d069-138">Click on the new role, and then in the **Name** column, rename the role to `Internet Sales US`.</span></span>  
  
4.  <span data-ttu-id="8d069-139">Na coluna **Permissões**, clique na lista suspensa e, em seguida, selecione a permissão **Leitura**.</span><span class="sxs-lookup"><span data-stu-id="8d069-139">In the **Permissions** column, click the dropdown list, and then select the **Read** permission.</span></span>  
  
5.  <span data-ttu-id="8d069-140">Clique na guia Filtros de Linha e somente para a tabela **Geografia** , na coluna Filtro DAX, digite a seguinte fórmula:</span><span class="sxs-lookup"><span data-stu-id="8d069-140">Click on the Row Filters tab, and then for the **Geography** table only, in the DAX Filter column, type the following formula:</span></span>  
  
     `=Geography[Country Region Code] = "US"`  
  
     <span data-ttu-id="8d069-141">Uma fórmula de Filtro de Linha deve ser resolvida para um valor booliano (TRUE/FALSE).</span><span class="sxs-lookup"><span data-stu-id="8d069-141">A Row Filter formula must resolve to a Boolean (TRUE/FALSE) value.</span></span> <span data-ttu-id="8d069-142">Com essa fórmula, você está especificando que somente as linhas com o valor de código do país Region de "US" fiquem visíveis para o usuário.</span><span class="sxs-lookup"><span data-stu-id="8d069-142">With this formula, you are specifying that only rows with the Country Region Code value of "US" be visible to the user.</span></span>  
  
     <span data-ttu-id="8d069-143">Ao concluir a criação da fórmula, pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="8d069-143">When you have finished building the formula, press ENTER.</span></span>  
  
6.  <span data-ttu-id="8d069-144">Opcional: clique na guia **Membros** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="8d069-144">Optional: Click on the **Members** tab, and then click **Add**.</span></span>  
  
7.  <span data-ttu-id="8d069-145">Na caixa de diálogo **Selecionar Usuários ou Grupos**, digite os grupos os usuários do Windows da sua organização que você deseja incluir na função.</span><span class="sxs-lookup"><span data-stu-id="8d069-145">In the **Select Users or Groups** dialog box, enter the Windows users or groups from your organization you want to include in the role.</span></span>  
  
8.  <span data-ttu-id="8d069-146">Verifique suas seleções e clique em **OK**</span><span class="sxs-lookup"><span data-stu-id="8d069-146">Verify your selections, and then click **OK**</span></span>  
  
#### <a name="to-create-an-administrator-role"></a><span data-ttu-id="8d069-147">Para criar uma função de Administrador</span><span class="sxs-lookup"><span data-stu-id="8d069-147">To create an Administrator role</span></span>  
  
1.  <span data-ttu-id="8d069-148">Na caixa de diálogo **Gerenciador de Funções** , clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="8d069-148">In the **Role Manager** dialog box, click **New**.</span></span>  
  
2.  <span data-ttu-id="8d069-149">Clique na nova função e, na coluna **nome** , renomeie a função como `Internet Sales Administrator` .</span><span class="sxs-lookup"><span data-stu-id="8d069-149">Click on the new role, and then in the **Name** column, rename the role to `Internet Sales Administrator`.</span></span>  
  
3.  <span data-ttu-id="8d069-150">Na coluna **Permissões** , clique na lista suspensa e selecione a permissão **Administrador** .</span><span class="sxs-lookup"><span data-stu-id="8d069-150">In the **Permissions** column, click the dropdown list, and then select the **Administrator** permission.</span></span>  
  
4.  <span data-ttu-id="8d069-151">Clique na guia **Membros** e em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="8d069-151">Click on the **Members** tab, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="8d069-152">Opcional: na caixa de diálogo **Selecionar Usuários ou Grupos** , digite os usuários ou grupos do Windows de sua organização a serem incluídos na função.</span><span class="sxs-lookup"><span data-stu-id="8d069-152">Optional: In the **Select Users or Groups** dialog box, enter the Windows users or groups from your organization you want to include in the role.</span></span>  
  
6.  <span data-ttu-id="8d069-153">Verifique suas seleções e clique em **OK**</span><span class="sxs-lookup"><span data-stu-id="8d069-153">Verify your selections, and then click **OK**</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8d069-154">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="8d069-154">Next Steps</span></span>  
 <span data-ttu-id="8d069-155">Para continuar este tutorial, vá para a próxima lição: [Lição 13: Analisar no Excel](lesson-12-analyze-in-excel.md).</span><span class="sxs-lookup"><span data-stu-id="8d069-155">To continue this tutorial, go to the next lesson: Lesson: [Lesson 13: Analyze in Excel](lesson-12-analyze-in-excel.md).</span></span>  
  
  
