---
title: Exibir e modificar propriedades de Publicador e Distribuidor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- viewing replication properties
- Distributors [SQL Server replication], modifying
- modifying replication properties, Distributors
- Distributors [SQL Server replication], properties
ms.assetid: 5dae1d59-c377-4c6e-adc9-b68c5b328f79
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 571f6f3a0d44f0fc87c67885249fca441776946d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571923"
---
# <a name="view-and-modify-distributor-and-publisher-properties"></a><span data-ttu-id="74ea7-102">Exibir e modificar propriedades de Publicador e Distribuidor</span><span class="sxs-lookup"><span data-stu-id="74ea7-102">View and Modify Distributor and Publisher Properties</span></span>
  <span data-ttu-id="74ea7-103">Este tópico descreve como exibir e modificar propriedades do Distribuidor e do Publicador no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], ou RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="74ea7-103">This topic describes how to view and modify Distributor and Publisher properties in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="74ea7-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="74ea7-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="74ea7-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="74ea7-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="74ea7-106">Recomendações</span><span class="sxs-lookup"><span data-stu-id="74ea7-106">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="74ea7-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="74ea7-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="74ea7-108">**Para exibir e modificar as propriedades do Distribuidor e do Publicador, usando:**</span><span class="sxs-lookup"><span data-stu-id="74ea7-108">**To view and modify Distributor and Publisher properties, using:**</span></span>  
  
     [<span data-ttu-id="74ea7-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="74ea7-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="74ea7-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="74ea7-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="74ea7-111">RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="74ea7-111">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="74ea7-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="74ea7-112">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="74ea7-113">Recomendações</span><span class="sxs-lookup"><span data-stu-id="74ea7-113">Recommendations</span></span>  
  
-   <span data-ttu-id="74ea7-114">Nas versões de Publicadores anteriores ao [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], um usuário na função de servidor fixa **sysadmin** pode registrar Assinantes na página **Assinantes**.</span><span class="sxs-lookup"><span data-stu-id="74ea7-114">For Publishers running versions prior to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], a user in the **sysadmin** fixed server role can register Subscribers on the **Subscribers** page.</span></span> <span data-ttu-id="74ea7-115">A partir do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], não é mais necessário registrar Assinantes explicitamente para replicação.</span><span class="sxs-lookup"><span data-stu-id="74ea7-115">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], it is no longer necessary to explicitly register Subscribers for replication.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="74ea7-116">Segurança</span><span class="sxs-lookup"><span data-stu-id="74ea7-116">Security</span></span>  
 <span data-ttu-id="74ea7-117">Quando possível, solicite que os usuários insiram as credenciais de segurança em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="74ea7-117">When possible, prompt users to enter security credentials at runtime.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="74ea7-118">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="74ea7-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-and-modify-distributor-properties"></a><span data-ttu-id="74ea7-119">Para exibir e modificar as propriedades do Distribuidor</span><span class="sxs-lookup"><span data-stu-id="74ea7-119">To view and modify Distributor properties</span></span>  
  
1.  <span data-ttu-id="74ea7-120">Conecte-se ao Distribuidor no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]e, em seguida, expanda o nó de servidor.</span><span class="sxs-lookup"><span data-stu-id="74ea7-120">Connect to the Distributor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="74ea7-121">Clique com o botão direito do mouse na pasta **Replicação** e em seguida clique em **Propriedades do Distribuidor**.</span><span class="sxs-lookup"><span data-stu-id="74ea7-121">Right-click the **Replication** folder, and then click **Distributor Properties**.</span></span>  
  
3.  <span data-ttu-id="74ea7-122">Veja e modifique as propriedades na caixa de diálogo **Propriedades do Distribuidor – \<Distributor>** .</span><span class="sxs-lookup"><span data-stu-id="74ea7-122">View and modify properties in the **Distributor Properties - \<Distributor>** dialog box.</span></span>  
  
    -   <span data-ttu-id="74ea7-123">Para exibir e modificar as propriedades de um banco de dados de distribuição, clique no botão de propriedades ( **...** ) do banco de dados na página **Geral** da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="74ea7-123">To view and modify properties for a distribution database, click the properties button (**...**) for the database on the **General** page of thedialog box.</span></span>  
  
    -   <span data-ttu-id="74ea7-124">Para exibir e modificar as propriedades do Publicador associado ao Distribuidor, clique no botão de propriedades ( **…** ) para o Publicador na página **Publicadores** da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="74ea7-124">To view and modify Publisher properties associated with the Distributor, click the properties button (**...**) for the Publisher on the **Publishers** page of the dialog box.</span></span>  
  
    -   <span data-ttu-id="74ea7-125">Para acessar os perfis para os agentes de replicação, clique no botão **Padrões de Perfil** na página **Geral** da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="74ea7-125">To access profiles for replication agents, click the **Profile Defaults** button on the **General** page of the dialog box.</span></span> <span data-ttu-id="74ea7-126">Para saber mais, confira [Replication Agent Profiles](agents/replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="74ea7-126">For more information, see [Replication Agent Profiles](agents/replication-agent-profiles.md).</span></span>  
  
    -   <span data-ttu-id="74ea7-127">Para alterar a senha da conta usada quando os procedimentos administrativos armazenados são executados no Publicador e para atualizar as informações no Distribuidor, digite uma senha nova nas caixas **Senha** e **Confirmar senha** na página **Publicadores** da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="74ea7-127">To change the password for the account used when administrative stored procedures execute at the Publisher and update information at the Distributor, enter a new password in the **Password** and **Confirm password** boxes on the **Publishers** page of the dialog box.</span></span> <span data-ttu-id="74ea7-128">Para obter mais informações, consulte [Proteger o Distribuidor](security/secure-the-distributor.md).</span><span class="sxs-lookup"><span data-stu-id="74ea7-128">For more information, see [Secure the Distributor](security/secure-the-distributor.md).</span></span>  
  
4.  <span data-ttu-id="74ea7-129">Modifique propriedades, se necessário, depois clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="74ea7-129">Modify any properties if necessary, and then click **OK**.</span></span>  
  
#### <a name="to-view-and-modify-publisher-properties"></a><span data-ttu-id="74ea7-130">Para exibir e modificar as propriedades do Publicador</span><span class="sxs-lookup"><span data-stu-id="74ea7-130">To view and modify Publisher properties</span></span>  
  
1.  <span data-ttu-id="74ea7-131">Conecte-se ao Publicador no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]e expanda o nó de servidor.</span><span class="sxs-lookup"><span data-stu-id="74ea7-131">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="74ea7-132">Clique com o botão direito do mouse na pasta **Replicação** e, em seguida, em **Propriedades do Publicador**.</span><span class="sxs-lookup"><span data-stu-id="74ea7-132">Right-click the **Replication** folder, and then click **Publisher Properties**.</span></span>  
  
3.  <span data-ttu-id="74ea7-133">Exiba e modifique as propriedades na caixa de diálogo \*\* \< Publisher > Propriedades do Publicador\*\* .</span><span class="sxs-lookup"><span data-stu-id="74ea7-133">View and modify properties in the **Publisher Properties - \< Publisher >** dialog box.</span></span>  
  
    -   <span data-ttu-id="74ea7-134">Um usuário na função de servidor fixa **sysadmin** pode ativar bancos de dados para replicação na página **Bancos de Dados de Publicação** .</span><span class="sxs-lookup"><span data-stu-id="74ea7-134">A user in the **sysadmin** fixed server role can enable databases for replication on the **Publication Databases** page.</span></span> <span data-ttu-id="74ea7-135">Habilitando um banco de dados não publica esse banco de dados, mas permite que qualquer usuário na função de banco de dados fixa **db_owner** para aquele banco de dados crie uma ou mais publicações no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="74ea7-135">Enabling a database does not publish that database; rather, it allows any user in the **db_owner** fixed database role for that database to create one or more publications in the database.</span></span>  
  
4.  <span data-ttu-id="74ea7-136">Modifique propriedades, se necessário, depois clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="74ea7-136">Modify any properties if necessary, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="74ea7-137">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="74ea7-137">Using Transact-SQL</span></span>  
 <span data-ttu-id="74ea7-138">As propriedades do Publicador e do Distribuidor podem ser exibidas programaticamente usando os procedimentos armazenados de replicação.</span><span class="sxs-lookup"><span data-stu-id="74ea7-138">Publisher and Distributor properties can be viewed programmatically using replication stored procedures.</span></span>  
  
#### <a name="to-view-distributor-and-distribution-database-properties"></a><span data-ttu-id="74ea7-139">Para exibir as propriedades do banco de dados de distribuição e do Distribuidor</span><span class="sxs-lookup"><span data-stu-id="74ea7-139">To view Distributor and distribution database properties</span></span>  
  
1.  <span data-ttu-id="74ea7-140">Execute [sp_helpdistributor](/sql/relational-databases/system-stored-procedures/sp-helpdistributor-transact-sql) para retornar informações sobre o Distribuidor, banco de dados de distribuição e diretório de funcionamento.</span><span class="sxs-lookup"><span data-stu-id="74ea7-140">Execute [sp_helpdistributor](/sql/relational-databases/system-stored-procedures/sp-helpdistributor-transact-sql) to return information about the Distributor, distribution database, and working directory.</span></span>  
  
2.  <span data-ttu-id="74ea7-141">Execute [sp_helpdistributiondb](/sql/relational-databases/system-stored-procedures/sp-helpdistributiondb-transact-sql) para retornar propriedades de um banco de dados de distribuição especificado.</span><span class="sxs-lookup"><span data-stu-id="74ea7-141">Execute [sp_helpdistributiondb](/sql/relational-databases/system-stored-procedures/sp-helpdistributiondb-transact-sql) to return properties of a specified distribution database.</span></span>  
  
#### <a name="to-change-distributor-and-distribution-database-properties"></a><span data-ttu-id="74ea7-142">Para alterar as propriedades do banco de dados de distribuição e do Distribuidor</span><span class="sxs-lookup"><span data-stu-id="74ea7-142">To change Distributor and distribution database properties</span></span>  
  
1.  <span data-ttu-id="74ea7-143">No Distribuidor, execute [sp_changedistributor_property](/sql/relational-databases/system-stored-procedures/sp-changedistributor-property-transact-sql) para modificar as propriedades do Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="74ea7-143">At the Distributor, execute [sp_changedistributor_property](/sql/relational-databases/system-stored-procedures/sp-changedistributor-property-transact-sql) to modify Distributor properties.</span></span>  
  
2.  <span data-ttu-id="74ea7-144">No Distribuidor, execute [sp_changedistributiondb](/sql/relational-databases/system-stored-procedures/sp-changedistributiondb-transact-sql) para modificar as propriedades do banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="74ea7-144">At the Distributor, execute [sp_changedistributiondb](/sql/relational-databases/system-stored-procedures/sp-changedistributiondb-transact-sql) to modify distribution database properties.</span></span>  
  
3.  <span data-ttu-id="74ea7-145">No Distribuidor, execute [sp_changedistributor_password](/sql/relational-databases/system-stored-procedures/sp-changedistributor-password-transact-sql) para alterar a senha do Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="74ea7-145">At the Distributor, execute [sp_changedistributor_password](/sql/relational-databases/system-stored-procedures/sp-changedistributor-password-transact-sql) to change the Distributor password.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="74ea7-146">Quando possível, solicite que os usuários insiram as credenciais de segurança em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="74ea7-146">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="74ea7-147">Se você precisar armazenar credenciais em um arquivo de script, proteja o arquivo para evitar acesso não autorizado.</span><span class="sxs-lookup"><span data-stu-id="74ea7-147">If you must store credentials in a script file, secure the file to prevent unauthorized access.</span></span>  
  
4.  <span data-ttu-id="74ea7-148">No Distribuidor, execute [sp_changedistpublisher](/sql/relational-databases/system-stored-procedures/sp-changedistpublisher-transact-sql) para alterar as propriedades de um Publicador usando o Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="74ea7-148">At the Distributor, execute [sp_changedistpublisher](/sql/relational-databases/system-stored-procedures/sp-changedistpublisher-transact-sql) to change the properties of a Publisher using the Distributor.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="74ea7-149">Exemplos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="74ea7-149">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="74ea7-150">O seguinte exemplo de script [!INCLUDE[tsql](../../includes/tsql-md.md)] retorna as informações sobre o Distribuidor e o banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="74ea7-150">The following example [!INCLUDE[tsql](../../includes/tsql-md.md)] script returns information about the Distributor and distribution database.</span></span>  
  
 [!code-sql[HowTo#sp_helpdistributor](../../snippets/tsql/SQL15/replication/howto/tsql/changedistpub.sql#sp_helpdistributor)]  
  
 [!code-sql[HowTo#sp_helpdistributiondb](../../snippets/tsql/SQL15/replication/howto/tsql/changedistpub.sql#sp_helpdistributiondb)]  
  
 <span data-ttu-id="74ea7-151">Esse exemplo altera os períodos de retenção para o Distribuidor, a senha usada quando conectando-se ao Distribuidor, e o intervalo no qual o Distribuidor verifica o status de vários agentes de replicação (também conhecidos como intervalo de heartbeat).</span><span class="sxs-lookup"><span data-stu-id="74ea7-151">This example changes retention periods for the Distributor, the password used when connecting to the Distributor, and the interval at which the Distributor checks the status of various replication agents (also known as the heartbeat interval).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="74ea7-152">Quando possível, solicite que os usuários insiram as credenciais de segurança em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="74ea7-152">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="74ea7-153">Se você precisar armazenar credenciais em um arquivo de script, proteja o arquivo para evitar acesso não autorizado.</span><span class="sxs-lookup"><span data-stu-id="74ea7-153">If you must store credentials in a script file, secure the file to prevent unauthorized access.</span></span>  
  
 [!code-sql[HowTo#sp_changedistributor_property](../../snippets/tsql/SQL15/replication/howto/tsql/changedistpub.sql#sp_changedistributor_property)]  
  
 [!code-sql[HowTo#sp_changedistributiondb](../../snippets/tsql/SQL15/replication/howto/tsql/changedistpub.sql#sp_changedistributiondb)]  
  
 [!code-sql[HowTo#sp_changedistributor_password](../../snippets/tsql/SQL15/replication/howto/tsql/changedistpub.sql#sp_changedistributor_password)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="74ea7-154">Usando o RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="74ea7-154">Using Replication Management Objects (RMO)</span></span>  
  
#### <a name="to-view-and-modify-distributor-properties"></a><span data-ttu-id="74ea7-155">Para exibir e modificar as propriedades do Distribuidor</span><span class="sxs-lookup"><span data-stu-id="74ea7-155">To view and modify Distributor properties</span></span>  
  
1.  <span data-ttu-id="74ea7-156">Crie uma conexão com o Distribuidor usando a classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="74ea7-156">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="74ea7-157">Criar uma instância da classe <xref:Microsoft.SqlServer.Replication.ReplicationServer>.</span><span class="sxs-lookup"><span data-stu-id="74ea7-157">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationServer> class.</span></span> <span data-ttu-id="74ea7-158">Passe o objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> da etapa 1.</span><span class="sxs-lookup"><span data-stu-id="74ea7-158">Pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object from step 1.</span></span>  
  
3.  <span data-ttu-id="74ea7-159">(Opcional) Verificar a propriedade <xref:Microsoft.SqlServer.Replication.ReplicationServer.IsDistributor%2A> para verificar se o servidor conectado no momento é um Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="74ea7-159">(Optional) Check the <xref:Microsoft.SqlServer.Replication.ReplicationServer.IsDistributor%2A> property to verify that the currently connected server is a Distributor.</span></span>  
  
4.  <span data-ttu-id="74ea7-160">Chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> para obter as propriedades do servidor.</span><span class="sxs-lookup"><span data-stu-id="74ea7-160">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> method to get the properties from the server.</span></span>  
  
5.  <span data-ttu-id="74ea7-161">(Opcional) Para alterar as propriedades, defina um novo valor para uma ou mais propriedades do Distribuidor que podem ser definidas no objeto <xref:Microsoft.SqlServer.Replication.ReplicationServer> .</span><span class="sxs-lookup"><span data-stu-id="74ea7-161">(Optional) To change properties, set a new value for one or more of the Distributor properties that can be set on the <xref:Microsoft.SqlServer.Replication.ReplicationServer> object.</span></span>  
  
6.  <span data-ttu-id="74ea7-162">(Opcional) Se a propriedade <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> no objeto <xref:Microsoft.SqlServer.Replication.ReplicationServer> é definida para `true`, chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> para confirmar as alterações para o servidor.</span><span class="sxs-lookup"><span data-stu-id="74ea7-162">(Optional) If the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> property on the <xref:Microsoft.SqlServer.Replication.ReplicationServer> object is set to `true`, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method to commit the changes to the server.</span></span>  
  
#### <a name="to-view-and-modify-distribution-database-properties"></a><span data-ttu-id="74ea7-163">Para exibir e modificar as propriedades do banco de dados de distribuição</span><span class="sxs-lookup"><span data-stu-id="74ea7-163">To view and modify distribution database properties</span></span>  
  
1.  <span data-ttu-id="74ea7-164">Crie uma conexão com o Distribuidor usando a classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="74ea7-164">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="74ea7-165">Criar uma instância da classe <xref:Microsoft.SqlServer.Replication.DistributionDatabase>.</span><span class="sxs-lookup"><span data-stu-id="74ea7-165">Create an instance of the <xref:Microsoft.SqlServer.Replication.DistributionDatabase> class.</span></span> <span data-ttu-id="74ea7-166">Especifique o nome da propriedade e passe o objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> da etapa 1.</span><span class="sxs-lookup"><span data-stu-id="74ea7-166">Specify the name property and pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object from step 1.</span></span>  
  
3.  <span data-ttu-id="74ea7-167">Chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> para obter as propriedades do servidor.</span><span class="sxs-lookup"><span data-stu-id="74ea7-167">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties from the server.</span></span> <span data-ttu-id="74ea7-168">Se este método retornar `false`, o banco de dados com o nome especificado não existirá no servidor.</span><span class="sxs-lookup"><span data-stu-id="74ea7-168">If this method returns `false`, the database with the specified name does not exist on the server.</span></span>  
  
4.  <span data-ttu-id="74ea7-169">(Opcional) Para alterar propriedades, defina um novo valor para uma das propriedades <xref:Microsoft.SqlServer.Replication.DistributionDatabase> que podem ser definidas.</span><span class="sxs-lookup"><span data-stu-id="74ea7-169">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.DistributionDatabase> properties that can be set.</span></span>  
  
5.  <span data-ttu-id="74ea7-170">(Opcional) Se a propriedade <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> no objeto <xref:Microsoft.SqlServer.Replication.DistributionDatabase> é definida para `true`, chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> para confirmar as alterações para o servidor.</span><span class="sxs-lookup"><span data-stu-id="74ea7-170">(Optional) If the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> property on the <xref:Microsoft.SqlServer.Replication.DistributionDatabase> object is set to `true`, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method to commit the changes to the server.</span></span>  
  
#### <a name="to-view-and-modify-publisher-properties"></a><span data-ttu-id="74ea7-171">Para exibir e modificar as propriedades do Publicador</span><span class="sxs-lookup"><span data-stu-id="74ea7-171">To view and modify Publisher properties</span></span>  
  
1.  <span data-ttu-id="74ea7-172">Crie uma conexão com o Publicador usando a classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="74ea7-172">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="74ea7-173">Criar uma instância da classe <xref:Microsoft.SqlServer.Replication.DistributionPublisher>.</span><span class="sxs-lookup"><span data-stu-id="74ea7-173">Create an instance of the <xref:Microsoft.SqlServer.Replication.DistributionPublisher> class.</span></span> <span data-ttu-id="74ea7-174">Especifique a propriedade <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Name%2A> e passe o objeto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> da etapa 1.</span><span class="sxs-lookup"><span data-stu-id="74ea7-174">Specify the <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Name%2A> property and pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object from step 1.</span></span>  
  
3.  <span data-ttu-id="74ea7-175">(Opcional) Para alterar propriedades, defina um novo valor para uma das propriedades <xref:Microsoft.SqlServer.Replication.DistributionPublisher> que podem ser definidas.</span><span class="sxs-lookup"><span data-stu-id="74ea7-175">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.DistributionPublisher> properties that can be set.</span></span>  
  
4.  <span data-ttu-id="74ea7-176">(Opcional) Se a propriedade <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> no objeto <xref:Microsoft.SqlServer.Replication.DistributionPublisher> é definida para `true`, chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> para confirmar as alterações para o servidor.</span><span class="sxs-lookup"><span data-stu-id="74ea7-176">(Optional) If the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> property on the <xref:Microsoft.SqlServer.Replication.DistributionPublisher> object is set to `true`, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method to commit the changes to the server.</span></span>  
  
#### <a name="to-change-the-password-for-the-administrative-connection-from-the-publisher-to-the-distributor"></a><span data-ttu-id="74ea7-177">Para alterar a senha para a conexão administrativa do Publicador para o Distribuidor</span><span class="sxs-lookup"><span data-stu-id="74ea7-177">To change the password for the administrative connection from the Publisher to the Distributor</span></span>  
  
1.  <span data-ttu-id="74ea7-178">Crie uma conexão com o Distribuidor usando a classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="74ea7-178">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="74ea7-179">Criar uma instância da classe <xref:Microsoft.SqlServer.Replication.ReplicationServer>.</span><span class="sxs-lookup"><span data-stu-id="74ea7-179">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationServer> class.</span></span>  
  
3.  <span data-ttu-id="74ea7-180">Defina a propriedade <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> para a conexão criada na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="74ea7-180">Set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the connection created in step 1.</span></span>  
  
4.  <span data-ttu-id="74ea7-181">Chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> para obter as propriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="74ea7-181">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> method to get the properties of the object.</span></span>  
  
5.  <span data-ttu-id="74ea7-182">Chame o método <xref:Microsoft.SqlServer.Replication.ReplicationServer.ChangeDistributorPassword%2A> .</span><span class="sxs-lookup"><span data-stu-id="74ea7-182">Call the <xref:Microsoft.SqlServer.Replication.ReplicationServer.ChangeDistributorPassword%2A> method.</span></span> <span data-ttu-id="74ea7-183">Passe o novo valor de senha para o parâmetro *password* .</span><span class="sxs-lookup"><span data-stu-id="74ea7-183">Pass the new password value for the *password* parameter.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="74ea7-184">Quando possível, solicite que os usuários insiram as credenciais de segurança em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="74ea7-184">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="74ea7-185">Se for preciso armazenar credenciais, use os serviços [criptográficos](https://go.microsoft.com/fwlink/?LinkId=34733) fornecidos pelo [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework do Windows.</span><span class="sxs-lookup"><span data-stu-id="74ea7-185">If you must store credentials, use the [cryptographic services](https://go.microsoft.com/fwlink/?LinkId=34733) provided by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows .NET Framework.</span></span>  
  
6.  <span data-ttu-id="74ea7-186">(Opcional) Execute as etapas seguintes para alterar a senha em cada Publicador remoto que usa esse Distribuidor:</span><span class="sxs-lookup"><span data-stu-id="74ea7-186">(Optional) Perform the following steps to change the password at each remote Publisher that uses this Distributor:</span></span>  
  
    1.  <span data-ttu-id="74ea7-187">Crie uma conexão com o Publicador usando a classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="74ea7-187">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
    2.  <span data-ttu-id="74ea7-188">Criar uma instância da classe <xref:Microsoft.SqlServer.Replication.ReplicationServer>.</span><span class="sxs-lookup"><span data-stu-id="74ea7-188">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationServer> class.</span></span>  
  
    3.  <span data-ttu-id="74ea7-189">Defina a propriedade <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> para a conexão criada na etapa 6a.</span><span class="sxs-lookup"><span data-stu-id="74ea7-189">Set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the connection created in step 6a.</span></span>  
  
    4.  <span data-ttu-id="74ea7-190">Chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> para obter as propriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="74ea7-190">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> method to get the properties of the object.</span></span>  
  
    5.  <span data-ttu-id="74ea7-191">Chame o método <xref:Microsoft.SqlServer.Replication.ReplicationServer.ChangeDistributorPassword%2A> .</span><span class="sxs-lookup"><span data-stu-id="74ea7-191">Call the <xref:Microsoft.SqlServer.Replication.ReplicationServer.ChangeDistributorPassword%2A> method.</span></span> <span data-ttu-id="74ea7-192">Passe o novo valor de senha da etapa 5 para o parâmetro *password* .</span><span class="sxs-lookup"><span data-stu-id="74ea7-192">Pass the new password value from Step 5 for the *password* parameter.</span></span>  
  
###  <a name="example-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="74ea7-193">Exemplo (RMO)</span><span class="sxs-lookup"><span data-stu-id="74ea7-193">Example (RMO)</span></span>  
 <span data-ttu-id="74ea7-194">Este exemplo mostra como alterar a Distribuição e as propriedades do banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="74ea7-194">This example shows how to change Distribution and distribution database properties.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="74ea7-195">Para evitar credenciais de armazenagem no código, a nova senha do Distribuidor é fornecida a runtime.</span><span class="sxs-lookup"><span data-stu-id="74ea7-195">To avoid storing credentials in the code, the new Distributor password is supplied at runtime.</span></span>  
  
 [!code-csharp[HowTo#rmo_ChangeDistPub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_changedistpub)]  
  
 [!code-vb[HowTo#rmo_vb_ChangeDistPub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_changedistpub)]  
  
## <a name="see-also"></a><span data-ttu-id="74ea7-196">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="74ea7-196">See Also</span></span>  
 <span data-ttu-id="74ea7-197">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="74ea7-197">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span></span>  
 <span data-ttu-id="74ea7-198">[Desabilitar a publicação e a distribuição](disable-publishing-and-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="74ea7-198">[Disable Publishing and Distribution](disable-publishing-and-distribution.md) </span></span>  
 <span data-ttu-id="74ea7-199">[Configurar Distribuição](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="74ea7-199">[Configure Distribution](configure-distribution.md) </span></span>  
 <span data-ttu-id="74ea7-200">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="74ea7-200">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span></span>  
 <span data-ttu-id="74ea7-201">[Script de informações do Distribuidor e Publicador](administration/distributor-and-publisher-information-script.md) </span><span class="sxs-lookup"><span data-stu-id="74ea7-201">[Distributor and Publisher Information Script](administration/distributor-and-publisher-information-script.md) </span></span>  
 <span data-ttu-id="74ea7-202">[Replication System Stored Procedures Concepts](concepts/replication-system-stored-procedures-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="74ea7-202">[Replication System Stored Procedures Concepts](concepts/replication-system-stored-procedures-concepts.md) </span></span>  
 [<span data-ttu-id="74ea7-203">Exibir informações e executar tarefas usando o Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="74ea7-203">View Information and Perform Tasks using Replication Monitor</span></span>](monitor/view-information-and-perform-tasks-replication-monitor.md)  
  
  
