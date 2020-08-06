---
title: Configurar a opção de configuração de servidor query wait | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], timing out
- time [SQL Server], query wait time
- query wait option [SQL Server]
ms.assetid: 0fc4aa01-65a3-4a33-9ef4-caca41add238
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 638afff2aa05a9fc4e61bc71e8610dba1dda8cf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575338"
---
# <a name="configure-the-query-wait-server-configuration-option"></a><span data-ttu-id="2aedf-102">Configurar a opção de configuração de servidor query wait</span><span class="sxs-lookup"><span data-stu-id="2aedf-102">Configure the query wait Server Configuration Option</span></span>
  <span data-ttu-id="2aedf-103">Este tópico descreve como configurar a opção de configuração de servidor **query wait** no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2aedf-103">This topic describes how to configure the **query wait** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="2aedf-104">As consultas que solicitam muita memória (como as que envolvem classificação e hash) são enfileiradas quando não há memória disponível executar a consulta.</span><span class="sxs-lookup"><span data-stu-id="2aedf-104">Memory-intensive queries (such as those involving sorting and hashing) are queued when there is not enough memory available to run the query.</span></span> <span data-ttu-id="2aedf-105">A opção **espera de consulta** especifica o tempo em segundos (de 0 a 2147483647) que uma consulta deve esperar por recursos antes de o tempo limite ser excedido. O valor padrão dessa opção é -1.</span><span class="sxs-lookup"><span data-stu-id="2aedf-105">The **query wait** option specifies the time, in seconds (from 0 through 2147483647), that a query waits for resources before it times out. The default value for this option is -1.</span></span> <span data-ttu-id="2aedf-106">Isso significa que o tempo limite é calculado como 25 vezes o custo de consulta estimado.</span><span class="sxs-lookup"><span data-stu-id="2aedf-106">This means the time-out is calculated as 25 times the estimated query cost.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2aedf-107">Uma transação que contém a consulta de espera pode manter bloqueios enquanto a consulta espera por memória.</span><span class="sxs-lookup"><span data-stu-id="2aedf-107">A transaction that contains the waiting query might hold locks while the query waits for memory.</span></span> <span data-ttu-id="2aedf-108">Em situações raras, é possível que um erro de deadlock indetectável ocorra.</span><span class="sxs-lookup"><span data-stu-id="2aedf-108">In rare situations, it is possible for an undetectable deadlock to occur.</span></span> <span data-ttu-id="2aedf-109">Diminuir o tempo de espera da consulta reduz a probabilidade desses deadlocks.</span><span class="sxs-lookup"><span data-stu-id="2aedf-109">Decreasing the query wait time lowers the probability of such deadlocks.</span></span> <span data-ttu-id="2aedf-110">Eventualmente, uma consulta em espera será encerrada e o bloqueio da transação liberado.</span><span class="sxs-lookup"><span data-stu-id="2aedf-110">Eventually, a waiting query will be terminated and the transaction locks released.</span></span> <span data-ttu-id="2aedf-111">Porém, aumentar o tempo de espera máximo pode aumentar a quantidade de tempo da consulta a ser encerrada.</span><span class="sxs-lookup"><span data-stu-id="2aedf-111">However, increasing the maximum wait time may increase the amount of time for the query to be terminated.</span></span> <span data-ttu-id="2aedf-112">Não é recomendado alterar essa opção.</span><span class="sxs-lookup"><span data-stu-id="2aedf-112">Changes to this option are not recommended.</span></span>  
  
 <span data-ttu-id="2aedf-113">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="2aedf-113">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2aedf-114">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="2aedf-114">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2aedf-115">Recomendações</span><span class="sxs-lookup"><span data-stu-id="2aedf-115">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="2aedf-116">Segurança</span><span class="sxs-lookup"><span data-stu-id="2aedf-116">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2aedf-117">**Para configurar a opção query wait usando:**</span><span class="sxs-lookup"><span data-stu-id="2aedf-117">**To configure the query wait option, using:**</span></span>  
  
     [<span data-ttu-id="2aedf-118">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2aedf-118">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2aedf-119">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2aedf-119">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="2aedf-120">**Acompanhamento:**  [depois de configurar a opção query wait option](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="2aedf-120">**Follow Up:**  [After you configure the query wait option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2aedf-121">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="2aedf-121">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="2aedf-122">Recomendações</span><span class="sxs-lookup"><span data-stu-id="2aedf-122">Recommendations</span></span>  
  
-   <span data-ttu-id="2aedf-123">Esta é uma opção avançada e deve ser alterada somente por um administrador de banco de dados experiente ou técnico certificado do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2aedf-123">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2aedf-124">Segurança</span><span class="sxs-lookup"><span data-stu-id="2aedf-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2aedf-125">Permissões</span><span class="sxs-lookup"><span data-stu-id="2aedf-125">Permissions</span></span>  
 <span data-ttu-id="2aedf-126">Permissões de execução sem parâmetros ou com apenas o primeiro parâmetro em **sp_configure** são concedidas a todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="2aedf-126">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="2aedf-127">Para executar **sp_configure** com ambos os parâmetros para alterar uma opção de configuração ou executar a instrução RECONFIGURE, o usuário deve ter a permissão ALTER SETTINGS no nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="2aedf-127">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="2aedf-128">A permissão ALTER SETTINGS é implicitamente mantida pelas funções de servidor fixas **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="2aedf-128">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2aedf-129">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2aedf-129">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-query-wait-option"></a><span data-ttu-id="2aedf-130">Para configurar a opção query wait</span><span class="sxs-lookup"><span data-stu-id="2aedf-130">To configure the query wait option</span></span>  
  
1.  <span data-ttu-id="2aedf-131">No Pesquisador de Objetos, clique com o botão direito do mouse em um servidor e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="2aedf-131">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="2aedf-132">Clique no nó **Avançado** .</span><span class="sxs-lookup"><span data-stu-id="2aedf-132">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="2aedf-133">Em **Paralelismo**, digite o valor desejado para a opção **query wait** .</span><span class="sxs-lookup"><span data-stu-id="2aedf-133">Under **Parallelism**, type the desired value for the **query wait** option.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2aedf-134">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2aedf-134">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-query-wait-option"></a><span data-ttu-id="2aedf-135">Para configurar a opção query wait</span><span class="sxs-lookup"><span data-stu-id="2aedf-135">To configure the query wait option</span></span>  
  
1.  <span data-ttu-id="2aedf-136">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2aedf-136">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2aedf-137">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="2aedf-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2aedf-138">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="2aedf-138">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="2aedf-139">Este exemplo mostra como usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para definir o valor da opção `query wait` como `7500` segundos.</span><span class="sxs-lookup"><span data-stu-id="2aedf-139">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `query wait` option to `7500` seconds.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'query wait', 7500 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="2aedf-140">Para obter mais informações, veja [Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2aedf-140">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-query-wait-option"></a><a name="FollowUp"></a> <span data-ttu-id="2aedf-141">Acompanhamento: depois de configurar a opção query wait option</span><span class="sxs-lookup"><span data-stu-id="2aedf-141">Follow Up: After you configure the query wait option</span></span>  
 <span data-ttu-id="2aedf-142">A configuração entra em vigor imediatamente sem reiniciar o servidor.</span><span class="sxs-lookup"><span data-stu-id="2aedf-142">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aedf-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2aedf-143">See Also</span></span>  
 <span data-ttu-id="2aedf-144">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2aedf-144">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="2aedf-145">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2aedf-145">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="2aedf-146">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2aedf-146">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
