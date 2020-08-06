---
title: Configurar a opção de configuração de servidor recovery interval | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- restoring recovery interval [SQL Server]
- checkpoints [SQL Server]
- recovery interval option [SQL Server]
- default recovery interval option
- time [SQL Server], recovery interval
- interval for recovery [SQL Server]
- maximum number of minutes per database recovery
- recovery [SQL Server], recovery interval option
ms.assetid: e4734b3b-8fbe-4b65-9c48-91b5a3dd18e1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 560d514ba8dd1503b59b3b59ecf404d876e24cd2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570241"
---
# <a name="configure-the-recovery-interval-server-configuration-option"></a><span data-ttu-id="7682d-102">Configurar a opção recovery interval de configuração de servidor</span><span class="sxs-lookup"><span data-stu-id="7682d-102">Configure the recovery interval Server Configuration Option</span></span>
  <span data-ttu-id="7682d-103">Este tópico descreve como configurar a opção de configuração de servidor **recovery interval** no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7682d-103">This topic describes how to configure the **recovery interval** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="7682d-104">A opção **recovery interval** define um limite superior em relação ao tempo que deve levar a recuperação de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7682d-104">The **recovery interval** option defines an upper limit on the time recovering a database should take.</span></span> <span data-ttu-id="7682d-105">O [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] usa o valor especificado para esta opção para determinar a frequência aproximada de [pontos de verificação automáticos](../../relational-databases/logs/database-checkpoints-sql-server.md) para emitir pontos de verificação automáticos em determinado banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7682d-105">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] uses the value specified for this option to determine approximately how often [automatic checkpoints](../../relational-databases/logs/database-checkpoints-sql-server.md) to issue automatic checkpoints on a given database.</span></span>  
  
 <span data-ttu-id="7682d-106">O valor do intervalo de recuperação padrão é 0, o que permite que o [!INCLUDE[ssDE](../../includes/ssde-md.md)] configure automaticamente o intervalo de recuperação.</span><span class="sxs-lookup"><span data-stu-id="7682d-106">The default recovery-interval value is 0, which allows the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to automatically configure the recovery interval.</span></span> <span data-ttu-id="7682d-107">Normalmente, o intervalo de recuperação padrão resulta em pontos de verificação automáticos que ocorrem aproximadamente uma vez por minuto para bancos de dados ativos e em um tempo de recuperação inferior a um minuto.</span><span class="sxs-lookup"><span data-stu-id="7682d-107">Typically, the default recovery interval results in automatic checkpoints occurring approximately once a minute for active databases and a recovery time of less than one minute.</span></span> <span data-ttu-id="7682d-108">Valores mais altos indicam o tempo de recuperação máximo aproximado, em minutos.</span><span class="sxs-lookup"><span data-stu-id="7682d-108">Higher values indicate the approximate maximum recovery time, in minutes.</span></span> <span data-ttu-id="7682d-109">Por exemplo, a definição do intervalo de recuperação como 3 indica o tempo máximo de recuperação de aproximadamente três minutos.</span><span class="sxs-lookup"><span data-stu-id="7682d-109">For example, setting the recovery interval to 3 indicates a maximum recovery time of approximately three minutes.</span></span>  
  
 <span data-ttu-id="7682d-110">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="7682d-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7682d-111">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="7682d-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7682d-112">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="7682d-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="7682d-113">Recomendações</span><span class="sxs-lookup"><span data-stu-id="7682d-113">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="7682d-114">Segurança</span><span class="sxs-lookup"><span data-stu-id="7682d-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7682d-115">**Para configurar a opção de configuração de servidor recovery interval usando:**</span><span class="sxs-lookup"><span data-stu-id="7682d-115">**To Configure the recovery interval Server Configuration Option, using:**</span></span>  
  
     [<span data-ttu-id="7682d-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7682d-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7682d-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7682d-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="7682d-118">**Acompanhamento:**  [depois de configurar a opção recovery interval](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="7682d-118">**Follow Up:**  [After you configure the recovery interval option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7682d-119">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="7682d-119">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="7682d-120">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="7682d-120">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="7682d-121">O intervalo de recuperação afeta apenas bancos de dados que usam o tempo de recuperação de destino padrão (0).</span><span class="sxs-lookup"><span data-stu-id="7682d-121">The recovery interval affects only databases that use the default target recovery time (0).</span></span> <span data-ttu-id="7682d-122">Para anular o intervalo de recuperação de servidor em um banco de dados, configure um tempo de recuperação de destino não padrão no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7682d-122">To override the server recovery interval on a database, configure a non-default target recovery time on the database.</span></span> <span data-ttu-id="7682d-123">Para obter mais informações, veja [Alterar o tempo de recuperação de destino de um banco de dados &#40;SQL Server&#41;](../../relational-databases/logs/change-the-target-recovery-time-of-a-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7682d-123">For more information, see [Change the Target Recovery Time of a Database &#40;SQL Server&#41;](../../relational-databases/logs/change-the-target-recovery-time-of-a-database-sql-server.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="7682d-124">Recomendações</span><span class="sxs-lookup"><span data-stu-id="7682d-124">Recommendations</span></span>  
  
-   <span data-ttu-id="7682d-125">Esta é uma opção avançada e deve ser alterada somente por um administrador de banco de dados experiente ou técnico certificado do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7682d-125">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="7682d-126">Normalmente, é recomendável manter o intervalo de recuperação em 0, a menos que você tenha problemas de desempenho.</span><span class="sxs-lookup"><span data-stu-id="7682d-126">Typically, we recommend that you keep the recovery interval at 0, unless you experience performance problems.</span></span> <span data-ttu-id="7682d-127">Se você decidir aumentar a configuração de intervalo de recuperação, é recomendável fazer isso gradativamente, em pequenos incrementos, e avaliar o efeito de cada aumento incremental no desempenho da recuperação.</span><span class="sxs-lookup"><span data-stu-id="7682d-127">If you decide to increase the recovery-interval setting, we recommend increasing it gradually by small increments and evaluating the effect of each incremental increase on recovery performance.</span></span>  
  
-   <span data-ttu-id="7682d-128">Se você usar **sp_configure** para alterar o valor da opção **recovery interval** para mais de 60 (minutos), especifique RECONFIGURE WITH OVERRIDE.</span><span class="sxs-lookup"><span data-stu-id="7682d-128">If you use **sp_configure** to change the value of the **recovery interval** option to more than 60 (minutes), specify RECONFIGURE WITH OVERRIDE.</span></span> <span data-ttu-id="7682d-129">WITH OVERRIDE desabilita a verificação do valor da configuração (para valores que não são válidos ou não são recomendados).</span><span class="sxs-lookup"><span data-stu-id="7682d-129">WITH OVERRIDE disables configuration value checking (for values that are not valid or are nonrecommended values).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7682d-130">Segurança</span><span class="sxs-lookup"><span data-stu-id="7682d-130">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7682d-131">Permissões</span><span class="sxs-lookup"><span data-stu-id="7682d-131">Permissions</span></span>  
 <span data-ttu-id="7682d-132">Permissões de execução sem parâmetros ou com apenas o primeiro parâmetro em **sp_configure** são concedidas a todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="7682d-132">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="7682d-133">Para executar **sp_configure** com ambos os parâmetros para alterar uma opção de configuração ou executar a instrução RECONFIGURE, o usuário deve ter a permissão ALTER SETTINGS no nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="7682d-133">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="7682d-134">A permissão ALTER SETTINGS é implicitamente mantida pelas funções de servidor fixas **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="7682d-134">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7682d-135">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7682d-135">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="7682d-136">**Para definir o intervalo de recuperação**</span><span class="sxs-lookup"><span data-stu-id="7682d-136">**To set the recovery interval**</span></span>  
  
1.  <span data-ttu-id="7682d-137">No Pesquisador de Objetos, clique com o botão direito do mouse na instância de servidor e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="7682d-137">In Object Explorer, right-click server instance and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="7682d-138">Clique no nó **Configurações de Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="7682d-138">Click the **Database settings** node.</span></span>  
  
3.  <span data-ttu-id="7682d-139">Em **Recuperação**, na caixa **Intervalo de recuperação (minutos)** , digite ou selecione um valor de 0 a 32767 para definir o intervalo máximo de tempo, em minutos, que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deveria gastar recuperando cada banco de dados na inicialização.</span><span class="sxs-lookup"><span data-stu-id="7682d-139">Under **Recovery**, in the **Recovery interval (minutes)** box, type or select a value from 0 through 32767 to set the maximum amount of time, in minutes, that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should spend recovering each database at startup.</span></span> <span data-ttu-id="7682d-140">O padrão é 0, que indica configuração automática pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7682d-140">The default is 0, indicating automatic configuration by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7682d-141">Na prática, isso significa um tempo de recuperação inferior a um minuto e um ponto de verificação a cada um minuto aproximadamente para bancos de dados ativos.</span><span class="sxs-lookup"><span data-stu-id="7682d-141">In practice, this means a recovery time of less than one minute and a checkpoint approximately every one minute for active databases.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7682d-142">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7682d-142">Using Transact-SQL</span></span>  
  
#### <a name="to-set-the-recovery-interval"></a><span data-ttu-id="7682d-143">Para definir o intervalo de recuperação</span><span class="sxs-lookup"><span data-stu-id="7682d-143">To set the recovery interval</span></span>  
  
1.  <span data-ttu-id="7682d-144">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7682d-144">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7682d-145">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="7682d-145">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7682d-146">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="7682d-146">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="7682d-147">Este exemplo mostra como usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para definir o valor da opção `recovery interval` como `3` minutos.</span><span class="sxs-lookup"><span data-stu-id="7682d-147">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `recovery interval` option to `3` minutes.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'recovery interval', 3 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="7682d-148">Para obter mais informações, veja [Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7682d-148">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-recovery-internal-option"></a><a name="FollowUp"></a> <span data-ttu-id="7682d-149">Acompanhamento: depois de configurar a opção recovery internal</span><span class="sxs-lookup"><span data-stu-id="7682d-149">Follow Up: After you configure the recovery internal option</span></span>  
 <span data-ttu-id="7682d-150">A configuração entra em vigor imediatamente sem reiniciar o servidor.</span><span class="sxs-lookup"><span data-stu-id="7682d-150">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7682d-151">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7682d-151">See Also</span></span>  
 <span data-ttu-id="7682d-152">[Alterar o tempo de recuperação de destino de um banco de dados &#40;SQL Server&#41;](../../relational-databases/logs/change-the-target-recovery-time-of-a-database-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7682d-152">[Change the Target Recovery Time of a Database &#40;SQL Server&#41;](../../relational-databases/logs/change-the-target-recovery-time-of-a-database-sql-server.md) </span></span>  
 <span data-ttu-id="7682d-153">[Pontos de verificação de banco de dados &#40;SQL Server&#41;](../../relational-databases/logs/database-checkpoints-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7682d-153">[Database Checkpoints &#40;SQL Server&#41;](../../relational-databases/logs/database-checkpoints-sql-server.md) </span></span>  
 <span data-ttu-id="7682d-154">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7682d-154">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="7682d-155">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7682d-155">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="7682d-156">[Opção de configuração de servidor show advanced options](show-advanced-options-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="7682d-156">[show advanced options Server Configuration Option](show-advanced-options-server-configuration-option.md) </span></span>  
 [<span data-ttu-id="7682d-157">RECONFIGURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7682d-157">RECONFIGURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reconfigure-transact-sql)  
  
  
