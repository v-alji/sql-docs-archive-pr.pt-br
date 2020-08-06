---
title: Configurar a opção de configuração de servidor locks | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- locks option [SQL Server]
ms.assetid: b0cf0f86-7652-4574-a9fb-908e10d03973
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e45f4cc539be585966eb0beb30d4938b504c3419
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685270"
---
# <a name="configure-the-locks-server-configuration-option"></a><span data-ttu-id="39e65-102">Configurar a opção locks de configuração de servidor</span><span class="sxs-lookup"><span data-stu-id="39e65-102">Configure the locks Server Configuration Option</span></span>
  <span data-ttu-id="39e65-103">Este tópico descreve como configurar a opção de configuração de servidor **locks** no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39e65-103">This topic describes how to configure the **locks** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="39e65-104">A opção **locks** define o número máximo de bloqueios disponíveis, limitando a quantidade de memória que o [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] usa para eles.</span><span class="sxs-lookup"><span data-stu-id="39e65-104">The **locks** option sets the maximum number of available locks, thereby limiting the amount of memory the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] uses for them.</span></span> <span data-ttu-id="39e65-105">A configuração padrão é 0, a qual permite que o [!INCLUDE[ssDE](../../includes/ssde-md.md)] aloque e desaloque as estruturas de bloqueio de forma dinâmica, baseado nas alterações de requisitos de sistema.</span><span class="sxs-lookup"><span data-stu-id="39e65-105">The default setting is 0, which allows the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to allocate and deallocate lock structures dynamically, based on changing system requirements.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)]  
  
 <span data-ttu-id="39e65-106">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="39e65-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="39e65-107">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="39e65-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="39e65-108">Recomendações</span><span class="sxs-lookup"><span data-stu-id="39e65-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="39e65-109">Segurança</span><span class="sxs-lookup"><span data-stu-id="39e65-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="39e65-110">**Para configurar a opção locks, usando:**</span><span class="sxs-lookup"><span data-stu-id="39e65-110">**To configure the locks option, using:**</span></span>  
  
     [<span data-ttu-id="39e65-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="39e65-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="39e65-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="39e65-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="39e65-113">**Acompanhamento:**  [depois de configurar a opção bloqueios](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="39e65-113">**Follow Up:**  [After you configure the locks option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="39e65-114">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="39e65-114">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="39e65-115">Recomendações</span><span class="sxs-lookup"><span data-stu-id="39e65-115">Recommendations</span></span>  
  
-   <span data-ttu-id="39e65-116">Esta é uma opção avançada e deve ser alterada somente por um administrador de banco de dados experiente ou técnico certificado do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="39e65-116">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="39e65-117">Quando o servidor é iniciado com **bloqueios** definido como 0, o gerenciador de bloqueio adquire memória suficiente do [!INCLUDE[ssDE](../../includes/ssde-md.md)] para um pool inicial de 2.500 estruturas de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="39e65-117">When the server is started with **locks** set to 0, the lock manager acquires sufficient memory from the [!INCLUDE[ssDE](../../includes/ssde-md.md)] for an initial pool of 2,500 lock structures.</span></span> <span data-ttu-id="39e65-118">Conforme o pool de bloqueio é esgotado, memória adicional é adquirida para o pool.</span><span class="sxs-lookup"><span data-stu-id="39e65-118">As the lock pool is exhausted, additional memory is acquired for the pool.</span></span>  
  
     <span data-ttu-id="39e65-119">Geralmente, se for necessária mais memória para o pool de bloqueio do que a que está disponível no pool de memória do [!INCLUDE[ssDE](../../includes/ssde-md.md)] , e se mais memória do computador estiver disponível (o limite de **memória máxima do servidor** não foi atingido), o [!INCLUDE[ssDE](../../includes/ssde-md.md)] alocará memória dinamicamente para satisfazer a solicitação de bloqueios.</span><span class="sxs-lookup"><span data-stu-id="39e65-119">Generally, if more memory is required for the lock pool than is available in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] memory pool, and more computer memory is available (the **max server memory** threshold has not been reached), the [!INCLUDE[ssDE](../../includes/ssde-md.md)] allocates memory dynamically to satisfy the request for locks.</span></span> <span data-ttu-id="39e65-120">No entanto, se a alocação dessa memória provocar paginação no nível do sistema operacional (por exemplo, se outro aplicativo estiver executando no mesmo computador como uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e usando essa memória), mais espaço de bloqueio não será alocado.</span><span class="sxs-lookup"><span data-stu-id="39e65-120">However, if allocating that memory would cause paging at the operating system level (for example, if another application is running on the same computer as an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and using that memory), more lock space is not allocated.</span></span> <span data-ttu-id="39e65-121">O pool de bloqueios dinâmico não adquire mais que 60 por cento da memória alocada para o [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39e65-121">The dynamic lock pool does not acquire more than 60 percent of the memory allocated to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="39e65-122">Depois que o pool de bloqueios atingiu 60 por cento da memória adquirida por uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)]ou quando não houver mais memória disponível no computador as solicitações de bloqueios adicionais gerarão um erro.</span><span class="sxs-lookup"><span data-stu-id="39e65-122">After the lock pool has reached 60 percent of the memory acquired by an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], or no more memory is available on the computer, further requests for locks generate an error.</span></span>  
  
     <span data-ttu-id="39e65-123">Recomenda-se permitir que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] use bloqueios dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="39e65-123">Allowing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to use locks dynamically is the recommended configuration.</span></span> <span data-ttu-id="39e65-124">No entanto, você pode definir **bloqueios** e substituir a capacidade do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de alocar recursos de bloqueio dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="39e65-124">However, you can set **locks** and override the ability of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to allocate lock resources dynamically.</span></span> <span data-ttu-id="39e65-125">Quando a opção **bloqueios** está definida com um valor diferente de 0, o [!INCLUDE[ssDE](../../includes/ssde-md.md)] não pode alocar mais bloqueios do que o valor especificado em **bloqueios**.</span><span class="sxs-lookup"><span data-stu-id="39e65-125">When **locks** is set to a value other than 0, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] cannot allocate more locks than the value specified in **locks**.</span></span> <span data-ttu-id="39e65-126">Aumente esse valor se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] exibir uma mensagem de que você excedeu o número de bloqueios disponíveis.</span><span class="sxs-lookup"><span data-stu-id="39e65-126">Increase this value if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] displays a message that you have exceeded the number of available locks.</span></span> <span data-ttu-id="39e65-127">Como cada bloqueio consome memória (96 bytes por bloqueio), aumentar esse valor pode exigir o aumento da quantidade de memória dedicada para o servidor.</span><span class="sxs-lookup"><span data-stu-id="39e65-127">Because each lock consumes memory (96 bytes per lock), increasing this value can require increasing the amount of memory dedicated to the server.</span></span>  
  
-   <span data-ttu-id="39e65-128">A opção **bloqueios** também é afetada quando ocorre escalonamento de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="39e65-128">The **locks** option also affects when lock escalation occurs.</span></span> <span data-ttu-id="39e65-129">Quando a opção **bloqueios** está definida como 0, o escalonamento de bloqueio ocorre quando a memória usada pelas estruturas de bloqueio atuais atingir 40 por cento do pool de memória do [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="39e65-129">When **locks** is set to 0, lock escalation occurs when the memory used by the current lock structures reaches 40 percent of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] memory pool.</span></span> <span data-ttu-id="39e65-130">Quando a opção **bloqueios** não está definida como 0, o escalonamento de bloqueio ocorre quando o número de bloqueios atinge 40 por cento do valor especificado para **bloqueios**.</span><span class="sxs-lookup"><span data-stu-id="39e65-130">When **locks** is not set to 0, lock escalation occurs when the number of locks reaches 40 percent of the value specified for **locks**.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="39e65-131">Segurança</span><span class="sxs-lookup"><span data-stu-id="39e65-131">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="39e65-132">Permissões</span><span class="sxs-lookup"><span data-stu-id="39e65-132">Permissions</span></span>  
 <span data-ttu-id="39e65-133">Permissões de execução sem parâmetros ou com apenas o primeiro parâmetro em **sp_configure** são concedidas a todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="39e65-133">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="39e65-134">Para executar **sp_configure** com ambos os parâmetros para alterar uma opção de configuração ou executar a instrução RECONFIGURE, o usuário deve ter a permissão ALTER SETTINGS no nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="39e65-134">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="39e65-135">A permissão ALTER SETTINGS é implicitamente mantida pelas funções de servidor fixas **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="39e65-135">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="39e65-136">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="39e65-136">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-locks-option"></a><span data-ttu-id="39e65-137">Para configurar a opção locks</span><span class="sxs-lookup"><span data-stu-id="39e65-137">To configure the locks option</span></span>  
  
1.  <span data-ttu-id="39e65-138">No Pesquisador de Objetos, clique com o botão direito do mouse em um servidor e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="39e65-138">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="39e65-139">Clique no nó **Avançado** .</span><span class="sxs-lookup"><span data-stu-id="39e65-139">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="39e65-140">No item **Paralelismo**, digite o valor desejado para a opção **locks** .</span><span class="sxs-lookup"><span data-stu-id="39e65-140">Under **Parallelism**, type the desired value for the **locks** option.</span></span>  
  
     <span data-ttu-id="39e65-141">Use a opção **locks** para definir o número máximo de bloqueios disponíveis, limitando a quantidade de memória que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usa para eles.</span><span class="sxs-lookup"><span data-stu-id="39e65-141">Use the **locks** option to set the maximum number of available locks, thereby limiting the amount of memory [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses for them.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="39e65-142">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="39e65-142">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-locks-option"></a><span data-ttu-id="39e65-143">Para configurar a opção locks</span><span class="sxs-lookup"><span data-stu-id="39e65-143">To configure the locks option</span></span>  
  
1.  <span data-ttu-id="39e65-144">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39e65-144">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="39e65-145">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="39e65-145">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="39e65-146">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="39e65-146">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="39e65-147">Este exemplo mostra como usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para definir o valor da opção `locks` para definir o número de bloqueios disponíveis para todos os usuários como `20000`.</span><span class="sxs-lookup"><span data-stu-id="39e65-147">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `locks` option to set the number of locks available for all users to `20000`.</span></span>  
  
```sql  
Use AdventureWorks2012 ;  
GO  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'locks', 20000;  
GO  
RECONFIGURE;  
GO  
```  
  
 <span data-ttu-id="39e65-148">Para obter mais informações, veja [Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="39e65-148">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-locks-option"></a><a name="FollowUp"></a> <span data-ttu-id="39e65-149">Acompanhamento: depois de configurar a opção bloqueios</span><span class="sxs-lookup"><span data-stu-id="39e65-149">Follow Up: After you configure the locks option</span></span>  
 <span data-ttu-id="39e65-150">O servidor deve ser reiniciado para que a configuração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="39e65-150">The server must be restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39e65-151">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="39e65-151">See Also</span></span>  
 <span data-ttu-id="39e65-152">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="39e65-152">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="39e65-153">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="39e65-153">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="39e65-154">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="39e65-154">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
