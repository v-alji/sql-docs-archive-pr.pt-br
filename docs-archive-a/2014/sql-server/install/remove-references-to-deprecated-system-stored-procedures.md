---
title: Remover referências a procedimentos armazenados do sistema preteridos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- undocumented system stored procedures [SQL Server]
- system stored procedures [SQL Server]
ms.assetid: 487d24fc-41d5-495e-843c-0ac974ec472f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 65e7da666beaf84050dd8d60caf4cac5bfc013c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683318"
---
# <a name="remove-references-to-deprecated-system-stored-procedures"></a><span data-ttu-id="a2dab-102">Remover referências a procedimentos armazenados do sistema obsoletos</span><span class="sxs-lookup"><span data-stu-id="a2dab-102">Remove references to deprecated system stored procedures</span></span>
  <span data-ttu-id="a2dab-103">O Supervisor de Atualização detectou instruções que fazem referência a procedimentos armazenados do sistema não documentados e a procedimentos armazenados estendidos que não estão mais disponíveis no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a2dab-103">Upgrade Advisor detected statements that reference undocumented system stored procedures and extended stored procedures that are no longer available in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a2dab-104">As instruções que fizerem referência a esses objetos falharão.</span><span class="sxs-lookup"><span data-stu-id="a2dab-104">Statements that reference these objects will fail.</span></span> <span data-ttu-id="a2dab-105">Não use objetos ou APIs do sistema não documentados, pois a funcionalidade pode ser alterada ou removida sem notificação em uma versão futura.</span><span class="sxs-lookup"><span data-stu-id="a2dab-105">Do not use undocumented system objects or APIs as the functionality might change or be removed without notification in a future release.</span></span>  
  
## <a name="component"></a><span data-ttu-id="a2dab-106">Componente</span><span class="sxs-lookup"><span data-stu-id="a2dab-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="a2dab-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="a2dab-107">Description</span></span>  
  
### <a name="documented-system-stored-procedures"></a><span data-ttu-id="a2dab-108">Procedimentos armazenados do sistema documentados</span><span class="sxs-lookup"><span data-stu-id="a2dab-108">Documented System Stored Procedures</span></span>  
 <span data-ttu-id="a2dab-109">Os seguintes procedimentos armazenados do sistema documentados foram removidos:</span><span class="sxs-lookup"><span data-stu-id="a2dab-109">The following documented system stored procedures have been removed:</span></span>  
  
-   <span data-ttu-id="a2dab-110">sp_addalias</span><span class="sxs-lookup"><span data-stu-id="a2dab-110">sp_addalias</span></span>  
  
-   <span data-ttu-id="a2dab-111">sp_addgroup</span><span class="sxs-lookup"><span data-stu-id="a2dab-111">sp_addgroup</span></span>  
  
-   <span data-ttu-id="a2dab-112">sp_changegroup</span><span class="sxs-lookup"><span data-stu-id="a2dab-112">sp_changegroup</span></span>  
  
-   <span data-ttu-id="a2dab-113">sp_dropgroup</span><span class="sxs-lookup"><span data-stu-id="a2dab-113">sp_dropgroup</span></span>  
  
-   <span data-ttu-id="a2dab-114">sp_helpgroup</span><span class="sxs-lookup"><span data-stu-id="a2dab-114">sp_helpgroup</span></span>  
  
### <a name="undocumented-system-stored-procedures"></a><span data-ttu-id="a2dab-115">Procedimentos armazenados do sistema não documentados</span><span class="sxs-lookup"><span data-stu-id="a2dab-115">Undocumented System Stored Procedures</span></span>  
 <span data-ttu-id="a2dab-116">Os seguintes procedimentos armazenados do sistema não documentados e procedimentos estendidos armazenados foram removidos:</span><span class="sxs-lookup"><span data-stu-id="a2dab-116">The following undocumented system stored procedures and extended stored procedures have been removed:</span></span>  
  
-   <span data-ttu-id="a2dab-117">sp_articlesynctranprocs</span><span class="sxs-lookup"><span data-stu-id="a2dab-117">sp_articlesynctranprocs</span></span>  
  
-   <span data-ttu-id="a2dab-118">sp_diskdefault</span><span class="sxs-lookup"><span data-stu-id="a2dab-118">sp_diskdefault</span></span>  
  
-   <span data-ttu-id="a2dab-119">sp_EventLog</span><span class="sxs-lookup"><span data-stu-id="a2dab-119">sp_EventLog</span></span>  
  
-   <span data-ttu-id="a2dab-120">sp_GetMBCSCharLen</span><span class="sxs-lookup"><span data-stu-id="a2dab-120">sp_GetMBCSCharLen</span></span>  
  
-   <span data-ttu-id="a2dab-121">sp_helplog</span><span class="sxs-lookup"><span data-stu-id="a2dab-121">sp_helplog</span></span>  
  
-   <span data-ttu-id="a2dab-122">sp_helpsql</span><span class="sxs-lookup"><span data-stu-id="a2dab-122">sp_helpsql</span></span>  
  
-   <span data-ttu-id="a2dab-123">sp_IsMBCSLeadByte</span><span class="sxs-lookup"><span data-stu-id="a2dab-123">sp_IsMBCSLeadByte</span></span>  
  
-   <span data-ttu-id="a2dab-124">sp_lock2</span><span class="sxs-lookup"><span data-stu-id="a2dab-124">sp_lock2</span></span>  
  
-   <span data-ttu-id="a2dab-125">sp_MSget_current_activity</span><span class="sxs-lookup"><span data-stu-id="a2dab-125">sp_MSget_current_activity</span></span>  
  
-   <span data-ttu-id="a2dab-126">sp_MSset_current_activity</span><span class="sxs-lookup"><span data-stu-id="a2dab-126">sp_MSset_current_activity</span></span>  
  
-   <span data-ttu-id="a2dab-127">sp_MSobjessearch</span><span class="sxs-lookup"><span data-stu-id="a2dab-127">sp_MSobjessearch</span></span>  
  
-   <span data-ttu-id="a2dab-128">xp_enum_ActiveScriptEngines</span><span class="sxs-lookup"><span data-stu-id="a2dab-128">xp_enum_ActiveScriptEngines</span></span>  
  
-   <span data-ttu-id="a2dab-129">xp_eventlog</span><span class="sxs-lookup"><span data-stu-id="a2dab-129">xp_eventlog</span></span>  
  
-   <span data-ttu-id="a2dab-130">xp_GetAdminGroupName</span><span class="sxs-lookup"><span data-stu-id="a2dab-130">xp_GetAdminGroupName</span></span>  
  
-   <span data-ttu-id="a2dab-131">xp_GetFileDetails</span><span class="sxs-lookup"><span data-stu-id="a2dab-131">xp_GetFileDetails</span></span>  
  
-   <span data-ttu-id="a2dab-132">xp_GetLocalSystemAccountName</span><span class="sxs-lookup"><span data-stu-id="a2dab-132">xp_GetLocalSystemAccountName</span></span>  
  
-   <span data-ttu-id="a2dab-133">xp_IsNTAdmin</span><span class="sxs-lookup"><span data-stu-id="a2dab-133">xp_IsNTAdmin</span></span>  
  
-   <span data-ttu-id="a2dab-134">xp_MSLocalSystem</span><span class="sxs-lookup"><span data-stu-id="a2dab-134">xp_MSLocalSystem</span></span>  
  
-   <span data-ttu-id="a2dab-135">xp_MSnt2000</span><span class="sxs-lookup"><span data-stu-id="a2dab-135">xp_MSnt2000</span></span>  
  
-   <span data-ttu-id="a2dab-136">xp_MSplatform</span><span class="sxs-lookup"><span data-stu-id="a2dab-136">xp_MSplatform</span></span>  
  
-   <span data-ttu-id="a2dab-137">xp_SetSecurity</span><span class="sxs-lookup"><span data-stu-id="a2dab-137">xp_SetSecurity</span></span>  
  
-   <span data-ttu-id="a2dab-138">xp_varbintohexstr</span><span class="sxs-lookup"><span data-stu-id="a2dab-138">xp_varbintohexstr</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="a2dab-139">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="a2dab-139">Corrective Action</span></span>  
  
### <a name="documented-system-stored-procedures"></a><span data-ttu-id="a2dab-140">Procedimentos armazenados do sistema documentados</span><span class="sxs-lookup"><span data-stu-id="a2dab-140">Documented System Stored Procedures</span></span>  
 <span data-ttu-id="a2dab-141">Modifique seus aplicativos de acordo com a tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="a2dab-141">Modify your applications according to the following table.</span></span>  
  
|<span data-ttu-id="a2dab-142">Em vez de</span><span class="sxs-lookup"><span data-stu-id="a2dab-142">Instead of</span></span>|<span data-ttu-id="a2dab-143">Faça isto</span><span class="sxs-lookup"><span data-stu-id="a2dab-143">Do this</span></span>|  
|----------------|-------------|  
|<span data-ttu-id="a2dab-144">sp_addalias</span><span class="sxs-lookup"><span data-stu-id="a2dab-144">sp_addalias</span></span>|<span data-ttu-id="a2dab-145">Substitua aliases por uma combinação de contas de usuário e funções de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a2dab-145">Replace aliases with a combination of user accounts and database roles.</span></span> <span data-ttu-id="a2dab-146">Para obter mais informações, consulte "CREATE USER (Transact-SQL)" e "CREATE ROLE (Transact-SQL)" nos Manuais Online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a2dab-146">For more information, see "CREATE USER (Transact-SQL)" and "CREATE ROLE (Transact-SQL)" in SQL Server Books Online.</span></span> <span data-ttu-id="a2dab-147">Remova aliases dos bancos de dados atualizados usando sp_dropalias.</span><span class="sxs-lookup"><span data-stu-id="a2dab-147">Remove aliases in upgraded databases by using sp_dropalias.</span></span>|  
|<span data-ttu-id="a2dab-148">sp_addgroupsp_changegroup</span><span class="sxs-lookup"><span data-stu-id="a2dab-148">sp_addgroupsp_changegroup</span></span><br /><br /> <span data-ttu-id="a2dab-149">sp_dropgroup</span><span class="sxs-lookup"><span data-stu-id="a2dab-149">sp_dropgroup</span></span><br /><br /> <span data-ttu-id="a2dab-150">sp_helpgroup</span><span class="sxs-lookup"><span data-stu-id="a2dab-150">sp_helpgroup</span></span>|<span data-ttu-id="a2dab-151">Use funções.</span><span class="sxs-lookup"><span data-stu-id="a2dab-151">Use roles.</span></span> <span data-ttu-id="a2dab-152">Para obter mais informações, consulte "Funções no nível de servidor" e "Funções no nível de banco de dados" nos Manuais Online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a2dab-152">For more information, see "Server-Level Roles" and "Database-Level Roles" in SQL Server Books Online.</span></span>|  
  
### <a name="undocmented-system-stored-procedures"></a><span data-ttu-id="a2dab-153">Procedimentos armazenados do sistema Undocmented</span><span class="sxs-lookup"><span data-stu-id="a2dab-153">Undocmented System Stored Procedures</span></span>  
 <span data-ttu-id="a2dab-154">Você pode criar procedimentos armazenados CLR com funcionalidade equivalente para substituir procedimentos armazenados do sistema não documentados.</span><span class="sxs-lookup"><span data-stu-id="a2dab-154">You can create CLR stored procedures with equivalent functionality to replace the undocumented system stored procedures.</span></span> <span data-ttu-id="a2dab-155">Para obter mais informações, consulte o tópico ‘Procedimentos armazenados CLR’ nos Manuais Online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a2dab-155">For more information, see the topic "CLR Stored Procedures" in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2dab-156">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a2dab-156">See Also</span></span>  
 <span data-ttu-id="a2dab-157">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="a2dab-157">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="a2dab-158">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="a2dab-158">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
