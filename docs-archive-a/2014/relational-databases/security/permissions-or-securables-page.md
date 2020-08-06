---
title: Página Permissões ou Protegíveis | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.common.permissions.f1
- sql12.swb.SecurableAndEffectPermissions.f1
- sql12.swb.availabilitygroupproperties.permission.f1
- sql12.swb.common.columnperm.f1
- sql12.swb.SecurableAndEffectivePermission.f1
ms.assetid: b3bf077a-bec2-4161-ac0c-460586199906
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 80417c720258833850f07eb67f83f5c47f487ad2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679791"
---
# <a name="permissions-or-securables-page"></a><span data-ttu-id="6a71a-102">Página Permissões ou Protegíveis</span><span class="sxs-lookup"><span data-stu-id="6a71a-102">Permissions or Securables Page</span></span>
  <span data-ttu-id="6a71a-103">Use a página **Permissões** ou a página **Protegíveis** para exibir ou definir as permissões para protegíveis.</span><span class="sxs-lookup"><span data-stu-id="6a71a-103">Use the **Permissions** page or the **Securables** page to view or set the permissions for securables.</span></span> <span data-ttu-id="6a71a-104">Essa página pode ser aberta de muitos locais.</span><span class="sxs-lookup"><span data-stu-id="6a71a-104">This page can be opened from many locations.</span></span> <span data-ttu-id="6a71a-105">O conteúdo da página pode ser ligeiramente alterado, dependendo de como a página é aberta e do que contém.</span><span class="sxs-lookup"><span data-stu-id="6a71a-105">The contents of the page can change slightly, depending on how the page is opened and what it contains.</span></span> <span data-ttu-id="6a71a-106">A grade na parte superior da página pode estar populada quando a página é aberta ou pode estar vazia.</span><span class="sxs-lookup"><span data-stu-id="6a71a-106">The top grid of the page might be populated when the page opens, or it might be empty.</span></span> <span data-ttu-id="6a71a-107">Para adicionar itens à grade superior, clique em **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="6a71a-107">To add items to the upper grid, click **Search**.</span></span> <span data-ttu-id="6a71a-108">Na grade superior, selecione um item e, depois, defina as permissões apropriadas na guia **Explícita** . Para exibir as permissões adicionadas, use a guia **Efetiva** .</span><span class="sxs-lookup"><span data-stu-id="6a71a-108">In the upper grid, select an item, and then set the appropriate permissions on the **Explicit** tab. To view aggregated permissions, use the **Effective** tab.</span></span>  
  
 <span data-ttu-id="6a71a-109">Para entender as combinações possíveis de protegíveis e as entidades, confira os links de sintaxe específica de protegíveis no tópico [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6a71a-109">To understand the possible combinations of securables and principals, see the securable-specific syntax links in the topic [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span></span> <span data-ttu-id="6a71a-110">Para obter mais informações, consulte [Securables](securables.md).</span><span class="sxs-lookup"><span data-stu-id="6a71a-110">For more information, see [Securables](securables.md).</span></span>  
  
## <a name="page-header"></a><span data-ttu-id="6a71a-111">Cabeçalho de página</span><span class="sxs-lookup"><span data-stu-id="6a71a-111">Page Header</span></span>  
 <span data-ttu-id="6a71a-112">O cabeçalho da página **Permissões** ou **Protegíveis** varia, dependendo do protegível ou entidade.</span><span class="sxs-lookup"><span data-stu-id="6a71a-112">The header of the **Permissions** or **Securables** page varies depending on the securable or principal.</span></span> <span data-ttu-id="6a71a-113">Ele exibe informações pertinentes ao item, como seu nome.</span><span class="sxs-lookup"><span data-stu-id="6a71a-113">It displays information relevant to the item, such as its name.</span></span>  
  
## <a name="upper-grid"></a><span data-ttu-id="6a71a-114">Grade superior</span><span class="sxs-lookup"><span data-stu-id="6a71a-114">Upper Grid</span></span>  
 <span data-ttu-id="6a71a-115">A grade superior contém um ou mais itens para os quais podem ser definidas permissões.</span><span class="sxs-lookup"><span data-stu-id="6a71a-115">The upper grid contains one or more items for which permissions can be set.</span></span> <span data-ttu-id="6a71a-116">Essa caixa de diálogo fornece o botão **Pesquisar** para selecionar objetos ou entidades a serem adicionados à grade superior.</span><span class="sxs-lookup"><span data-stu-id="6a71a-116">This dialog box provides the **Search** button for selecting objects or principals to add to the upper grid.</span></span> <span data-ttu-id="6a71a-117">O nome da grade pode exibir **Protegíveis** ou um ou mais tipos de protegíveis ou entidades.</span><span class="sxs-lookup"><span data-stu-id="6a71a-117">The name of the grid might display **Securables** or one or more types of securables or principals.</span></span> <span data-ttu-id="6a71a-118">As colunas que são exibidas na grade superior variam, dependendo da entidade ou protegível.</span><span class="sxs-lookup"><span data-stu-id="6a71a-118">The columns that are displayed in the upper grid vary depending on the principal or securable.</span></span>  
  
 <span data-ttu-id="6a71a-119">**Nome**</span><span class="sxs-lookup"><span data-stu-id="6a71a-119">**Name**</span></span>  
 <span data-ttu-id="6a71a-120">O nome de cada entidade ou protegível que é adicionado à grade.</span><span class="sxs-lookup"><span data-stu-id="6a71a-120">The name of each principal or securable that is added to the grid.</span></span>  
  
 <span data-ttu-id="6a71a-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6a71a-121">**Type**</span></span>  
 <span data-ttu-id="6a71a-122">Descreve o tipo de cada item.</span><span class="sxs-lookup"><span data-stu-id="6a71a-122">Describes the type of each item.</span></span>  
  
## <a name="explicit-tab"></a><span data-ttu-id="6a71a-123">Guia Explícita</span><span class="sxs-lookup"><span data-stu-id="6a71a-123">Explicit Tab</span></span>  
 <span data-ttu-id="6a71a-124">A guia **Explícita** lista as permissões possíveis para o protegível que está selecionado na grade superior.</span><span class="sxs-lookup"><span data-stu-id="6a71a-124">The **Explicit** tab lists the possible permissions for the securable that are selected in the upper grid.</span></span> <span data-ttu-id="6a71a-125">Para configurar permissões, marque ou desmarque as caixas de seleção **Conceder** (ou **Permitir**), **Com Concessão**e **Negar** .</span><span class="sxs-lookup"><span data-stu-id="6a71a-125">To configure the permissions, select or clear the **Grant** (or **Allow**), **With Grant**, and **Deny** check boxes.</span></span> <span data-ttu-id="6a71a-126">Nem todas as opções estão disponíveis para todas as permissões explícitas.</span><span class="sxs-lookup"><span data-stu-id="6a71a-126">All options are not available for all explicit permissions.</span></span>  
  
 <span data-ttu-id="6a71a-127">**Permissões**</span><span class="sxs-lookup"><span data-stu-id="6a71a-127">**Permissions**</span></span>  
 <span data-ttu-id="6a71a-128">O nome da permissão.</span><span class="sxs-lookup"><span data-stu-id="6a71a-128">The name of the permission.</span></span>  
  
 <span data-ttu-id="6a71a-129">**Concessor**</span><span class="sxs-lookup"><span data-stu-id="6a71a-129">**Grantor**</span></span>  
 <span data-ttu-id="6a71a-130">A entidade que concedeu a permissão.</span><span class="sxs-lookup"><span data-stu-id="6a71a-130">The principal that granted the permission.</span></span>  
  
 <span data-ttu-id="6a71a-131">**Conceder**</span><span class="sxs-lookup"><span data-stu-id="6a71a-131">**Grant**</span></span>  
 <span data-ttu-id="6a71a-132">Selecione para conceder essa permissão ao logon.</span><span class="sxs-lookup"><span data-stu-id="6a71a-132">Select to grant this permission to the login.</span></span> <span data-ttu-id="6a71a-133">Desmarque para revogar essa permissão.</span><span class="sxs-lookup"><span data-stu-id="6a71a-133">Clear to revoke this permission.</span></span>  
  
 <span data-ttu-id="6a71a-134">**Com Concessão**</span><span class="sxs-lookup"><span data-stu-id="6a71a-134">**With Grant**</span></span>  
 <span data-ttu-id="6a71a-135">Reflete o estado da opção WITH GRANT para a permissão listada.</span><span class="sxs-lookup"><span data-stu-id="6a71a-135">Reflects the state of the WITH GRANT option for the listed permission.</span></span> <span data-ttu-id="6a71a-136">Essa caixa é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="6a71a-136">This box is read-only.</span></span> <span data-ttu-id="6a71a-137">Para aplicar essa permissão, use a instrução [GRANT](/sql/t-sql/statements/grant-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="6a71a-137">To apply this permission, use the [GRANT](/sql/t-sql/statements/grant-transact-sql) statement.</span></span>  
  
 <span data-ttu-id="6a71a-138">**Deny**</span><span class="sxs-lookup"><span data-stu-id="6a71a-138">**Deny**</span></span>  
 <span data-ttu-id="6a71a-139">Selecione para negar essa permissão ao logon.</span><span class="sxs-lookup"><span data-stu-id="6a71a-139">Select to deny this permission to the login.</span></span> <span data-ttu-id="6a71a-140">Desmarque para revogar essa permissão.</span><span class="sxs-lookup"><span data-stu-id="6a71a-140">Clear to revoke this permission.</span></span>  
  
 <span data-ttu-id="6a71a-141">**Permissões de Coluna**</span><span class="sxs-lookup"><span data-stu-id="6a71a-141">**Column Permissions**</span></span>  
 <span data-ttu-id="6a71a-142">Para objetos que contêm colunas (como tabelas, exibições ou funções com valor de tabela), o botão **Permissões de Coluna** abre a caixa de diálogo **Permissões de Coluna** .</span><span class="sxs-lookup"><span data-stu-id="6a71a-142">For objects that contain columns (such as tables, views, or table-valued functions), the **Column Permissions** button opens the **Column Permissions** dialog box.</span></span> <span data-ttu-id="6a71a-143">Nessa caixa de diálogo, você pode definir **Conceder**, **Permitir**ou **Negar** permissões em colunas individuais de uma tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="6a71a-143">In this dialog box, you can set **Grant**, **Allow**, or **Deny** permissions on individual columns of a table or view.</span></span> <span data-ttu-id="6a71a-144">Essa opção não está disponível para todos os tipos de objeto ou permissões.</span><span class="sxs-lookup"><span data-stu-id="6a71a-144">This option is not available for all object types or permissions.</span></span>  
  
## <a name="effective-tab"></a><span data-ttu-id="6a71a-145">Guia Efetiva</span><span class="sxs-lookup"><span data-stu-id="6a71a-145">Effective Tab</span></span>  
 <span data-ttu-id="6a71a-146">As permissões que uma entidade tem associadas a um protegível podem vir das permissões que são definidas para diversas entidades diferentes.</span><span class="sxs-lookup"><span data-stu-id="6a71a-146">The permissions that a principal has related to a securable may come from permissions that are set for several different principals.</span></span> <span data-ttu-id="6a71a-147">Por exemplo, um logon pode receber permissões individualmente e também como um membro de um grupo.</span><span class="sxs-lookup"><span data-stu-id="6a71a-147">For example, a login might be granted permissions individually and also as a member of a group.</span></span> <span data-ttu-id="6a71a-148">A guia **Efetiva** mostra o resultado da combinação de permissões explícitas e das permissões que são recebidas pela associação a um grupo ou função.</span><span class="sxs-lookup"><span data-stu-id="6a71a-148">The **Effective** tab shows the result of combining explicit permissions and the permissions that are received from group or role memberships.</span></span> <span data-ttu-id="6a71a-149">As permissões concedidas são agregadas.</span><span class="sxs-lookup"><span data-stu-id="6a71a-149">Grant permissions are aggregated.</span></span> <span data-ttu-id="6a71a-150">Uma negação de permissão substitui todas as concessões de permissões.</span><span class="sxs-lookup"><span data-stu-id="6a71a-150">A deny permission overrides all grant permissions.</span></span>  
  
 <span data-ttu-id="6a71a-151">**Permissões**</span><span class="sxs-lookup"><span data-stu-id="6a71a-151">**Permissions**</span></span>  
 <span data-ttu-id="6a71a-152">O nome da permissão.</span><span class="sxs-lookup"><span data-stu-id="6a71a-152">The name of the permission.</span></span>  
  
 <span data-ttu-id="6a71a-153">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="6a71a-153">**Column**</span></span>  
 <span data-ttu-id="6a71a-154">Os nomes de colunas que são afetadas pela permissão.</span><span class="sxs-lookup"><span data-stu-id="6a71a-154">The names of columns that are affected by the permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a71a-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6a71a-155">See Also</span></span>  
 <span data-ttu-id="6a71a-156">[Funções de nível de banco de dados](authentication-access/database-level-roles.md) </span><span class="sxs-lookup"><span data-stu-id="6a71a-156">[Database-Level Roles](authentication-access/database-level-roles.md) </span></span>  
 [<span data-ttu-id="6a71a-157">Central de segurança do Mecanismo de Banco de Dados do SQL Server e Banco de Dados SQL do Azure</span><span class="sxs-lookup"><span data-stu-id="6a71a-157">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
  
