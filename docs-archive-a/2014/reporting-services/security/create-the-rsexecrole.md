---
title: Criar a RSExecRole | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- RSExecRole
ms.assetid: 7ac17341-df7e-4401-870e-652caa2859c0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0037ef0c4d7a949b5a30bb45356613f6114db130
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680316"
---
# <a name="create-the-rsexecrole"></a><span data-ttu-id="0a772-102">Criar o RSExecRole</span><span class="sxs-lookup"><span data-stu-id="0a772-102">Create the RSExecRole</span></span>
  <span data-ttu-id="0a772-103">O [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] usa uma função de banco de dados predefinida chamada `RSExecRole` para conceder permissões de servidor de relatório ao banco de dados de servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="0a772-103">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] uses a predefined database role called `RSExecRole` to grant report server permissions to the report server database.</span></span> <span data-ttu-id="0a772-104">A `RSExecRole` função é criada automaticamente com o banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="0a772-104">The `RSExecRole` role is created automatically with the report server database.</span></span> <span data-ttu-id="0a772-105">Como regra geral, você nunca deve modificá-la ou atribuir outros usuários à função.</span><span class="sxs-lookup"><span data-stu-id="0a772-105">As a rule, you should never modify it or assign other users to the role.</span></span> <span data-ttu-id="0a772-106">No entanto, quando você move um banco de dados do servidor de relatório para um novo ou diferente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../../includes/ssde-md.md)] , o deve recriar a função nos bancos de dados do sistema mestre e msdb.</span><span class="sxs-lookup"><span data-stu-id="0a772-106">However, when you move a report server database to a new or different [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../../includes/ssde-md.md)], must re-create the role in the Master and MSDB system databases.</span></span>

 <span data-ttu-id="0a772-107">Usando as instruções a seguir, você executará estas etapas:</span><span class="sxs-lookup"><span data-stu-id="0a772-107">Using the following instructions, you will perform the following steps:</span></span>

-   <span data-ttu-id="0a772-108">Crie e provisione o `RSExecRole` no banco de dados Mestre do sistema.</span><span class="sxs-lookup"><span data-stu-id="0a772-108">Create and provision the `RSExecRole` in the Master system database.</span></span>

-   <span data-ttu-id="0a772-109">Crie e provisione o `RSExecRole` no banco de dados MSDB do sistema.</span><span class="sxs-lookup"><span data-stu-id="0a772-109">Create and provision the `RSExecRole` in the MSDB system database.</span></span>

> [!NOTE]
>  <span data-ttu-id="0a772-110">As instruções deste tópico são voltadas para os usuários que não desejam executar um script ou gravar um código WMI para provisionar o banco de dados de servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="0a772-110">The instructions in this topic are intended for users who do not want to run a script or write WMI code to provision the report server database.</span></span> <span data-ttu-id="0a772-111">Se você gerenciar uma grande implantação e mover bancos de dados periodicamente, grave um script para automatizar estas etapas.</span><span class="sxs-lookup"><span data-stu-id="0a772-111">If you manage a large deployment and will be moving databases routinely, you should write a script to automate these steps.</span></span> <span data-ttu-id="0a772-112">Para obter mais informações, consulte [Acessar o provedor WMI do Reporting Services](../tools/access-the-reporting-services-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="0a772-112">For more information, see [Access the Reporting Services WMI Provider](../tools/access-the-reporting-services-wmi-provider.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="0a772-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="0a772-113">Before you start</span></span>

-   <span data-ttu-id="0a772-114">Faça backup das chaves de criptografia de forma que você possa restaurá-las depois que o banco de dados for movido.</span><span class="sxs-lookup"><span data-stu-id="0a772-114">Back up the encryption keys so that you can restore them after the database is moved.</span></span> <span data-ttu-id="0a772-115">Essa etapa não afeta diretamente a possibilidade de criar e provisionar o `RSExecRole`, mas é necessário ter um backup das chaves para verificar seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="0a772-115">This is step does not directly affect your ability to create and provision the `RSExecRole`, but you must have a backup of the keys in order to verify your work.</span></span> <span data-ttu-id="0a772-116">Para saber mais, confira [Back Up and Restore Reporting Services Encryption Keys](../install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys.md).</span><span class="sxs-lookup"><span data-stu-id="0a772-116">For more information, see [Back Up and Restore Reporting Services Encryption Keys](../install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys.md).</span></span>

-   <span data-ttu-id="0a772-117">Verifique se você está conectado com uma conta de usuário que tem permissões `sysadmin` na instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0a772-117">Verify you are logged on as a user account that has `sysadmin` permissions on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span>

-   <span data-ttu-id="0a772-118">Verifique se o serviço do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent está instalado e em execução na instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)] que pretende usar.</span><span class="sxs-lookup"><span data-stu-id="0a772-118">Verify [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent service is installed and running on the instance of the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] instance that you plan to use.</span></span>

-   <span data-ttu-id="0a772-119">Conecte os bancos de dados reportserver e reportservertempdb.</span><span class="sxs-lookup"><span data-stu-id="0a772-119">Attach the reportservertempdb and reportserver databases.</span></span> <span data-ttu-id="0a772-120">Não é necessário conectar os bancos de dados para criar a função real, mas eles devem ser conectados antes de você testar seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="0a772-120">You are not required to attach the databases to create the actual role, but they must be attached before you can test your work.</span></span>

 <span data-ttu-id="0a772-121">As instruções para a criação manual do `RSExecRole` devem ser usadas no contexto de migração da instalação de um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="0a772-121">The instructions for manually creating the `RSExecRole` are intended to be used within the context of migrating a report server installation.</span></span> <span data-ttu-id="0a772-122">Tarefas importantes como o backup e a movimentação do banco de dados de servidor de relatórios não são descritas neste tópico, mas estão disponíveis na documentação do Mecanismo do Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="0a772-122">Important tasks such as backing up and moving the report server database are not addressed in this topic, but are documented in the Database Engine documentation.</span></span>

## <a name="create-rsexecrole-in-master"></a><span data-ttu-id="0a772-123">Criar o RSExecRole no Mestre</span><span class="sxs-lookup"><span data-stu-id="0a772-123">Create RSExecRole in Master</span></span>
 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="0a772-124">usa procedimentos armazenados estendidos para que o serviço do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent dê suporte a operações agendadas.</span><span class="sxs-lookup"><span data-stu-id="0a772-124">uses extended stored procedures for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent service to support scheduled operations.</span></span> <span data-ttu-id="0a772-125">As etapas a seguir explicam como conceder permissões Executar para os procedimentos da função `RSExecRole`.</span><span class="sxs-lookup"><span data-stu-id="0a772-125">The following steps explain how to grant Execute permissions for the procedures to the `RSExecRole` role.</span></span>

#### <a name="to-create-rsexecrole-in-the-master-system-database-using-management-studio"></a><span data-ttu-id="0a772-126">Para criar o RSExecRole no banco de dados Mestre do sistema usando o Management Studio</span><span class="sxs-lookup"><span data-stu-id="0a772-126">To create RSExecRole in the Master system database using Management Studio</span></span>

1.  <span data-ttu-id="0a772-127">Inicie o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] e estabeleça uma conexão com a instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)] que hospeda o banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="0a772-127">Start [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] instance that hosts the report server database.</span></span>

2.  <span data-ttu-id="0a772-128">Abra **Bancos de Dados**.</span><span class="sxs-lookup"><span data-stu-id="0a772-128">Open **Databases**.</span></span>

3.  <span data-ttu-id="0a772-129">Abra **Bancos de Dados do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="0a772-129">Open **System Databases**.</span></span>

4.  <span data-ttu-id="0a772-130">Abra o `Master`.</span><span class="sxs-lookup"><span data-stu-id="0a772-130">Open `Master`.</span></span>

5.  <span data-ttu-id="0a772-131">Abra **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="0a772-131">Open **Security**.</span></span>

6.  <span data-ttu-id="0a772-132">Abra **Funções**.</span><span class="sxs-lookup"><span data-stu-id="0a772-132">Open **Roles**.</span></span>

7.  <span data-ttu-id="0a772-133">Clique com o botão direito do mouse em **Funções de Banco de Dados**e selecione **Nova Função de Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="0a772-133">Right-click **Database Roles**, and select **New Database Role**.</span></span> <span data-ttu-id="0a772-134">A página Geral é exibida.</span><span class="sxs-lookup"><span data-stu-id="0a772-134">The General page appears.</span></span>

8.  <span data-ttu-id="0a772-135">Em **nome da função**, digite `RSExecRole` .</span><span class="sxs-lookup"><span data-stu-id="0a772-135">In **Role name**, type `RSExecRole`.</span></span>

9. <span data-ttu-id="0a772-136">Em **Proprietário**, digite **DBO**.</span><span class="sxs-lookup"><span data-stu-id="0a772-136">In **Owner**, type **DBO**.</span></span>

10. <span data-ttu-id="0a772-137">Clique em **Protegíveis**.</span><span class="sxs-lookup"><span data-stu-id="0a772-137">Click **Securables**.</span></span>

11. <span data-ttu-id="0a772-138">Clique em **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="0a772-138">Click **Search**.</span></span> <span data-ttu-id="0a772-139">A caixa de diálogo **Adicionar Objetos** é exibida.</span><span class="sxs-lookup"><span data-stu-id="0a772-139">The **Add Objects** dialog box appears.</span></span> <span data-ttu-id="0a772-140">A opção **Objetos Específicos** é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="0a772-140">The **Specific Objects** option is selected by default.</span></span>

12. <span data-ttu-id="0a772-141">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a772-141">Click **OK**.</span></span> <span data-ttu-id="0a772-142">A caixa de diálogo **Selecionar Objetos** é exibida.</span><span class="sxs-lookup"><span data-stu-id="0a772-142">The **Select Objects** dialog box appears.</span></span>

13. <span data-ttu-id="0a772-143">Clique em **Tipos de Objetos**.</span><span class="sxs-lookup"><span data-stu-id="0a772-143">Click **Object Types**.</span></span>

14. <span data-ttu-id="0a772-144">Clique em **Procedimentos Armazenados Estendidos**.</span><span class="sxs-lookup"><span data-stu-id="0a772-144">Click **Extended Stored Procedures**.</span></span>

15. <span data-ttu-id="0a772-145">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a772-145">Click **OK**.</span></span>

16. <span data-ttu-id="0a772-146">Clique em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="0a772-146">Click **Browse**.</span></span>

17. <span data-ttu-id="0a772-147">Percorra a lista de procedimentos armazenados estendidos e selecione o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0a772-147">Scroll down the list of extended stored procedures and select the following:</span></span>

    1.  <span data-ttu-id="0a772-148">xp_sqlagent_enum_jobs</span><span class="sxs-lookup"><span data-stu-id="0a772-148">xp_sqlagent_enum_jobs</span></span>

    2.  <span data-ttu-id="0a772-149">xp_sqlagent_is_starting</span><span class="sxs-lookup"><span data-stu-id="0a772-149">xp_sqlagent_is_starting</span></span>

    3.  <span data-ttu-id="0a772-150">xp_sqlagent_notify</span><span class="sxs-lookup"><span data-stu-id="0a772-150">xp_sqlagent_notify</span></span>

18. <span data-ttu-id="0a772-151">Clique em **OK**e em **OK** novamente.</span><span class="sxs-lookup"><span data-stu-id="0a772-151">Click **OK**, and the click **OK** again.</span></span>

19. <span data-ttu-id="0a772-152">Na linha **Executar** , na coluna **Conceder** , marque a caixa de seleção e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a772-152">In the **Execute** row, in the **Grant** column, click the check box, and then click **OK**.</span></span>

20. <span data-ttu-id="0a772-153">Repita essas etapas para cada um dos procedimentos armazenados restantes.</span><span class="sxs-lookup"><span data-stu-id="0a772-153">Repeat for each of the remaining stored procedures.</span></span> <span data-ttu-id="0a772-154">O `RSExecRole` deve receber permissões Executar para todos os três procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="0a772-154">`RSExecRole` must be granted Execute permissions for all three stored procedures.</span></span>

 <span data-ttu-id="0a772-155">![Página Propriedades da Função de Banco de Dados](../media/rsexecroledbproperties.gif "Página Propriedades da Função de Banco de Dados")</span><span class="sxs-lookup"><span data-stu-id="0a772-155">![Database Role Properties page](../media/rsexecroledbproperties.gif "Database Role Properties page")</span></span>

## <a name="create-rsexecrole-in-msdb"></a><span data-ttu-id="0a772-156">Criar o RSExecRole no MSDB</span><span class="sxs-lookup"><span data-stu-id="0a772-156">Create RSExecRole in MSDB</span></span>
 <span data-ttu-id="0a772-157">O Reporting Services usa procedimentos armazenados para o serviço do SQL Server Agent e recupera informações de trabalho das tabelas do sistema para suportar as operações agendadas.</span><span class="sxs-lookup"><span data-stu-id="0a772-157">Reporting Services uses stored procedures for SQL Server Agent service and retrieves job information from system tables to support scheduled operations.</span></span> <span data-ttu-id="0a772-158">As etapas a seguir explicam como conceder permissões Executar para os procedimentos e as permissões Selecionar nas tabelas para o RSExecRole.</span><span class="sxs-lookup"><span data-stu-id="0a772-158">The following steps explain how to grant Execute permissions for the procedures and Select permissions on the tables to the RSExecRole.</span></span>

#### <a name="to-create-rsexecrole-in-the-msdb-system-database"></a><span data-ttu-id="0a772-159">Para criar o RSExecRole no banco de dados MSDB do sistema</span><span class="sxs-lookup"><span data-stu-id="0a772-159">To create RSExecRole in the MSDB system database</span></span>

1.  <span data-ttu-id="0a772-160">Repita etapas semelhantes para conceder permissões a procedimentos armazenados e tabelas no MSDB.</span><span class="sxs-lookup"><span data-stu-id="0a772-160">Repeat similar steps for granting permissions to stored procedures and tables in MSDB.</span></span> <span data-ttu-id="0a772-161">Para simplificar as etapas, você provisionará os procedimentos armazenados e as tabelas separadamente.</span><span class="sxs-lookup"><span data-stu-id="0a772-161">To simplify the steps, you will provision the stored procedures and tables separately.</span></span>

2.  <span data-ttu-id="0a772-162">Abra o `MSDB`.</span><span class="sxs-lookup"><span data-stu-id="0a772-162">Open `MSDB`.</span></span>

3.  <span data-ttu-id="0a772-163">Abra **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="0a772-163">Open **Security**.</span></span>

4.  <span data-ttu-id="0a772-164">Abra **Funções**.</span><span class="sxs-lookup"><span data-stu-id="0a772-164">Open **Roles**.</span></span>

5.  <span data-ttu-id="0a772-165">Clique com o botão direito do mouse em **Funções de Banco de Dados**e selecione **Nova Função de Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="0a772-165">Right-click **Database Roles**, and select **New Database Role**.</span></span> <span data-ttu-id="0a772-166">A página Geral é exibida.</span><span class="sxs-lookup"><span data-stu-id="0a772-166">The General page appears.</span></span>

6.  <span data-ttu-id="0a772-167">Em nome da função, digite `RSExecRole` .</span><span class="sxs-lookup"><span data-stu-id="0a772-167">In Role name, type `RSExecRole`.</span></span>

7.  <span data-ttu-id="0a772-168">Em proprietário, digite **dbo**.</span><span class="sxs-lookup"><span data-stu-id="0a772-168">In Owner, type **DBO**.</span></span>

8.  <span data-ttu-id="0a772-169">Clique em **Protegíveis**.</span><span class="sxs-lookup"><span data-stu-id="0a772-169">Click **Securables**.</span></span>

9. <span data-ttu-id="0a772-170">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="0a772-170">Click **Add**.</span></span> <span data-ttu-id="0a772-171">A caixa de diálogo **Adicionar Objetos** é exibida.</span><span class="sxs-lookup"><span data-stu-id="0a772-171">The **Add Objects** dialog box appears.</span></span> <span data-ttu-id="0a772-172">A opção **Especificar Objetos** é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="0a772-172">The **Specify Objects** option is selected by default.</span></span>

10. <span data-ttu-id="0a772-173">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a772-173">Click **OK**.</span></span>

11. <span data-ttu-id="0a772-174">Clique em **Tipos de Objeto**.</span><span class="sxs-lookup"><span data-stu-id="0a772-174">Click **Object Types**.</span></span>

12. <span data-ttu-id="0a772-175">Clique em **Procedimentos Armazenados**.</span><span class="sxs-lookup"><span data-stu-id="0a772-175">Click **Stored Procedures.**</span></span>

13. <span data-ttu-id="0a772-176">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a772-176">Click **OK**.</span></span>

14. <span data-ttu-id="0a772-177">Clique em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="0a772-177">Click **Browse**.</span></span>

15. <span data-ttu-id="0a772-178">Percorra a lista de itens e selecione o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0a772-178">Scroll down the list of items and select the following:</span></span>

    1.  <span data-ttu-id="0a772-179">sp_add_category</span><span class="sxs-lookup"><span data-stu-id="0a772-179">sp_add_category</span></span>

    2.  <span data-ttu-id="0a772-180">sp_add_job</span><span class="sxs-lookup"><span data-stu-id="0a772-180">sp_add_job</span></span>

    3.  <span data-ttu-id="0a772-181">sp_add_jobschedule</span><span class="sxs-lookup"><span data-stu-id="0a772-181">sp_add_jobschedule</span></span>

    4.  <span data-ttu-id="0a772-182">sp_add_jobserver</span><span class="sxs-lookup"><span data-stu-id="0a772-182">sp_add_jobserver</span></span>

    5.  <span data-ttu-id="0a772-183">sp_add_jobstep</span><span class="sxs-lookup"><span data-stu-id="0a772-183">sp_add_jobstep</span></span>

    6.  <span data-ttu-id="0a772-184">sp_delete_job</span><span class="sxs-lookup"><span data-stu-id="0a772-184">sp_delete_job</span></span>

    7.  <span data-ttu-id="0a772-185">sp_help_category</span><span class="sxs-lookup"><span data-stu-id="0a772-185">sp_help_category</span></span>

    8.  <span data-ttu-id="0a772-186">sp_help_job</span><span class="sxs-lookup"><span data-stu-id="0a772-186">sp_help_job</span></span>

    9. <span data-ttu-id="0a772-187">sp_help_jobschedule</span><span class="sxs-lookup"><span data-stu-id="0a772-187">sp_help_jobschedule</span></span>

    10. <span data-ttu-id="0a772-188">sp_verify_job_identifiers</span><span class="sxs-lookup"><span data-stu-id="0a772-188">sp_verify_job_identifiers</span></span>

16. <span data-ttu-id="0a772-189">Clique em **OK**e em **OK** novamente.</span><span class="sxs-lookup"><span data-stu-id="0a772-189">Click **OK**, and the click **OK** again.</span></span>

17. <span data-ttu-id="0a772-190">Selecione o primeiro procedimento armazenado: sp_add_category.</span><span class="sxs-lookup"><span data-stu-id="0a772-190">Select the first stored procedure: sp_add_category.</span></span>

18. <span data-ttu-id="0a772-191">Na linha **Executar** , na coluna **Conceder** , marque a caixa de seleção e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a772-191">In the **Execute** row, in the **Grant** column, click the checkbox, and then click **OK**.</span></span>

19. <span data-ttu-id="0a772-192">Repita essas etapas para cada um dos procedimentos armazenados restantes.</span><span class="sxs-lookup"><span data-stu-id="0a772-192">Repeat for each of the remaining stored procedures.</span></span> <span data-ttu-id="0a772-193">O RSExecRole deve obter permissões Executar para os dez procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="0a772-193">RSExecRole must be granted Execute permissions for all ten stored procedures.</span></span>

20. <span data-ttu-id="0a772-194">Na guia Protegíveis, clique em **Adicionar** novamente.</span><span class="sxs-lookup"><span data-stu-id="0a772-194">On the Securables tab, and click **Add** again.</span></span> <span data-ttu-id="0a772-195">A caixa de diálogo **Adicionar Objetos** é exibida.</span><span class="sxs-lookup"><span data-stu-id="0a772-195">The **Add Objects** dialog box appears.</span></span> <span data-ttu-id="0a772-196">A opção **Especificar Objetos** é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="0a772-196">The **Specify Objects** option is selected by default.</span></span>

21. <span data-ttu-id="0a772-197">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a772-197">Click **OK**.</span></span>

22. <span data-ttu-id="0a772-198">Clique em **Tipos de Objeto**.</span><span class="sxs-lookup"><span data-stu-id="0a772-198">Click **Object Types**.</span></span>

23. <span data-ttu-id="0a772-199">Clique em **Tabelas**.</span><span class="sxs-lookup"><span data-stu-id="0a772-199">Click **Tables.**</span></span>

24. <span data-ttu-id="0a772-200">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a772-200">Click **OK**.</span></span>

25. <span data-ttu-id="0a772-201">Clique em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="0a772-201">Click **Browse**.</span></span>

26. <span data-ttu-id="0a772-202">Percorra a lista de itens e selecione o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0a772-202">Scroll down the list of items and select the following:</span></span>

    1.  <span data-ttu-id="0a772-203">syscategories</span><span class="sxs-lookup"><span data-stu-id="0a772-203">syscategories</span></span>

    2.  <span data-ttu-id="0a772-204">sysjobs</span><span class="sxs-lookup"><span data-stu-id="0a772-204">sysjobs</span></span>

27. <span data-ttu-id="0a772-205">Clique em **OK**e em **OK** novamente.</span><span class="sxs-lookup"><span data-stu-id="0a772-205">Click **OK**, and the click **OK** again.</span></span>

28. <span data-ttu-id="0a772-206">Selecione a primeira tabela: syscategories.</span><span class="sxs-lookup"><span data-stu-id="0a772-206">Select the first table: syscategories.</span></span>

29. <span data-ttu-id="0a772-207">Na linha **Selecionar** , na coluna **Conceder** , marque a caixa de seleção e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a772-207">In the **Select** row, in the **Grant** column, click the checkbox, and then click **OK**.</span></span>

30. <span data-ttu-id="0a772-208">Repita para a tabela sysjobs.</span><span class="sxs-lookup"><span data-stu-id="0a772-208">Repeat for the sysjobs table.</span></span> <span data-ttu-id="0a772-209">O RSExecRole deve obter permissões Selecionar para as duas tabelas.</span><span class="sxs-lookup"><span data-stu-id="0a772-209">RSExecRole must be granted Select permissions for both tables.</span></span>

## <a name="move-the-report-server-database"></a><span data-ttu-id="0a772-210">Mover o banco de dados do servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="0a772-210">Move the Report Server Database</span></span>
 <span data-ttu-id="0a772-211">Depois de criar as funções, você pode mover o banco de dados de servidor de relatório para a nova instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0a772-211">After you create the roles, you can move the report server database to new SQL Server instance.</span></span> <span data-ttu-id="0a772-212">Para obter mais informações, consulte [Movendo os bancos de dados do servidor de relatório para outro computador &#40;modo nativo do SSRS&#41;](../report-server/moving-the-report-server-databases-to-another-computer-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="0a772-212">For more information, see [Moving the Report Server Databases to Another Computer &#40;SSRS Native Mode&#41;](../report-server/moving-the-report-server-databases-to-another-computer-ssrs-native-mode.md).</span></span>

 <span data-ttu-id="0a772-213">Se você estiver atualizando o [!INCLUDE[ssDE](../../../includes/ssde-md.md)] para [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], poderá atualizá-lo antes de ou depois de mover o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="0a772-213">If you are upgrading the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] to [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], you can upgrade it before or after moving the database.</span></span>

 <span data-ttu-id="0a772-214">O banco de dados do servidor de relatório será atualizado automaticamente para o [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] quando o servidor de relatório se conectar a ele.</span><span class="sxs-lookup"><span data-stu-id="0a772-214">The report server database will be upgraded to the [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] automatically when the report server connects to it.</span></span> <span data-ttu-id="0a772-215">Não há nenhuma etapa específica necessária para atualizar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="0a772-215">There are no specific steps required for upgrading the database.</span></span>

## <a name="restore-encryption-keys-and-verify-your-work"></a><span data-ttu-id="0a772-216">Restaurar as chaves de criptografia e verificar seu trabalho</span><span class="sxs-lookup"><span data-stu-id="0a772-216">Restore Encryption Keys and Verify Your Work</span></span>
 <span data-ttu-id="0a772-217">Se você tiver anexado os bancos de dados de servidor de relatório, execute estas etapas para verificar seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="0a772-217">If you have attached the report server databases, you should now be able to complete the following steps to verify your work.</span></span>

#### <a name="to-verify-report-server-operability-after-a-database-move"></a><span data-ttu-id="0a772-218">Para verificar a operabilidade do servidor de relatório depois de um movimento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="0a772-218">To verify report server operability after a database move</span></span>

1.  <span data-ttu-id="0a772-219">Inicie a ferramenta Configuração do Reporting Services e conecte-se ao servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="0a772-219">Start the Reporting Services Configuration tool and connect to the report server.</span></span>

2.  <span data-ttu-id="0a772-220">Clique em **Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="0a772-220">Click **Database**.</span></span>

3.  <span data-ttu-id="0a772-221">Clique em **Alterar Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="0a772-221">Click **Change Database**.</span></span>

4.  <span data-ttu-id="0a772-222">Clique em **Escolher um banco de dados existente do servidor de relatório**.</span><span class="sxs-lookup"><span data-stu-id="0a772-222">Click **Choose an existing report server database**.</span></span>

5.  <span data-ttu-id="0a772-223">Insira o nome do servidor do Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="0a772-223">Enter the server name of the Database Engine.</span></span> <span data-ttu-id="0a772-224">Se você anexou os bancos de dados do servidor de relatório a uma instância nomeada, deverá digitar o nome da instância neste formato: \<servername> \\<InstanceName \> .</span><span class="sxs-lookup"><span data-stu-id="0a772-224">If you attached the report server databases to a named instance, you must type the instance name in this format: \<servername>\\<instancename\>.</span></span>

6.  <span data-ttu-id="0a772-225">Clique em **Testar Conexão**.</span><span class="sxs-lookup"><span data-stu-id="0a772-225">Click **Test Connection**.</span></span>

7.  <span data-ttu-id="0a772-226">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0a772-226">Click **Next**.</span></span>

8.  <span data-ttu-id="0a772-227">Em Banco de Dados, selecione o banco de dados de servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="0a772-227">On the Database, select the report server database.</span></span>

9. <span data-ttu-id="0a772-228">Clique em **Próximo** e conclua o assistente.</span><span class="sxs-lookup"><span data-stu-id="0a772-228">Click **Next** and complete the wizard.</span></span>

10. <span data-ttu-id="0a772-229">Clique em **Chaves de Criptografia**.</span><span class="sxs-lookup"><span data-stu-id="0a772-229">Click **Encryption Keys**.</span></span>

11. <span data-ttu-id="0a772-230">Clique em **restaurar**.</span><span class="sxs-lookup"><span data-stu-id="0a772-230">Click **Restore**.</span></span>

12. <span data-ttu-id="0a772-231">Selecione o arquivo forte (.snk) que tem a cópia de backup da chave simétrica usada para descriptografar as credenciais armazenadas e as informações de conexão no banco de dados de servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="0a772-231">Select the strong file (.snk) that has the backup copy of the symmetric key used to decrypt stored credentials and connection information in the report server database.</span></span>

13. <span data-ttu-id="0a772-232">Insira a senha e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a772-232">Enter the password and click **OK**.</span></span>

14. <span data-ttu-id="0a772-233">Clique em **URL do Gerenciador de Relatórios**.</span><span class="sxs-lookup"><span data-stu-id="0a772-233">Click **Report Manager URL**.</span></span>

15. <span data-ttu-id="0a772-234">Clique no link para abrir o Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="0a772-234">Click the link to open Report Manager.</span></span> <span data-ttu-id="0a772-235">Você deve ver os itens de servidor de relatório do banco de dados de servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="0a772-235">You should see the report server items from the report server database.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a772-236">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0a772-236">See Also</span></span>
 <span data-ttu-id="0a772-237">[Mover os bancos de dados do servidor de relatório para outro computador &#40;modo nativo do SSRS&#41;](../report-server/moving-the-report-server-databases-to-another-computer-ssrs-native-mode.md) [Gerenciador de configurações do Reporting Services &#40;modo nativo&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) [criar um banco de dados do servidor de relatório no modo nativo &#40;SSRS Configuration Manager&#41;](../install-windows/ssrs-report-server-create-a-native-mode-report-server-database.md) [fazer backup e restaurar Reporting Services chaves de criptografia](../install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys.md)</span><span class="sxs-lookup"><span data-stu-id="0a772-237">[Moving the Report Server Databases to Another Computer &#40;SSRS Native Mode&#41;](../report-server/moving-the-report-server-databases-to-another-computer-ssrs-native-mode.md) [Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) [Create a Native Mode Report Server Database  &#40;SSRS Configuration Manager&#41;](../install-windows/ssrs-report-server-create-a-native-mode-report-server-database.md) [Back Up and Restore Reporting Services Encryption Keys](../install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys.md)</span></span>


