---
title: Configurar a opção de configuração de servidor scan for startup procs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- scan for startup procs option
ms.assetid: 6bf9d252-e766-458d-9dcd-23d895f032a2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fbf46fc7476e6e879991cfe3f649fd5617f3275e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572171"
---
# <a name="configure-the-scan-for-startup-procs-server-configuration-option"></a><span data-ttu-id="0cd92-102">Configurar a opção de configuração de servidor scan for startup procs</span><span class="sxs-lookup"><span data-stu-id="0cd92-102">Configure the scan for startup procs Server Configuration Option</span></span>
  <span data-ttu-id="0cd92-103">Este tópico descreve como configurar a opção de configuração de servidor **scan for startup procs** no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0cd92-103">This topic describes how to configure the **scan for startup procs** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="0cd92-104">Use a opção **scan for startup procs** para examinar a execução automática de procedimentos armazenados no tempo de inicialização do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0cd92-104">Use the **scan for startup procs** option to scan for automatic execution of stored procedures at [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] startup time.</span></span> <span data-ttu-id="0cd92-105">Se essa opção for definida como 1, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] examinará e executará todos os procedimentos armazenados executados automaticamente definidos no servidor.</span><span class="sxs-lookup"><span data-stu-id="0cd92-105">If this option is set to 1, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] scans for and runs all automatically run stored procedures that are defined on the server.</span></span> <span data-ttu-id="0cd92-106">O valor padrão de **scan for startup procs** é 0 (não examinar).</span><span class="sxs-lookup"><span data-stu-id="0cd92-106">The default value for **scan for startup procs** is 0 (do not scan).</span></span>  
  
 <span data-ttu-id="0cd92-107">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="0cd92-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0cd92-108">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="0cd92-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0cd92-109">Recomendações</span><span class="sxs-lookup"><span data-stu-id="0cd92-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="0cd92-110">Segurança</span><span class="sxs-lookup"><span data-stu-id="0cd92-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0cd92-111">**Para configurar a opção scan for startup procs usando:**</span><span class="sxs-lookup"><span data-stu-id="0cd92-111">**To configure the scan for startup procs option, using:**</span></span>  
  
     [<span data-ttu-id="0cd92-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0cd92-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="0cd92-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0cd92-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="0cd92-114">**Acompanhamento:**  [depois de configurar a opção verificar processos de inicialização](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="0cd92-114">**Follow Up:**  [After you configure the scan for startup procs option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0cd92-115">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="0cd92-115">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="0cd92-116">Recomendações</span><span class="sxs-lookup"><span data-stu-id="0cd92-116">Recommendations</span></span>  
  
-   <span data-ttu-id="0cd92-117">Esta é uma opção avançada e deve ser alterada somente por um administrador de banco de dados experiente ou técnico certificado do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0cd92-117">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="0cd92-118">O valor desta opção pode ser definido usando **sp_configure**; porém, será definido automaticamente se você usar **sp_procoption**, que é usado para marcar ou desmarcar automaticamente os procedimentos armazenados executados.</span><span class="sxs-lookup"><span data-stu-id="0cd92-118">The value for this option can be set by using **sp_configure**; however, it will be set automatically if you use **sp_procoption**, which is used to mark or unmark automatically run stored procedures.</span></span> <span data-ttu-id="0cd92-119">Quando **sp_procoption** é usado para marcar o primeiro procedimento armazenado como um autoproc, essa opção é automaticamente definida como um valor 1.</span><span class="sxs-lookup"><span data-stu-id="0cd92-119">When **sp_procoption** is used to mark the first stored procedure as an autoproc, this option is set automatically to a value of 1.</span></span> <span data-ttu-id="0cd92-120">Quando **sp_procoption** é usado para desmarcar o último procedimento armazenado como um autoproc, essa opção é automaticamente definida como um valor 0.</span><span class="sxs-lookup"><span data-stu-id="0cd92-120">When **sp_procoption** is used to unmark the last stored procedure as an autoproc, this option is automatically set to a value of 0.</span></span> <span data-ttu-id="0cd92-121">Se você usar **sp_procoption** para marcar e desmarcar autoprocs, e se você sempre desmarcar autoprocs antes de cancelá-los, não haverá necessidade de definir essa opção manualmente.</span><span class="sxs-lookup"><span data-stu-id="0cd92-121">If you use **sp_procoption** to mark and unmark autoprocs, and if you always unmark autoprocs before dropping them, there is no need to set this option manually.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0cd92-122">Segurança</span><span class="sxs-lookup"><span data-stu-id="0cd92-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0cd92-123">Permissões</span><span class="sxs-lookup"><span data-stu-id="0cd92-123">Permissions</span></span>  
 <span data-ttu-id="0cd92-124">Permissões de execução sem parâmetros ou com apenas o primeiro parâmetro em **sp_configure** são concedidas a todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="0cd92-124">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="0cd92-125">Para executar **sp_configure** com ambos os parâmetros para alterar uma opção de configuração ou executar a instrução RECONFIGURE, o usuário deve ter a permissão ALTER SETTINGS no nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="0cd92-125">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="0cd92-126">A permissão ALTER SETTINGS é implicitamente mantida pelas funções de servidor fixas **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="0cd92-126">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0cd92-127">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0cd92-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-scan-for-startup-procs-option"></a><span data-ttu-id="0cd92-128">Para configurar a opção scan for startup procs</span><span class="sxs-lookup"><span data-stu-id="0cd92-128">To configure the scan for startup procs option</span></span>  
  
1.  <span data-ttu-id="0cd92-129">No Pesquisador de Objetos, clique com o botão direito do mouse em um servidor e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="0cd92-129">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="0cd92-130">Clique no nó **Avançado** .</span><span class="sxs-lookup"><span data-stu-id="0cd92-130">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="0cd92-131">Em **Diversos**, altere a opção **Examinar Procedimentos de Inicialização** para Verdadeiro ou Falso, selecionando o valor desejado na caixa de listagem suspensa.</span><span class="sxs-lookup"><span data-stu-id="0cd92-131">Under **Miscellaneous**, change the **Scan for Startup Procs** option to True or False by selecting the value you want from the drop-down list box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0cd92-132">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0cd92-132">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-scan-for-startup-procs-option"></a><span data-ttu-id="0cd92-133">Para configurar a opção scan for startup procs</span><span class="sxs-lookup"><span data-stu-id="0cd92-133">To configure the scan for startup procs option</span></span>  
  
1.  <span data-ttu-id="0cd92-134">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0cd92-134">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0cd92-135">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="0cd92-135">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0cd92-136">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="0cd92-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="0cd92-137">Este exemplo mostra como usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para definir o valor da opção `scan for startup procs` como `1`.</span><span class="sxs-lookup"><span data-stu-id="0cd92-137">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `scan for startup procs` option to `1`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE  
GO  
EXEC sp_configure 'scan for startup procs', 1 ;  
GO  
RECONFIGURE  
GO  
  
```  
  
##  <a name="follow-up-after-you-configure-the-scan-for-startup-procs-option"></a><a name="FollowUp"></a> <span data-ttu-id="0cd92-138">Acompanhamento: depois de configurar a opção verificar processos de inicialização</span><span class="sxs-lookup"><span data-stu-id="0cd92-138">Follow Up: After you configure the scan for startup procs option</span></span>  
 <span data-ttu-id="0cd92-139">O servidor deve ser reiniciado para que a configuração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="0cd92-139">The server must be restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cd92-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0cd92-140">See Also</span></span>  
 <span data-ttu-id="0cd92-141">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0cd92-141">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="0cd92-142">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0cd92-142">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="0cd92-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0cd92-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="0cd92-144">sp_procoption &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0cd92-144">sp_procoption &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql)  
  
  
