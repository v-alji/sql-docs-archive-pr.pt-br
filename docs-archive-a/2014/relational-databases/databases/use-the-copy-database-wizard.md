---
title: Usar o Assistente para Copiar Banco de Dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.cdw.transfermethod.f1
- sql12.swb.cdw.welcome.f1
- sql12.swb.cdw.packageconfiguration.f1
- sql12.swb.cdw.schedule.f1
- sql12.swb.cdw.destination.f1
- sql12.swb.cdw.complete.f1
- sql12.swb.cdw.destinationconfiguration.f1
- sql12.swb.cdw.selectdatabaseobjects.f1
- sql12.swb.cdw.databases.f1
- sql12.swb.cdw.source.f1
- sql12.swb.cdw.locationofsourcedbfiles.f1
helpviewer_keywords:
- Copy Database Wizard
- starting Copy Database Wizard
ms.assetid: 7a999fc7-0a26-4a0d-9eeb-db6fc794f3cb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0baaeef6cb196a67b2f615aa280b61b61fbc5119
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685187"
---
# <a name="use-the-copy-database-wizard"></a><span data-ttu-id="26e60-102">Usar o Assistente para Copiar Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="26e60-102">Use the Copy Database Wizard</span></span>
  <span data-ttu-id="26e60-103">O Assistente para Copiar Banco de Dados lhe permite migrar ou copiar bancos de dados e seus objetos facilmente de um servidor para outro, sem inatividade do servidor.</span><span class="sxs-lookup"><span data-stu-id="26e60-103">The Copy Database Wizard lets you move or copy databases and their objects easily from one server to another, with no server downtime.</span></span> <span data-ttu-id="26e60-104">Também é possível atualizar bancos de dados de uma versão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anterior a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26e60-104">You can also upgrade databases from a previous [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="26e60-105">Com esse assistente, é possível fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="26e60-105">By using this wizard, you can do the following:</span></span>  
  
-   <span data-ttu-id="26e60-106">Selecionar um servidor de origem e de destino.</span><span class="sxs-lookup"><span data-stu-id="26e60-106">Pick a source and destination server.</span></span>  
  
-   <span data-ttu-id="26e60-107">Selecionar bancos de dados para mover, copiar ou atualizar.</span><span class="sxs-lookup"><span data-stu-id="26e60-107">Select databases to move, copy or upgrade.</span></span>  
  
-   <span data-ttu-id="26e60-108">Especificar o local de arquivo para os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="26e60-108">Specify the file location for the databases.</span></span>  
  
-   <span data-ttu-id="26e60-109">Criar logons no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="26e60-109">Create logins on the destination server.</span></span>  
  
-   <span data-ttu-id="26e60-110">Copiar objetos, trabalhos, procedimentos armazenados definidos pelo usuário e mensagens de erro de suporte adicionais.</span><span class="sxs-lookup"><span data-stu-id="26e60-110">Copy additional supporting objects, jobs, user-defined stored procedures, and error messages.</span></span>  
  
-   <span data-ttu-id="26e60-111">Agendar a migração ou cópia dos bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="26e60-111">Schedule when to move or copy the databases.</span></span>  
  
 <span data-ttu-id="26e60-112">Além de copiar bancos de dados, é possível copiar os metadados associados, como, por exemplo, logons e objetos do banco de dados **mestre** exigidos por um banco de dados copiado.</span><span class="sxs-lookup"><span data-stu-id="26e60-112">In addition to copying databases, you can copy associated metadata, for example, logins and objects from the **master** database that are required by a copied database.</span></span>  
  
 <span data-ttu-id="26e60-113">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="26e60-113">**In This Topic**</span></span>  
  
-   <span data-ttu-id="26e60-114">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="26e60-114">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="26e60-115">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="26e60-115">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="26e60-116">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="26e60-116">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="26e60-117">Recomendações</span><span class="sxs-lookup"><span data-stu-id="26e60-117">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="26e60-118">Segurança</span><span class="sxs-lookup"><span data-stu-id="26e60-118">Security</span></span>](#Security)  
  
-   <span data-ttu-id="26e60-119">**Usando o Assistente para Copiar Banco de Dados para**</span><span class="sxs-lookup"><span data-stu-id="26e60-119">**Using the Copy Database Wizard to:**</span></span>  
  
     [<span data-ttu-id="26e60-120">Copiar, mover ou atualizar bancos de dados</span><span class="sxs-lookup"><span data-stu-id="26e60-120">Copy, Move, or Upgrade Databases</span></span>](#Copy_Move)  
  
-   <span data-ttu-id="26e60-121">**Acompanhamento: após a atualização:**</span><span class="sxs-lookup"><span data-stu-id="26e60-121">**Follow up, after upgrade:**</span></span>  
  
     [<span data-ttu-id="26e60-122">Depois de atualizar um banco de dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="26e60-122">After Upgrading a SQL Server Database</span></span>](#FollowUp)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="26e60-123">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="26e60-123">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="26e60-124">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="26e60-124">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="26e60-125">O Assistente para Copiar Banco de Dados não está disponível na edição Express.</span><span class="sxs-lookup"><span data-stu-id="26e60-125">The Copy Database Wizard is not available in the Express edition.</span></span>  
  
-   <span data-ttu-id="26e60-126">O Assistente para Copiar Banco de Dados não pode ser usado para copiar ou mover os bancos de dados a seguir.</span><span class="sxs-lookup"><span data-stu-id="26e60-126">The Copy Database Wizard cannot be used to copy or move the following databases.</span></span>  
  
    -   <span data-ttu-id="26e60-127">Bancos de dados do sistema</span><span class="sxs-lookup"><span data-stu-id="26e60-127">System databases</span></span>  
  
    -   <span data-ttu-id="26e60-128">Bancos de dados marcados para replicação.</span><span class="sxs-lookup"><span data-stu-id="26e60-128">Databases marked for replication.</span></span>  
  
    -   <span data-ttu-id="26e60-129">Bancos de dados marcados como Inacessível, Carregando, Offline, Recuperando, Suspeito ou em Modo de Emergência.</span><span class="sxs-lookup"><span data-stu-id="26e60-129">Databases marked Inaccessible, Loading, Offline, Recovering, Suspect, or in Emergency Mode.</span></span>  
  
-   <span data-ttu-id="26e60-130">Depois que um banco de dados é atualizado, ele não pode ser rebaixado para uma versão anterior.</span><span class="sxs-lookup"><span data-stu-id="26e60-130">After a database has been upgraded, it cannot be downgraded to a previous version.</span></span>  
  
-   <span data-ttu-id="26e60-131">Se você selecionar a opção **Migrar** , o assistente excluirá o banco de dados de origem automaticamente após migrá-lo.</span><span class="sxs-lookup"><span data-stu-id="26e60-131">If you select the **Move** option, the wizard deletes the source database automatically after moving the database.</span></span> <span data-ttu-id="26e60-132">Se você selecionar **Copiar** , o Assistente para Copiar Banco de Dados não excluirá o banco de dados de origem.</span><span class="sxs-lookup"><span data-stu-id="26e60-132">The Copy Database Wizard does not delete a source database if you select the **Copy** option.</span></span>  
  
-   <span data-ttu-id="26e60-133">Se você usar o método [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Object para mover o catálogo de texto completo, deverá repopular o índice após a movimentação.</span><span class="sxs-lookup"><span data-stu-id="26e60-133">If you use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Object method to move the full-text catalog, you must repopulate the index after the move.</span></span>  
  
-   <span data-ttu-id="26e60-134">O método desanexar-e-anexar desanexa o banco de dados, migra ou copia os arquivos .mdf, .ndf e .ldf do banco de dados e os reanexa ao banco de dados em um novo local.</span><span class="sxs-lookup"><span data-stu-id="26e60-134">The detach-and-attach method detaches the database, moves or copies the database .mdf, .ndf, .ldf files and reattaches the database in the new location.</span></span> <span data-ttu-id="26e60-135">Ao utilizar o método desanexar-e-anexar, para evitar perda ou inconsistência de dados, as sessões ativas não podem ser anexadas ao banco de dados que está sendo migrado ou copiado.</span><span class="sxs-lookup"><span data-stu-id="26e60-135">For the detach-and-attach method, to avoid data loss or inconsistency, active sessions cannot be attached to the database being moved or copied.</span></span> <span data-ttu-id="26e60-136">Se houver alguma sessão ativa, o Assistente para Copiar Banco de Dados não executará a operação de migração ou cópia.</span><span class="sxs-lookup"><span data-stu-id="26e60-136">If any active sessions exist, the Copy Database Wizard does not execute the move or copy operation.</span></span> <span data-ttu-id="26e60-137">No método [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Object, permitem-se sessões ativas porque o banco de dados nunca é colocado offline.</span><span class="sxs-lookup"><span data-stu-id="26e60-137">For the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Object method, active sessions are allowed because the database is never taken offline.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="26e60-138">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="26e60-138">Prerequisites</span></span>  
 <span data-ttu-id="26e60-139">Verifique se o SQL Server Agent foi iniciado no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="26e60-139">Ensure that SQL Server Agent is started on the destination server.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="26e60-140">Recomendações</span><span class="sxs-lookup"><span data-stu-id="26e60-140">Recommendations</span></span>  
  
-   <span data-ttu-id="26e60-141">Para garantir o desempenho perfeito de um banco de dados atualizado, execute sp_updatestats (atualização de estatísticas) nele.</span><span class="sxs-lookup"><span data-stu-id="26e60-141">To ensure optimal performance of an upgraded database, run sp_updatestats (update statistics) against the upgraded database.</span></span>  
  
-   <span data-ttu-id="26e60-142">Ao copiar um banco de dados para outra instância do servidor, para oferecer uma experiência consistente aos usuários e aplicativos, pode ser necessário recriar alguns ou todos os metadados do banco de dados, como logons e trabalhos, na outra instância de servidor.</span><span class="sxs-lookup"><span data-stu-id="26e60-142">When you copy a database to another server instance, to provide a consistent experience to users and applications, you might have to re-create some or all of the metadata for the database, such as logins and jobs, on the other server instance.</span></span> <span data-ttu-id="26e60-143">Para obter mais informações, consulte [Gerenciar metadados ao disponibilizar um banco de dados em outra instância do servidor &#40;SQL Server&#41;](manage-metadata-when-making-a-database-available-on-another-server.md).</span><span class="sxs-lookup"><span data-stu-id="26e60-143">For more information, see [Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](manage-metadata-when-making-a-database-available-on-another-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="26e60-144">Segurança</span><span class="sxs-lookup"><span data-stu-id="26e60-144">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="26e60-145">Permissões</span><span class="sxs-lookup"><span data-stu-id="26e60-145">Permissions</span></span>  
 <span data-ttu-id="26e60-146">Você deve ser membro da função de servidor fixa **sysadmin** em ambos os servidores, de origem e de destino.</span><span class="sxs-lookup"><span data-stu-id="26e60-146">You must be a member of the **sysadmin** fixed server role on both the source and destination servers.</span></span>  
  
##  <a name="copy-move-or-upgrade-databases"></a><a name="Copy_Move"></a><span data-ttu-id="26e60-147">Copiar, mover ou atualizar bancos de dados</span><span class="sxs-lookup"><span data-stu-id="26e60-147">Copy, Move or Upgrade Databases</span></span>  
  
1.  <span data-ttu-id="26e60-148">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , no Pesquisador de objetos, expanda **bancos**de dados, clique com o botão direito do mouse em um Database, aponte para **tarefas**e clique em **copiar banco de dados**.</span><span class="sxs-lookup"><span data-stu-id="26e60-148">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], in Object Explorer, expand **Databases**, right-click a database, point to **Tasks**, and then click **Copy Database**.</span></span>  
  
2.  <span data-ttu-id="26e60-149">Na página **Selecionar um Servidor de Origem** , especifique o servidor com o banco de dados que deseja mover ou copiar e digite as informações de logon.</span><span class="sxs-lookup"><span data-stu-id="26e60-149">From the **Select a Source Server** page, specify the server with the database to move or copy, and to enter login information.</span></span> <span data-ttu-id="26e60-150">Depois de selecionar o método de autenticação e digitar as informações de logon, clique em **Avançar** para estabelecer conexão com o servidor de origem.</span><span class="sxs-lookup"><span data-stu-id="26e60-150">After you select the authentication method and enter login information, click **Next** to establish the connection to the source server.</span></span> <span data-ttu-id="26e60-151">Essa conexão permanece aberta durante a sessão.</span><span class="sxs-lookup"><span data-stu-id="26e60-151">This connection remains open throughout the session.</span></span>  
  
     <span data-ttu-id="26e60-152">**Servidor de origem**</span><span class="sxs-lookup"><span data-stu-id="26e60-152">**Source server**</span></span>  
     <span data-ttu-id="26e60-153">Selecione o nome do servidor no qual está localizado o banco de dados ou os bancos que você deseja mover ou copiar ou clique no botão procurar (**...**) para localizar o servidor desejado.</span><span class="sxs-lookup"><span data-stu-id="26e60-153">Select the name of the server on which the database or databases you want to move or copy are located, or click the browse (**...**) button to locate the server you want.</span></span> <span data-ttu-id="26e60-154">O servidor deve ser pelo menos [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26e60-154">The server must be at least [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
     <span data-ttu-id="26e60-155">**Usar Autenticação do Windows**</span><span class="sxs-lookup"><span data-stu-id="26e60-155">**Use Windows Authentication**</span></span>  
     <span data-ttu-id="26e60-156">Permite que um usuário conecte por meio de uma conta de usuário [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="26e60-156">Allow a user to connect through a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows user account.</span></span>  
  
     <span data-ttu-id="26e60-157">**Usar Autenticação do SQL Server**</span><span class="sxs-lookup"><span data-stu-id="26e60-157">**Use SQL Server Authentication**</span></span>  
     <span data-ttu-id="26e60-158">Permite que um usuário conecte-se fornecendo um nome de usuário e uma senha de Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="26e60-158">Allow a user to connect by providing a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication user name and password.</span></span>  
  
     <span data-ttu-id="26e60-159">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="26e60-159">**User name**</span></span>  
     <span data-ttu-id="26e60-160">Digite o nome do usuário com o qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="26e60-160">Enter the user name to connect with.</span></span> <span data-ttu-id="26e60-161">Essa opção estará disponível somente se você decidiu se conectar usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="26e60-161">This option is only available if you have selected to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication .</span></span>  
  
     <span data-ttu-id="26e60-162">**Senha**</span><span class="sxs-lookup"><span data-stu-id="26e60-162">**Password**</span></span>  
     <span data-ttu-id="26e60-163">Digite a senha do logon.</span><span class="sxs-lookup"><span data-stu-id="26e60-163">Enter the password for the login.</span></span> <span data-ttu-id="26e60-164">Essa opção estará disponível somente se você decidiu conectar-se usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="26e60-164">This option is only available if you have selected to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
     <span data-ttu-id="26e60-165">**Próximo**</span><span class="sxs-lookup"><span data-stu-id="26e60-165">**Next**</span></span>  
     <span data-ttu-id="26e60-166">Conecta ao servidor e valida o usuário.</span><span class="sxs-lookup"><span data-stu-id="26e60-166">Connect to the server and validate the user.</span></span> <span data-ttu-id="26e60-167">Esse processo verifica se o usuário é membro da função de servidor fixa **sysadmin** no computador selecionado.</span><span class="sxs-lookup"><span data-stu-id="26e60-167">This process checks whether the user is a member of the **sysadmin** fixed server role on the selected computer.</span></span>  
  
3.  <span data-ttu-id="26e60-168">Na página **Selecione um Servidor de Destino** , especifique o servidor para o qual o banco de dados será movido ou copiado.</span><span class="sxs-lookup"><span data-stu-id="26e60-168">From the **Select a Destination Server** page, specify the server where the database will be moved or copied.</span></span> <span data-ttu-id="26e60-169">Se você definiu os servidores de origem e destino com a mesma instância de servidor, fará uma cópia de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="26e60-169">If you set the source and destination servers to the same server instance, you will make a copy of a database.</span></span> <span data-ttu-id="26e60-170">Nesse caso, renomeie o banco de dados em um ponto posterior do assistente.</span><span class="sxs-lookup"><span data-stu-id="26e60-170">In this case you must rename the database at a later point in the wizard.</span></span> <span data-ttu-id="26e60-171">O nome do banco de dados de origem poderá ser usado somente para o banco de dados copiado ou migrado se não houver conflitos de nome no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="26e60-171">The source database name can be used for the copied or moved database only if name conflicts do not exist on the destination server.</span></span> <span data-ttu-id="26e60-172">Se houver conflitos de nome, será preciso resolvê-los manualmente no servidor de destino para poder usar o nome do banco de dados de origem nele.</span><span class="sxs-lookup"><span data-stu-id="26e60-172">If name conflicts exist, you must resolve them manually on the destination server before you can use the source database name there.</span></span>  
  
     <span data-ttu-id="26e60-173">**Servidor de destino**</span><span class="sxs-lookup"><span data-stu-id="26e60-173">**Destination server**</span></span>  
     <span data-ttu-id="26e60-174">Selecione o nome do servidor para o qual os bancos de dados serão movidos ou copiados ou clique no botão procurar (**...**) para localizar um servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="26e60-174">Select the name of the server to which the database or databases will be moved or copied, or click the browse (**...**) button to locate a destination server.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="26e60-175">Você pode usar um destino que está em um servidor clusterizado; o Assistente para Copiar Banco de Dados garantirá que você selecionará somente unidades compartilhadas de um servidor de destino clusterizado.</span><span class="sxs-lookup"><span data-stu-id="26e60-175">You can use a destination that is a clustered server; the Copy Database Wizard will make sure you select only shared drives on a clustered destination server.</span></span>  
  
     <span data-ttu-id="26e60-176">**Usar Autenticação do Windows**</span><span class="sxs-lookup"><span data-stu-id="26e60-176">**Use Windows Authentication**</span></span>  
     <span data-ttu-id="26e60-177">Permite que um usuário conecte por meio de uma conta de usuário [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="26e60-177">Allow a user to connect through a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows user account.</span></span>  
  
     <span data-ttu-id="26e60-178">**Usar Autenticação do SQL Server**</span><span class="sxs-lookup"><span data-stu-id="26e60-178">**Use SQL Server Authentication**</span></span>  
     <span data-ttu-id="26e60-179">Permite que um usuário conecte-se fornecendo um nome de usuário e uma senha de Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="26e60-179">Allow a user to connect by providing a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication user name and password.</span></span>  
  
     <span data-ttu-id="26e60-180">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="26e60-180">**User name**</span></span>  
     <span data-ttu-id="26e60-181">Digite o nome do usuário com o qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="26e60-181">Enter the user name to connect with.</span></span> <span data-ttu-id="26e60-182">Essa opção estará disponível apenas se você selecionou a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="26e60-182">This option is only available if you have selected [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
     <span data-ttu-id="26e60-183">**Senha**</span><span class="sxs-lookup"><span data-stu-id="26e60-183">**Password**</span></span>  
     <span data-ttu-id="26e60-184">Digite a senha do logon.</span><span class="sxs-lookup"><span data-stu-id="26e60-184">Enter the password for the login.</span></span> <span data-ttu-id="26e60-185">Essa opção estará disponível apenas se você selecionou a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="26e60-185">This option is only available if you have selected [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
     <span data-ttu-id="26e60-186">**Próximo**</span><span class="sxs-lookup"><span data-stu-id="26e60-186">**Next**</span></span>  
     <span data-ttu-id="26e60-187">Conecta ao servidor e valida o usuário.</span><span class="sxs-lookup"><span data-stu-id="26e60-187">Connect to the server and validate the user.</span></span> <span data-ttu-id="26e60-188">Esse processo verifica se o usuário tem as permissões listadas acima nos computadores selecionados.</span><span class="sxs-lookup"><span data-stu-id="26e60-188">This process checks whether the user has the permissions listed above on the selected computers.</span></span>  
  
4.  <span data-ttu-id="26e60-189">Na página **Selecione o Método de Transferência** , selecione o método de transferência.</span><span class="sxs-lookup"><span data-stu-id="26e60-189">From the **Select a Transfer Method** page, select the transfer method.</span></span>  
  
     <span data-ttu-id="26e60-190">**Usar o método desanexar e anexar**</span><span class="sxs-lookup"><span data-stu-id="26e60-190">**Use the detach and attach method**</span></span>  
     <span data-ttu-id="26e60-191">Desanexa o banco de dados do servidor de origem, copia os arquivos do banco de dados (.mdf, .ndf e . ldf) para o servidor de destino e anexa o banco de dados ao servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="26e60-191">Detach the database from the source server, copy the database files (.mdf, .ndf, and .ldf) to the destination server, and attach the database at the destination server.</span></span> <span data-ttu-id="26e60-192">Esse método é geralmente o mais rápido porque o trabalho principal é ler o disco de origem e gravar o disco de destino.</span><span class="sxs-lookup"><span data-stu-id="26e60-192">This method is usually the faster method because the principal work is reading the source disk and writing the destination disk.</span></span> <span data-ttu-id="26e60-193">Nenhuma lógica do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é exigida para criar objetos dentro do banco de dados ou para criar estruturas de armazenamento de dados.</span><span class="sxs-lookup"><span data-stu-id="26e60-193">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logic is required to create objects within the database, or create data storage structures.</span></span> <span data-ttu-id="26e60-194">Porém, este método pode ser mais lento se o banco de dados contiver uma grande quantidade de espaço alocado, mas não utilizado.</span><span class="sxs-lookup"><span data-stu-id="26e60-194">This method can be slower, however, if the database contains a large amount of allocated but unused space.</span></span> <span data-ttu-id="26e60-195">Por exemplo, um banco de dados novo e praticamente vazio que seja criado alocando 100 MB, copia todos os 100 MB, mesmo que apenas 5 MB estejam completos.</span><span class="sxs-lookup"><span data-stu-id="26e60-195">For instance, a new and practically empty database that is created allocating 100 MB, copies the entire 100 MB, even if only 5 MB is full.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="26e60-196">Esse método torna o banco de dados indisponível para os usuários durante a transferência.</span><span class="sxs-lookup"><span data-stu-id="26e60-196">This method makes the database unavailable to users during the transfer.</span></span>  
  
     <span data-ttu-id="26e60-197">**Se ocorrer uma falha, anexar novamente o banco de dados de origem**</span><span class="sxs-lookup"><span data-stu-id="26e60-197">**If a failure occurs, reattach the source database**</span></span>  
     <span data-ttu-id="26e60-198">Quando um banco de dados é copiado, os arquivos do banco de dados original são sempre anexados novamente ao servidor de origem.</span><span class="sxs-lookup"><span data-stu-id="26e60-198">When a database is copied, the original database files are always reattached to the source server.</span></span> <span data-ttu-id="26e60-199">Use essa caixa para anexar novamente os arquivos originais ao banco de dados de origem se não for possível mover um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="26e60-199">Use this box to reattach original files to the source database if a database move cannot be completed.</span></span>  
  
     <span data-ttu-id="26e60-200">**Usar o método SQL Management Object**</span><span class="sxs-lookup"><span data-stu-id="26e60-200">**Use the SQL Management Object method**</span></span>  
     <span data-ttu-id="26e60-201">Esse método lê a definição de cada objeto de banco de dados no banco de dados de origem e cria cada objeto no banco de dados de destino.</span><span class="sxs-lookup"><span data-stu-id="26e60-201">This method reads the definition of each database object on the source database and creates each object in the destination database.</span></span> <span data-ttu-id="26e60-202">Depois ele transfere os dados das tabela de origem para as tabelas de destino, recriando os índices e os metadados.</span><span class="sxs-lookup"><span data-stu-id="26e60-202">Then it transfers the data from the source tables to the destination tables, recreating indexes and metadata.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="26e60-203">Os usuários do banco de dados podem continuar a acessar o banco de dados durante a transferência.</span><span class="sxs-lookup"><span data-stu-id="26e60-203">Database users can continue to access the database during the transfer.</span></span>  
  
5.  <span data-ttu-id="26e60-204">Na página **Selecionar Banco de Dados** , selecione o banco ou os bancos de dados que deseja mover ou copiar do servidor de origem para o servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="26e60-204">From the **Select Database** page, select the database or databases you want to move or copy from the source server to the destination server.</span></span> <span data-ttu-id="26e60-205">Consulte [limitações e restrições](#Restrictions) na seção ' antes de começar ' deste tópico.</span><span class="sxs-lookup"><span data-stu-id="26e60-205">See [Limitations and Restrictions](#Restrictions) in the 'Before You Begin' section of this topic.</span></span>  
  
     <span data-ttu-id="26e60-206">**Mover**</span><span class="sxs-lookup"><span data-stu-id="26e60-206">**Move**</span></span>  
     <span data-ttu-id="26e60-207">Mova o banco de dados para o servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="26e60-207">Move the database to the destination server.</span></span>  
  
     <span data-ttu-id="26e60-208">**Cópia**</span><span class="sxs-lookup"><span data-stu-id="26e60-208">**Copy**</span></span>  
     <span data-ttu-id="26e60-209">Copie o banco de dados no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="26e60-209">Copy the database to the destination server.</span></span>  
  
     <span data-ttu-id="26e60-210">**Origem**</span><span class="sxs-lookup"><span data-stu-id="26e60-210">**Source**</span></span>  
     <span data-ttu-id="26e60-211">Exibe os bancos de dados existentes no servidor de origem.</span><span class="sxs-lookup"><span data-stu-id="26e60-211">Displays the databases that exist on the source server.</span></span>  
  
     <span data-ttu-id="26e60-212">**Status**</span><span class="sxs-lookup"><span data-stu-id="26e60-212">**Status**</span></span>  
     <span data-ttu-id="26e60-213">Exibe **OK** se o banco de dados puder ser movido.</span><span class="sxs-lookup"><span data-stu-id="26e60-213">Displays **OK** if the database can be moved.</span></span> <span data-ttu-id="26e60-214">Caso contrário, exibe a razão pela qual o banco de dados não pode ser movido.</span><span class="sxs-lookup"><span data-stu-id="26e60-214">Otherwise displays the reason why the database cannot be moved.</span></span>  
  
     <span data-ttu-id="26e60-215">**Atualizar**</span><span class="sxs-lookup"><span data-stu-id="26e60-215">**Refresh**</span></span>  
     <span data-ttu-id="26e60-216">Atualize a lista de bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="26e60-216">Refresh the list of databases.</span></span>  
  
     <span data-ttu-id="26e60-217">**Próximo**</span><span class="sxs-lookup"><span data-stu-id="26e60-217">**Next**</span></span>  
     <span data-ttu-id="26e60-218">Inicie o processo de validação e avance para a próxima tela.</span><span class="sxs-lookup"><span data-stu-id="26e60-218">Start the validation process, and then move to the next screen.</span></span>  
  
6.  <span data-ttu-id="26e60-219">Na página **Configurar Banco de Dados de Destino** , altere o nome do banco de dados, se apropriado, e especifique o local e os nomes dos arquivos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="26e60-219">From the **Configure Destination Database** page, change the database name if appropriate and specify the location and names of the database files.</span></span> <span data-ttu-id="26e60-220">Essa página aparece uma vez para cada banco de dados que é movido ou copiado.</span><span class="sxs-lookup"><span data-stu-id="26e60-220">This page appears once for each database being moved or copied.</span></span>  
  
7.  <span data-ttu-id="26e60-221">Na página **Selecionar Objetos de Banco de Dados** , selecione os objetos para incluir na operação de movimentação ou cópia.</span><span class="sxs-lookup"><span data-stu-id="26e60-221">From the **Select Database Objects** page, select the objects to include in the move or copy operation.</span></span> <span data-ttu-id="26e60-222">Essa página está disponível apenas quando os servidores de origem e de destino forem diferentes.</span><span class="sxs-lookup"><span data-stu-id="26e60-222">This page is only available when the source and destination are different servers.</span></span> <span data-ttu-id="26e60-223">Para incluir um objeto, clique no nome do objeto na caixa **Objetos relacionados disponíveis** e clique no botão **>>** para mover o objeto para a caixa **Objetos relacionados selecionados** .</span><span class="sxs-lookup"><span data-stu-id="26e60-223">To include an object, click the object name in the **Available related objects** box, and then click the **>>** button to move the object to the **Selected related objects** box.</span></span> <span data-ttu-id="26e60-224">Para excluir um objeto, clique no nome do objeto na caixa **objetos relacionados selecionados** e, em seguida, clique no **<\<** botão para mover o objeto para a caixa **objetos relacionados disponíveis** .</span><span class="sxs-lookup"><span data-stu-id="26e60-224">To exclude an object, click the object name in the **Selected related objects** box, and then click the **<\<** button to move the object to the **Available related objects** box.</span></span> <span data-ttu-id="26e60-225">Por padrão, são transferidos todos os objetos de cada tipo selecionado.</span><span class="sxs-lookup"><span data-stu-id="26e60-225">By default all objects of each selected type are transferred.</span></span> <span data-ttu-id="26e60-226">Para escolher objetos individuais de qualquer tipo, clique no botão de reticências ao lado de qualquer tipo de objeto na caixa **Objetos relacionados selecionados** .</span><span class="sxs-lookup"><span data-stu-id="26e60-226">To choose individual objects of any type, click the ellipsis button next to any object type in the **Selected related objects** box.</span></span> <span data-ttu-id="26e60-227">Isso abre uma caixa de diálogo onde você pode selecionar objetos individuais.</span><span class="sxs-lookup"><span data-stu-id="26e60-227">This opens a dialog box where you can select individual objects.</span></span>  
  
     <span data-ttu-id="26e60-228">**Logons (Todos os logons em tempo de execução)**</span><span class="sxs-lookup"><span data-stu-id="26e60-228">**Logins (All logins at run time)**</span></span>  
     <span data-ttu-id="26e60-229">Inclua logons na operação de mover ou copiar.</span><span class="sxs-lookup"><span data-stu-id="26e60-229">Include logins in the move or copy operation.</span></span> <span data-ttu-id="26e60-230">Selecionadas por padrão.</span><span class="sxs-lookup"><span data-stu-id="26e60-230">Selected by default.</span></span>  
  
     <span data-ttu-id="26e60-231">**Procedimentos armazenados do banco de dados mestre**</span><span class="sxs-lookup"><span data-stu-id="26e60-231">**Stored procedures from master database**</span></span>  
     <span data-ttu-id="26e60-232">Inclua procedimentos armazenados do banco de dados **mestre** na operação de movimentação ou cópia.</span><span class="sxs-lookup"><span data-stu-id="26e60-232">Include stored procedures from the **master** database in the move or copy operation.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="26e60-233">Procedimentos armazenados estendidos e seus DLLs associados não são qualificados para cópia automatizada.</span><span class="sxs-lookup"><span data-stu-id="26e60-233">Extended stored procedures and their associated DLLs are not eligible for automated copy.</span></span>  
  
     <span data-ttu-id="26e60-234">**trabalhos do SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="26e60-234">**SQL Server Agent jobs**</span></span>  
     <span data-ttu-id="26e60-235">Inclua trabalhos do banco de dados **msdb** na operação de movimentação ou cópia.</span><span class="sxs-lookup"><span data-stu-id="26e60-235">Include jobs from the **msdb** database in the move or copy operation.</span></span>  
  
     <span data-ttu-id="26e60-236">**Mensagens de erro definidas pelo usuário**</span><span class="sxs-lookup"><span data-stu-id="26e60-236">**User-defined error messages**</span></span>  
     <span data-ttu-id="26e60-237">Inclua mensagens de erro definidas pelo usuário na operação de mover e copiar.</span><span class="sxs-lookup"><span data-stu-id="26e60-237">Include user-defined error messages in the move or copy operation.</span></span>  
  
     <span data-ttu-id="26e60-238">**Pontos de extremidade**</span><span class="sxs-lookup"><span data-stu-id="26e60-238">**Endpoints**</span></span>  
     <span data-ttu-id="26e60-239">Inclua pontos de extremidade definidos no banco de dados de origem.</span><span class="sxs-lookup"><span data-stu-id="26e60-239">Include endpoints defined in the source database.</span></span>  
  
     <span data-ttu-id="26e60-240">**Catálogo de texto completo**</span><span class="sxs-lookup"><span data-stu-id="26e60-240">**Full-text catalog**</span></span>  
     <span data-ttu-id="26e60-241">Inclua catálogos de texto completo do banco de dados de origem.</span><span class="sxs-lookup"><span data-stu-id="26e60-241">Include full-text catalogs from the source database.</span></span>  
  
     <span data-ttu-id="26e60-242">**Pacote SSIS**</span><span class="sxs-lookup"><span data-stu-id="26e60-242">**SSIS Package**</span></span>  
     <span data-ttu-id="26e60-243">Inclua pacotes [!INCLUDE[ssIS](../../includes/ssis-md.md)] definidos no banco de dados de origem.</span><span class="sxs-lookup"><span data-stu-id="26e60-243">Include [!INCLUDE[ssIS](../../includes/ssis-md.md)] packages defined in the source database.</span></span>  
  
     <span data-ttu-id="26e60-244">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="26e60-244">**Description**</span></span>  
     <span data-ttu-id="26e60-245">Uma descrição do objeto .</span><span class="sxs-lookup"><span data-stu-id="26e60-245">A description of the object.</span></span>  
  
8.  <span data-ttu-id="26e60-246">Na página **Local do Arquivos de Banco de Dados de Origem** , especifique um compartilhamento de sistema de arquivos que contém os arquivos de banco de dados no servidor de origem.</span><span class="sxs-lookup"><span data-stu-id="26e60-246">From the **Location of Source Database Files** page, specify a file system share that contains the database files on the source server.</span></span> <span data-ttu-id="26e60-247">Isso será necessário se as instâncias de servidor de origem e destino estiverem em computadores diferentes.</span><span class="sxs-lookup"><span data-stu-id="26e60-247">This is required if the source and destination server instances are on different computers.</span></span>  
  
     <span data-ttu-id="26e60-248">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="26e60-248">**Database**</span></span>  
     <span data-ttu-id="26e60-249">Exibe o nome de cada banco de dados que é movido.</span><span class="sxs-lookup"><span data-stu-id="26e60-249">Displays the name of each database being moved.</span></span>  
  
     <span data-ttu-id="26e60-250">**Local da pasta**</span><span class="sxs-lookup"><span data-stu-id="26e60-250">**Folder location**</span></span>  
     <span data-ttu-id="26e60-251">Especifique o local dos arquivos de banco de dados de origem no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="26e60-251">Specify the location of the source database files on the file system.</span></span>  
  
     <span data-ttu-id="26e60-252">Por exemplo, C:\Arquivos de Programas\Microsoft SQL Server\MSSQL110.MSSQLSERVER\MSSQL\DATA.</span><span class="sxs-lookup"><span data-stu-id="26e60-252">For example: C:\Program Files\Microsoft SQL Server\MSSQL110.MSSQLSERVER\MSSQL\DATA</span></span>  
  
     <span data-ttu-id="26e60-253">**Compartilhamento de arquivo no servidor de origem**</span><span class="sxs-lookup"><span data-stu-id="26e60-253">**File share on source server**</span></span>  
     <span data-ttu-id="26e60-254">Especifique o local dos arquivos de banco de dados de origem como um caminho de compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="26e60-254">Specify the location of the source database files as a path of a file share.</span></span>  
  
     <span data-ttu-id="26e60-255">Por exemplo: " \\ \\ *server_name*\c $ \Program Files\Microsoft SQL Server\MSSQL110. MSSQLSERVER\MSSQL\Data</span><span class="sxs-lookup"><span data-stu-id="26e60-255">For example: "\\\\*server_name*\C$\Program Files\Microsoft SQL Server\MSSQL110.MSSQLSERVER\MSSQL\Data</span></span>  
  
9. <span data-ttu-id="26e60-256">O Assistente para Copiar Banco de Dados cria um pacote [!INCLUDE[ssIS](../../includes/ssis-md.md)] para transferir o banco de dados. Na página **Configurar o Pacote** , personalize o pacote, se apropriado.</span><span class="sxs-lookup"><span data-stu-id="26e60-256">The Copy Database Wizard creates a [!INCLUDE[ssIS](../../includes/ssis-md.md)] package to transfer the database From the **Configure the Package** page, customize the package if appropriate.</span></span>  
  
     <span data-ttu-id="26e60-257">**Local do pacote**</span><span class="sxs-lookup"><span data-stu-id="26e60-257">**Package location**</span></span>  
     <span data-ttu-id="26e60-258">Exibe onde o pacote [!INCLUDE[ssIS](../../includes/ssis-md.md)] será gravado.</span><span class="sxs-lookup"><span data-stu-id="26e60-258">Displays where the [!INCLUDE[ssIS](../../includes/ssis-md.md)] package will be written.</span></span>  
  
     <span data-ttu-id="26e60-259">**Nome do pacote**</span><span class="sxs-lookup"><span data-stu-id="26e60-259">**Package name**</span></span>  
     <span data-ttu-id="26e60-260">Insira um nome para o pacote [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="26e60-260">Enter a name for the [!INCLUDE[ssIS](../../includes/ssis-md.md)] package.</span></span>  
  
     <span data-ttu-id="26e60-261">**Opções de log**</span><span class="sxs-lookup"><span data-stu-id="26e60-261">**Logging options**</span></span>  
     <span data-ttu-id="26e60-262">Selecione se as informações de log serão armazenadas no log de eventos do Windows ou em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="26e60-262">Select whether to store the logging information in the Windows event log, or in a text file.</span></span>  
  
     <span data-ttu-id="26e60-263">**Caminho do arquivo de log de erros**</span><span class="sxs-lookup"><span data-stu-id="26e60-263">**Error log file path**</span></span>  
     <span data-ttu-id="26e60-264">Forneça um caminho para o local do arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="26e60-264">Provide a path for the location of the log file.</span></span> <span data-ttu-id="26e60-265">Essa opção só estará disponível se a opção de log de arquivo de texto for selecionada.</span><span class="sxs-lookup"><span data-stu-id="26e60-265">This option is only available if the text file logging option is selected.</span></span>  
  
10. <span data-ttu-id="26e60-266">Na página **Agendar o Pacote** , especifique quando você quer que a operação de movimentação ou cópia seja iniciada.</span><span class="sxs-lookup"><span data-stu-id="26e60-266">From the **Schedule the Package** page, specify when you want the move or copy operation to start.</span></span> <span data-ttu-id="26e60-267">Se você não for um administrador do sistema, deverá especificar uma conta proxy do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent que tenha acesso ao subsistema de execução de Pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] (SSIS).</span><span class="sxs-lookup"><span data-stu-id="26e60-267">If you are not a system administrator, you must specify a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Proxy account that has access to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] (SSIS) Package execution subsystem.</span></span>  
  
     <span data-ttu-id="26e60-268">**Run immediately**</span><span class="sxs-lookup"><span data-stu-id="26e60-268">**Run immediately**</span></span>  
     <span data-ttu-id="26e60-269">Inicie a operação de movimentação ou cópia depois de clicar em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="26e60-269">Start the move or copy operation after you click **Next**.</span></span>  
  
     <span data-ttu-id="26e60-270">**Agenda**</span><span class="sxs-lookup"><span data-stu-id="26e60-270">**Schedule**</span></span>  
     <span data-ttu-id="26e60-271">Iniciar a operação de mover ou copiar mais tarde.</span><span class="sxs-lookup"><span data-stu-id="26e60-271">Start the move or copy operation later.</span></span> <span data-ttu-id="26e60-272">As configurações de agenda atuais aparecem na caixa de descrição.</span><span class="sxs-lookup"><span data-stu-id="26e60-272">The current schedule settings appear in the description box.</span></span> <span data-ttu-id="26e60-273">Para alterar a agenda, clique em **Alterar**.</span><span class="sxs-lookup"><span data-stu-id="26e60-273">To change the schedule, click **Change**.</span></span>  
  
     <span data-ttu-id="26e60-274">**Alteração**</span><span class="sxs-lookup"><span data-stu-id="26e60-274">**Change**</span></span>  
     <span data-ttu-id="26e60-275">Abra a caixa de diálogo **nova agenda de trabalho** .</span><span class="sxs-lookup"><span data-stu-id="26e60-275">Open the **New Job Schedule** dialog box.</span></span>  
  
     <span data-ttu-id="26e60-276">**conta proxy do Integration Services**</span><span class="sxs-lookup"><span data-stu-id="26e60-276">**Integration Services proxy account**</span></span>  
     <span data-ttu-id="26e60-277">Selecione uma conta proxy disponível.</span><span class="sxs-lookup"><span data-stu-id="26e60-277">Select an available proxy account.</span></span> <span data-ttu-id="26e60-278">Para agendar a transferência, deve haver pelo menos uma conta proxy disponível para o usuário, configurada com permissão para o subsistema de **execução do pacote SQL Server Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="26e60-278">To schedule the transfer, there must be at least one proxy account available to the user, configured with permission to the **SQL Server Integration Services package execution** subsystem.</span></span>  
  
     <span data-ttu-id="26e60-279">Para criar uma conta proxy para a [!INCLUDE[ssIS](../../includes/ssis-md.md)] execução do pacote, no Pesquisador de objetos, expanda **SQL Server Agent**, expanda **proxies**, clique com o botão direito do mouse em **execução do pacote SSIS**e clique em **novo proxy**.</span><span class="sxs-lookup"><span data-stu-id="26e60-279">To create a proxy account for [!INCLUDE[ssIS](../../includes/ssis-md.md)] package execution, in Object Explorer, expand **SQL Server Agent**, expand **Proxies**, right-click **SSIS Package Execution**, and then click **New Proxy**.</span></span>  
  
     <span data-ttu-id="26e60-280">Os membros da função de servidor fixa **sysadmin** podem selecionar a **Conta de Serviço do SQL Server Agent**que tenha as permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="26e60-280">Members of the **sysadmin** fixed server role can select the **SQL Server Agent Service Account**, which has the necessary permissions.</span></span>  
  
11. <span data-ttu-id="26e60-281">Na página **Concluir o Assistente** , confira o resumo das opções selecionadas.</span><span class="sxs-lookup"><span data-stu-id="26e60-281">From the **Complete the Wizard** page, review the summary of the selected options.</span></span> <span data-ttu-id="26e60-282">Clique em **Voltar** para alterar uma opção.</span><span class="sxs-lookup"><span data-stu-id="26e60-282">Click **Back** to change an option.</span></span> <span data-ttu-id="26e60-283">Clique em **Concluir** para criar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="26e60-283">Click **Finish** to create the database.</span></span> <span data-ttu-id="26e60-284">Durante a transferência, a página **Executando operação** monitora informações de status sobre a execução do **Assistente para Copiar Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="26e60-284">During the transfer, the **Performing operation** page monitors status information about the execution of the **Copy Database Wizard**.</span></span>  
  
     <span data-ttu-id="26e60-285">**Ação**</span><span class="sxs-lookup"><span data-stu-id="26e60-285">**Action**</span></span>  
     <span data-ttu-id="26e60-286">Lista cada ação que está sendo executada.</span><span class="sxs-lookup"><span data-stu-id="26e60-286">Lists each action being performed.</span></span>  
  
     <span data-ttu-id="26e60-287">**Status**</span><span class="sxs-lookup"><span data-stu-id="26e60-287">**Status**</span></span>  
     <span data-ttu-id="26e60-288">Indica se a ação como um todo obteve êxito ou falhou.</span><span class="sxs-lookup"><span data-stu-id="26e60-288">Indicates whether the action as a whole succeeded or failed.</span></span>  
  
     <span data-ttu-id="26e60-289">**Message**</span><span class="sxs-lookup"><span data-stu-id="26e60-289">**Message**</span></span>  
     <span data-ttu-id="26e60-290">Fornece qualquer mensagem que retornou de cada etapa.</span><span class="sxs-lookup"><span data-stu-id="26e60-290">Provides any messages returned from each step.</span></span>  
  
##  <a name="follow-up-after-upgrading-a-sql-server-database"></a><a name="FollowUp"></a> <span data-ttu-id="26e60-291">Acompanhamento: Depois de atualizar um banco de dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="26e60-291">Follow Up: After Upgrading a SQL Server Database</span></span>  
 <span data-ttu-id="26e60-292">Após o uso do Assistente para Copiar Banco de Dados para atualizar um banco de dados de uma versão anterior do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], o banco de dados é disponibilizado imediatamente e é atualizado de forma automática.</span><span class="sxs-lookup"><span data-stu-id="26e60-292">After you use the Copy Database Wizard to upgrade a database from an earlier version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], the database becomes available immediately and is automatically upgraded.</span></span> <span data-ttu-id="26e60-293">Se o banco de dados tiver índices de texto completo, o processo de atualização importará, redefinirá ou recriará esses índices dependendo da configuração da propriedade de servidor **Opção de Atualização de Texto Completo** .</span><span class="sxs-lookup"><span data-stu-id="26e60-293">If the database has full-text indexes, the upgrade process either imports, resets, or rebuilds them, depending on the setting of the **Full-Text Upgrade Option** server property.</span></span> <span data-ttu-id="26e60-294">Se a opção de atualização for definida como **Importar** ou **Recriar**, os índices de texto completo permanecerão indisponíveis durante a atualização.</span><span class="sxs-lookup"><span data-stu-id="26e60-294">If the upgrade option is set to **Import** or **Rebuild**, the full-text indexes will be unavailable during the upgrade.</span></span> <span data-ttu-id="26e60-295">Dependendo da quantidade de dados a serem indexados, a importação pode levar várias horas, e a recriação pode ser até dez vezes mais demorada.</span><span class="sxs-lookup"><span data-stu-id="26e60-295">Depending the amount of data being indexed, importing can take several hours, and rebuilding can take up to ten times longer.</span></span> <span data-ttu-id="26e60-296">Lembre-se também de que, quando a opção de atualização estiver definida como **Importar**, se não houver um catálogo de texto completo disponível, os índices de texto completo associados serão recompilados.</span><span class="sxs-lookup"><span data-stu-id="26e60-296">Note also that when the upgrade option is set to **Import**, if a full-text catalog is not available, the associated full-text indexes are rebuilt.</span></span> <span data-ttu-id="26e60-297">Para obter informações sobre como exibir ou alterar a configuração da propriedade **Full-Text Upgrade Option** , veja [Gerenciar e monitorar a pesquisa de texto completo para uma instância de servidor](../search/manage-and-monitor-full-text-search-for-a-server-instance.md).</span><span class="sxs-lookup"><span data-stu-id="26e60-297">For information about viewing or changing the setting of the **Full-Text Upgrade Option** property, see [Manage and Monitor Full-Text Search for a Server Instance](../search/manage-and-monitor-full-text-search-for-a-server-instance.md).</span></span>  
  
 <span data-ttu-id="26e60-298">Se o nível de compatibilidade de um banco de dados de usuário era 100 ou mais alto antes da atualização, ele permanecerá o mesmo depois da atualização.</span><span class="sxs-lookup"><span data-stu-id="26e60-298">If the compatibility level of a user database was 100 or higher before upgrade, it remains the same after upgrade.</span></span> <span data-ttu-id="26e60-299">Se o nível de compatibilidade era 90, no banco de dados atualizado, o nível de compatibilidade será definido como 100, que é o nível de compatibilidade mais baixo com suporte no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26e60-299">If the compatibility level was 90 in the upgraded database, the compatibility level is set to 100, which is the lowest supported compatibility level in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="26e60-300">Para obter mais informações, veja [Nível de compatibilidade de ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span><span class="sxs-lookup"><span data-stu-id="26e60-300">For more information, see [ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26e60-301">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="26e60-301">See Also</span></span>  
 <span data-ttu-id="26e60-302">[Atualizar um banco de dados usando desanexar e anexar &#40;&#41;Transact-SQL](upgrade-a-database-using-detach-and-attach-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="26e60-302">[Upgrade a Database Using Detach and Attach &#40;Transact-SQL&#41;](upgrade-a-database-using-detach-and-attach-transact-sql.md) </span></span>  
 [<span data-ttu-id="26e60-303">Criar um proxy do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="26e60-303">Create a SQL Server Agent Proxy</span></span>](../../ssms/agent/create-a-sql-server-agent-proxy.md)  
  
  
