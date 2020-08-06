---
title: Exibir ou configurar opções de conexão de servidor remoto (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- remote servers [SQL Server], connection options
- servers [SQL Server], remote
- connections [SQL Server], remote servers
ms.assetid: 356d3e6b-8514-4bd2-a683-9de147949b2b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 73fe5e484d62cde025d1a560937e8cbcf5ec361d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679509"
---
# <a name="view-or-configure-remote-server-connection-options-sql-server"></a><span data-ttu-id="2113a-102">Exibir ou configurar opções de conexão de servidor remoto (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2113a-102">View or Configure Remote Server Connection Options (SQL Server)</span></span>
  <span data-ttu-id="2113a-103">Este tópico descreve como exibir ou configurar as opções de conexão de servidor remoto no nível de servidor no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2113a-103">This topic describes how to view or configure remote server connection options at the server level in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="2113a-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="2113a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2113a-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="2113a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2113a-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="2113a-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2113a-107">**Para exibir ou configurar opções de conexão de servidor remoto usando:**</span><span class="sxs-lookup"><span data-stu-id="2113a-107">**To view or configure remote server connection options, using:**</span></span>  
  
     [<span data-ttu-id="2113a-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2113a-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2113a-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2113a-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="2113a-110">**Acompanhamento:**  [depois de configurar opções de conexão de servidor remoto](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="2113a-110">**Follow Up:**  [After you configure remote server connection options](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2113a-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="2113a-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2113a-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="2113a-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2113a-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="2113a-113">Permissions</span></span>  
 <span data-ttu-id="2113a-114">A execução de **sp_serveroption** requer a permissão ALTER ANY LINKED SERVER no servidor.</span><span class="sxs-lookup"><span data-stu-id="2113a-114">Executing **sp_serveroption** requires ALTER ANY LINKED SERVER permission on the server.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2113a-115">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2113a-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-configure-remote-server-connection-options"></a><span data-ttu-id="2113a-116">Para exibir ou configurar opções de conexão de servidor remoto</span><span class="sxs-lookup"><span data-stu-id="2113a-116">To view or configure remote server connection options</span></span>  
  
1.  <span data-ttu-id="2113a-117">No Pesquisador de Objetos, clique com o botão direito do mouse em um servidor e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="2113a-117">In Object Explorer, right-click a server, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="2113a-118">Na caixa de diálogo **Propriedades do SQL Server – \<***server_name***>** , clique em **Conexões**.</span><span class="sxs-lookup"><span data-stu-id="2113a-118">In the **SQL Server Properties - \<***server_name***>** dialog box, click **Connections**.</span></span>  
  
3.  <span data-ttu-id="2113a-119">Na página **Conexões** , verifique as configurações de **Conexões de servidor remoto** e as modifique, se necessário.</span><span class="sxs-lookup"><span data-stu-id="2113a-119">On the **Connections** page, review the **Remote server connections** settings, and modify them if necessary.</span></span>  
  
4.  <span data-ttu-id="2113a-120">Repita os etapas 1 até 3, no outro servidor do par de servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="2113a-120">Repeat steps 1 through 3 on the other server of the remote server pair.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2113a-121">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2113a-121">Using Transact-SQL</span></span>  
  
#### <a name="to-view-remote-server-connection-options"></a><span data-ttu-id="2113a-122">Para exibir as opções de conexão de servidor remoto</span><span class="sxs-lookup"><span data-stu-id="2113a-122">To view remote server connection options</span></span>  
  
1.  <span data-ttu-id="2113a-123">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2113a-123">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2113a-124">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="2113a-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2113a-125">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="2113a-125">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="2113a-126">Este exemplo usa [sp_helpserver](/sql/relational-databases/system-stored-procedures/sp-helpserver-transact-sql) para retornar informações sobre todos os servidores remotos.</span><span class="sxs-lookup"><span data-stu-id="2113a-126">This example uses [sp_helpserver](/sql/relational-databases/system-stored-procedures/sp-helpserver-transact-sql) to return information about all remote servers.</span></span>  
  
```sql  
USE master;  
GO  
EXEC sp_helpserver ;  
```  
  
#### <a name="to-configure-remote-server-connection-options"></a><span data-ttu-id="2113a-127">Para configurar opções de conexão de servidor remoto</span><span class="sxs-lookup"><span data-stu-id="2113a-127">To configure remote server connection options</span></span>  
  
1.  <span data-ttu-id="2113a-128">Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2113a-128">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2113a-129">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="2113a-129">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2113a-130">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="2113a-130">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="2113a-131">Este exemplo mostra como usar [sp_serveroption](/sql/relational-databases/system-stored-procedures/sp-serveroption-transact-sql) para configurar um servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="2113a-131">This example shows how to use [sp_serveroption](/sql/relational-databases/system-stored-procedures/sp-serveroption-transact-sql) to configure a remote server.</span></span> <span data-ttu-id="2113a-132">O exemplo configura um servidor remoto correspondente a outra instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], `SEATTLE3`, para que seja compatível com ordenação com a instância local do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2113a-132">The example configures a remote server corresponding to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], `SEATTLE3`, to be collation compatible with the local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
```sql  
USE master;  
EXEC sp_serveroption 'SEATTLE3', 'collation compatible', 'true';  
```  
  
##  <a name="follow-up-after-you-configure-remote-server-connection-options"></a><a name="FollowUp"></a> <span data-ttu-id="2113a-133">Acompanhamento: depois de configurar opções de conexão de servidor remoto</span><span class="sxs-lookup"><span data-stu-id="2113a-133">Follow Up: After you configure remote server connection options</span></span>  
 <span data-ttu-id="2113a-134">O servidor remoto deve ser interrompido e reiniciado para que a configuração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="2113a-134">The remote server must be stopped and restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2113a-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2113a-135">See Also</span></span>  
 <span data-ttu-id="2113a-136">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2113a-136">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="2113a-137">[Servidores remotos](remote-servers.md) </span><span class="sxs-lookup"><span data-stu-id="2113a-137">[Remote Servers](remote-servers.md) </span></span>  
 <span data-ttu-id="2113a-138">[Servidores vinculados &#40;Mecanismo de Banco de Dados&#41;](../../relational-databases/linked-servers/linked-servers-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="2113a-138">[Linked Servers &#40;Database Engine&#41;](../../relational-databases/linked-servers/linked-servers-database-engine.md) </span></span>  
 <span data-ttu-id="2113a-139">[sp_linkedservers &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-linkedservers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2113a-139">[sp_linkedservers &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-linkedservers-transact-sql) </span></span>  
 <span data-ttu-id="2113a-140">[sp_helpserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpserver-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2113a-140">[sp_helpserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpserver-transact-sql) </span></span>  
 [<span data-ttu-id="2113a-141">sp_serveroption &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2113a-141">sp_serveroption &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-serveroption-transact-sql)  
  
  
