---
title: Configurar a opção de configuração de servidor user connections | Microsoft Docs
ms.custom: ''
ms.date: 12/02/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- simultaneous connections [SQL Server]
- user connections option [SQL Server]
- users [SQL Server], simultaneous connections
- maximum number of simultaneous user connections
- connections [SQL Server], simultaneous
ms.assetid: 53beee6e-59fe-4276-9abb-8f1cec2a3508
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 68fbb4a17de131c128b5b1bb7cfb35a33b9d0037
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569643"
---
# <a name="configure-the-user-connections-server-configuration-option"></a><span data-ttu-id="6cf46-102">Configurar a opção de configuração de servidor user connections</span><span class="sxs-lookup"><span data-stu-id="6cf46-102">Configure the user connections Server Configuration Option</span></span>
  <span data-ttu-id="6cf46-103">Este tópico descreve como definir a opção de configuração de servidor **user connections** no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6cf46-103">This topic describes how to set the **user connections** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="6cf46-104">A opção **user connections** especifica o número máximo de conexões de usuário simultâneas permitido em uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6cf46-104">The **user connections** option specifies the maximum number of simultaneous user connections that are allowed on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6cf46-105">O número real de conexões de usuário permitidas depende também da versão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que você está usando e dos limites de seu aplicativo ou aplicativos e hardware.</span><span class="sxs-lookup"><span data-stu-id="6cf46-105">The actual number of user connections allowed also depends on the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you are using, and also the limits of your application or applications and hardware.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6cf46-106">permite um máximo de 32.767 conexões de usuário.</span><span class="sxs-lookup"><span data-stu-id="6cf46-106">allows a maximum of 32,767 user connections.</span></span> <span data-ttu-id="6cf46-107">Como **conexões de usuário** é uma opção dinâmica (autoconfigurável), o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ajusta o número máximo de conexões de usuário automaticamente conforme o necessário, até o valor máximo permitido.</span><span class="sxs-lookup"><span data-stu-id="6cf46-107">Because **user connections** is a dynamic (self-configuring) option, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] adjusts the maximum number of user connections automatically as needed, up to the maximum value allowable.</span></span> <span data-ttu-id="6cf46-108">Por exemplo, se somente 10 usuários estiverem conectados, 10 objetos de conexão de usuário serão alocados.</span><span class="sxs-lookup"><span data-stu-id="6cf46-108">For example, if only 10 users are logged in, 10 user connection objects are allocated.</span></span> <span data-ttu-id="6cf46-109">Na maioria dos casos, não é necessário alterar o valor dessa opção.</span><span class="sxs-lookup"><span data-stu-id="6cf46-109">In most cases, you do not have to change the value for this option.</span></span> <span data-ttu-id="6cf46-110">O padrão é 0, o que significa que as permitidas conexões máximas (32,767) de usuário são permitidas.</span><span class="sxs-lookup"><span data-stu-id="6cf46-110">The default is 0, which means that the maximum (32,767) user connections are allowed.</span></span>  
  
 <span data-ttu-id="6cf46-111">Para determinar o número máximo de conexões de usuário que seu sistema permite, você pode executar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) ou pode consultar a exibição de catálogo [sys.configuration](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="6cf46-111">To determine the maximum number of user connections that your system allows, you can execute [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) or query the [sys.configuration](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) catalog view.</span></span>  
  
 <span data-ttu-id="6cf46-112">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="6cf46-112">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6cf46-113">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="6cf46-113">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6cf46-114">Recomendações</span><span class="sxs-lookup"><span data-stu-id="6cf46-114">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="6cf46-115">Segurança</span><span class="sxs-lookup"><span data-stu-id="6cf46-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6cf46-116">**Para configurar a opção user connections usando:**</span><span class="sxs-lookup"><span data-stu-id="6cf46-116">**To configure the user connections option, using:**</span></span>  
  
     [<span data-ttu-id="6cf46-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6cf46-117">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6cf46-118">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6cf46-118">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="6cf46-119">**Acompanhamento:**  [depois de configurar a opção user connections](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="6cf46-119">**Follow Up:**  [After you configure the user connections option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6cf46-120">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="6cf46-120">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="6cf46-121">Recomendações</span><span class="sxs-lookup"><span data-stu-id="6cf46-121">Recommendations</span></span>  
  
-   <span data-ttu-id="6cf46-122">Esta é uma opção avançada e deve ser alterada somente por um administrador de banco de dados experiente ou técnico certificado do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6cf46-122">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="6cf46-123">O uso da opção **user connections** ajuda a evitar sobrecarregar o servidor com muitas conexões simultâneas.</span><span class="sxs-lookup"><span data-stu-id="6cf46-123">Using the **user connections** option helps avoid overloading the server with too many concurrent connections.</span></span> <span data-ttu-id="6cf46-124">Você pode calcular o número de conexões com base no sistema e nos requisitos do usuário.</span><span class="sxs-lookup"><span data-stu-id="6cf46-124">You can estimate the number of connections based on system and user requirements.</span></span> <span data-ttu-id="6cf46-125">Por exemplo, em um sistema com muitos usuários, cada usuário não requer geralmente uma conexão exclusiva.</span><span class="sxs-lookup"><span data-stu-id="6cf46-125">For example, on a system with many users, each user would not usually require a unique connection.</span></span> <span data-ttu-id="6cf46-126">As conexões podem ser compartilhadas entre os usuários.</span><span class="sxs-lookup"><span data-stu-id="6cf46-126">Connections can be shared among users.</span></span> <span data-ttu-id="6cf46-127">Usuários que executam aplicativos OLE DB precisam de uma conexão para cada objeto de conexão aberto, usuários que executam aplicativos ODBC (Conectividade Aberta de Banco de Dados) precisam de uma conexão para cada atividade gerenciada no aplicativo e usuários que executam aplicativos DB-Library precisam de uma conexão para cada processo iniciado que chama a função **dbopen** do DB-Library.</span><span class="sxs-lookup"><span data-stu-id="6cf46-127">Users running OLE DB applications need a connection for each open connection object, users running Open Database Connectivity (ODBC) applications need a connection for each active connection handle in the application, and users running DB-Library applications need one connection for each process started that calls the DB-Library **dbopen** function.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="6cf46-128">Se for necessário usar essa opção, não defina o valor muito alto, porque cada conexão tem sobrecarga, independentemente da conexão que está sendo usada.</span><span class="sxs-lookup"><span data-stu-id="6cf46-128">If you must use this option, do not set the value too high, because each connection has overhead regardless of whether the connection is being used.</span></span> <span data-ttu-id="6cf46-129">Se o número máximo de conexões de usuário for excedido, você receberá uma mensagem de erro e não poderá se conectar até que outra conexão fique disponível.</span><span class="sxs-lookup"><span data-stu-id="6cf46-129">If you exceed the maximum number of user connections, you receive an error message and are not able to connect until another connection becomes available.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6cf46-130">Segurança</span><span class="sxs-lookup"><span data-stu-id="6cf46-130">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6cf46-131">Permissões</span><span class="sxs-lookup"><span data-stu-id="6cf46-131">Permissions</span></span>  
 <span data-ttu-id="6cf46-132">Permissões de execução sem parâmetros ou com apenas o primeiro parâmetro em **sp_configure** são concedidas a todos os usuários por padrão.</span><span class="sxs-lookup"><span data-stu-id="6cf46-132">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="6cf46-133">Para executar **sp_configure** com ambos os parâmetros para alterar uma opção de configuração ou executar a instrução RECONFIGURE, o usuário deve ter a permissão ALTER SETTINGS no nível do servidor.</span><span class="sxs-lookup"><span data-stu-id="6cf46-133">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="6cf46-134">A permissão ALTER SETTINGS é implicitamente mantida pelas funções de servidor fixas **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="6cf46-134">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6cf46-135">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6cf46-135">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-user-connections-option"></a><span data-ttu-id="6cf46-136">Para configurar a opção user connections</span><span class="sxs-lookup"><span data-stu-id="6cf46-136">To configure the user connections option</span></span>  
  
1.  <span data-ttu-id="6cf46-137">No Pesquisador de Objetos, clique com o botão direito do mouse em um servidor e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="6cf46-137">In Object Explorer, right-click a server and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="6cf46-138">Clique no nó **Conexões** .</span><span class="sxs-lookup"><span data-stu-id="6cf46-138">Click the **Connections** node.</span></span>  
  
3.  <span data-ttu-id="6cf46-139">Em **Conexões**, na caixa **Número máximo de conexões simultâneas** , digite ou selecione um valor de 0 a 32767 para definir o número máximo de usuários que terão permissão para se conectar simultaneamente à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6cf46-139">Under **Connections**, in the **Max number of concurrent connections** box, type or select a value from 0 through 32767 to set the maximum number of users that are allowed to connect simultaneously to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
4.  <span data-ttu-id="6cf46-140">Reinicie o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6cf46-140">Restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6cf46-141">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6cf46-141">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-user-connections-option"></a><span data-ttu-id="6cf46-142">Para configurar a opção user connections</span><span class="sxs-lookup"><span data-stu-id="6cf46-142">To configure the user connections option</span></span>  
  
1.  <span data-ttu-id="6cf46-143">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6cf46-143">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6cf46-144">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="6cf46-144">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6cf46-145">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="6cf46-145">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="6cf46-146">Este exemplo mostra como usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para configurar o valor da opção `user connections` como `325` usuários.</span><span class="sxs-lookup"><span data-stu-id="6cf46-146">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the value of the `user connections` option to `325` users.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'user connections', 325 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="6cf46-147">Para obter mais informações, veja [Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6cf46-147">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-user-connections-option"></a><a name="FollowUp"></a> <span data-ttu-id="6cf46-148">Acompanhamento: depois de configurar a opção user connections</span><span class="sxs-lookup"><span data-stu-id="6cf46-148">Follow Up: After you configure the user connections option</span></span>  
 <span data-ttu-id="6cf46-149">O servidor deve ser reiniciado para que a configuração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="6cf46-149">The server must be restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cf46-150">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6cf46-150">See Also</span></span>  
 <span data-ttu-id="6cf46-151">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6cf46-151">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="6cf46-152">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6cf46-152">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="6cf46-153">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6cf46-153">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
