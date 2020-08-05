---
title: Configurar a opção de configuração de servidor media retention | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- backup retention duration [SQL Server]
- backup sets [SQL Server], retention duration
- media retention option
ms.assetid: 12e9fe6a-20a5-4c6e-9cc9-d500c003b70a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 092e0a2b5cfc30fd2d2362645fc1242bf4a1651e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572180"
---
# <a name="configure-the-media-retention-server-configuration-option"></a><span data-ttu-id="50e23-102">Configurar a opção de configuração de servidor media retention</span><span class="sxs-lookup"><span data-stu-id="50e23-102">Configure the media retention Server Configuration Option</span></span>
  <span data-ttu-id="50e23-103">Este tópico descreve como configurar a opção de configuração de servidor **media retention** no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50e23-103">This topic describes how to configure the **media retention** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="50e23-104">A opção **media retention** especifica a duração da retenção de cada conjunto de backups.</span><span class="sxs-lookup"><span data-stu-id="50e23-104">The **media retention** option specifies the length of time to retain each backup set.</span></span> <span data-ttu-id="50e23-105">A opção ajuda a proteger os backups para que não sejam substituídos até que o número especificado de dias tenha se passado.</span><span class="sxs-lookup"><span data-stu-id="50e23-105">The option helps protect backups from being overwritten until the specified number of days has elapsed.</span></span> <span data-ttu-id="50e23-106">Depois de configurar a opção **media retention** , não é necessário especificar a quantidade de tempo para reter backups de sistema cada vez em que se executa um backup.</span><span class="sxs-lookup"><span data-stu-id="50e23-106">After you configure **media retention** option, you do not have to specify the length of time to retain system backups each time you perform a backup.</span></span> <span data-ttu-id="50e23-107">O valor padrão é 0 dias e o valor máximo é 365 dias.</span><span class="sxs-lookup"><span data-stu-id="50e23-107">The default value is 0 days, and the maximum value is 365 days.</span></span>  
  
 <span data-ttu-id="50e23-108">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="50e23-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="50e23-109">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="50e23-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="50e23-110">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="50e23-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="50e23-111">Recomendações</span><span class="sxs-lookup"><span data-stu-id="50e23-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="50e23-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="50e23-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="50e23-113">**Para configurar a opção media retention usando:**</span><span class="sxs-lookup"><span data-stu-id="50e23-113">**To configure the media retention option, using:**</span></span>  
  
     [<span data-ttu-id="50e23-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="50e23-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="50e23-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="50e23-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="50e23-116">**Acompanhamento:**  [depois de configurar a opção media retention](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="50e23-116">**Follow Up:**  [After you configure the media retention option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="50e23-117">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="50e23-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="50e23-118">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="50e23-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="50e23-119">Se você usar a mídia de backup antes do número de dias definido, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] emitirá uma mensagem de aviso.</span><span class="sxs-lookup"><span data-stu-id="50e23-119">If you use the backup medium before the set number of days has passed, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] issues a warning message.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="50e23-120">não emitirá um aviso a menos que você altere o padrão.</span><span class="sxs-lookup"><span data-stu-id="50e23-120">does not issue a warning unless you change the default.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="50e23-121">Recomendações</span><span class="sxs-lookup"><span data-stu-id="50e23-121">Recommendations</span></span>  
  
-   <span data-ttu-id="50e23-122">Esta é uma opção avançada e deve ser alterada somente por um administrador de banco de dados experiente ou técnico certificado do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="50e23-122">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="50e23-123">A opção **media retention** pode ser substituída usando a cláusula RETAINDAYS da instrução [BACKUP](/sql/t-sql/statements/backup-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="50e23-123">The **media retention** option can be overridden by using the RETAINDAYS clause of the [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="50e23-124">Segurança</span><span class="sxs-lookup"><span data-stu-id="50e23-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="50e23-125">Permissões</span><span class="sxs-lookup"><span data-stu-id="50e23-125">Permissions</span></span>  
 <span data-ttu-id="50e23-126">Permissões de execução sem parâmetros ou com apenas o primeiro parâmetro em **sp_configure** são concedidas a todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="50e23-126">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="50e23-127">Para executar **sp_configure** com ambos os parâmetros para alterar uma opção de configuração ou executar a instrução RECONFIGURE, o usuário deve ter a permissão ALTER SETTINGS no nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="50e23-127">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="50e23-128">A permissão ALTER SETTINGS é implicitamente mantida pelas funções de servidor fixas **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="50e23-128">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="50e23-129">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="50e23-129">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-media-retention-option"></a><span data-ttu-id="50e23-130">Para configurar a opção media retention</span><span class="sxs-lookup"><span data-stu-id="50e23-130">To configure the media retention option</span></span>  
  
1.  <span data-ttu-id="50e23-131">No Pesquisador de Objetos, clique com o botão direito do mouse em um servidor e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="50e23-131">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="50e23-132">Clique no nó **Configurações de Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="50e23-132">Click the **Database settings** node.</span></span>  
  
3.  <span data-ttu-id="50e23-133">Em **Backup/Restauração**, na caixa **Retenção de mídia de backup padrão** , digite ou selecione um valor de 0 a 365 para definir o número de dias que a mídia de backup será retida depois do backup de log de bancos de dados ou de transações.</span><span class="sxs-lookup"><span data-stu-id="50e23-133">Under **Backup/Restore**, in the **Default backup media retention** box, type or select a value from 0 through 365 to set the number of days the backup medium will be retained after a database or transaction log backup.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="50e23-134">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="50e23-134">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-media-retention-option"></a><span data-ttu-id="50e23-135">Para configurar a opção media retention</span><span class="sxs-lookup"><span data-stu-id="50e23-135">To configure the media retention option</span></span>  
  
1.  <span data-ttu-id="50e23-136">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50e23-136">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="50e23-137">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="50e23-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="50e23-138">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="50e23-138">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="50e23-139">Este exemplo mostra como usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para definir o valor da opção `media retention` como `60` dias.</span><span class="sxs-lookup"><span data-stu-id="50e23-139">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `media retention` option to `60` days.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'media retention', 60 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="50e23-140">Para obter mais informações, veja [Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="50e23-140">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-media-retention-option"></a><a name="FollowUp"></a> <span data-ttu-id="50e23-141">Acompanhamento: depois de configurar a opção media retention</span><span class="sxs-lookup"><span data-stu-id="50e23-141">Follow Up: After you configure the media retention option</span></span>  
 <span data-ttu-id="50e23-142">A configuração entra em vigor imediatamente sem reiniciar o servidor.</span><span class="sxs-lookup"><span data-stu-id="50e23-142">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50e23-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="50e23-143">See Also</span></span>  
 <span data-ttu-id="50e23-144">[Fazer backup e restaurar bancos de dados do SQL Server](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="50e23-144">[Back Up and Restore of SQL Server Databases](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="50e23-145">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="50e23-145">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="50e23-146">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="50e23-146">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="50e23-147">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="50e23-147">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="50e23-148">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="50e23-148">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
