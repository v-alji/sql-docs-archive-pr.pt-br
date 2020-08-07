---
title: Configurar o Data Warehouse de Gerenciamento (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dc.datacollection.wizard_finish.f1
- sql12.swb.dc.datacollection.wizard_maploginuser.f1
- sql12.swb.dc.datacollection.wizard_welcome.f1
- sql12.swb.dc.datacollection.wizard_choosemdw.f1
- sql12.swb.dc.datacollection.wizard_completecfg.f1
- sql12.swb.dc.datacollection.wizard_config.f1
- sql12.swb.dc.datacollection.wizard_createmdw.f1
helpviewer_keywords:
- data warehouse [SQL Server], multiple instances
- data warehouse [SQL Server], configuring
- Configure Management Data Warehouse Wizard
- management data warehouse, configuring
ms.assetid: 23a584f3-c5e1-414c-9afe-73cd7efbda4b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1ef4ddd518343a3076c72ecc41f9b15ddf092dc0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584157"
---
# <a name="configure-the-management-data-warehouse-sql-server-management-studio"></a><span data-ttu-id="70f6e-102">Configurar o Data Warehouse de Gerenciamento (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="70f6e-102">Configure the Management Data Warehouse (SQL Server Management Studio)</span></span>
  <span data-ttu-id="70f6e-103">Este tópico descreve como configurar o data warehouse de gerenciamento para oferecer suporte de armazenamento de dados em uma ou várias instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que usam o coletor de dados.</span><span class="sxs-lookup"><span data-stu-id="70f6e-103">This topic describes how to configure the management data warehouse to support data storage on a single instance or multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are using the data collector.</span></span> <span data-ttu-id="70f6e-104">Essas instâncias podem estar no mesmo servidor ou em servidores diferentes.</span><span class="sxs-lookup"><span data-stu-id="70f6e-104">These instances can be on the same server or on different servers.</span></span> <span data-ttu-id="70f6e-105">Este tópico também fornece descrições da interface do usuário para a caixa de diálogo [Assistente para Configurar Data Warehouse de Gerenciamento](#Wizard) .</span><span class="sxs-lookup"><span data-stu-id="70f6e-105">This topic also provides descriptions of the user interface for the [Configure Data Management Warehouse Wizard](#Wizard) dialog box.</span></span> <span data-ttu-id="70f6e-106">Para obter informações sobre como configurar um coletor de dados, consulte [Configure Properties of a Data Collector](configure-properties-of-a-data-collector.md).</span><span class="sxs-lookup"><span data-stu-id="70f6e-106">For information about configuring a data collector, see [Configure Properties of a Data Collector](configure-properties-of-a-data-collector.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="70f6e-107">Se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent estiver configurado para ser executado usando uma das contas de serviço do Sistema (Sistema Local, Serviço de Rede ou Serviço Local) e o data warehouse de gerenciamento for criado em uma instância diferente do coletor de dados, você deverá configurar os conjuntos de coleta para usar um proxy para carregar dados no data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="70f6e-107">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent is configured to run using one of the System service accounts (Local System, Network Service, or Local Service), and the management data warehouse is created on a different instance from the data collector, you must configure collection sets to use a proxy for uploading data to the management data warehouse.</span></span>  
  
### <a name="configure-the-management-data-warehouse-on-a-single-instance-or-multiple-instances-of-ssnoversion"></a><span data-ttu-id="70f6e-108">Configurar o data warehouse de gerenciamento em uma ou várias instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70f6e-108">Configure the management data warehouse on a single instance or multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
1.  <span data-ttu-id="70f6e-109">Verifique se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent está em execução.</span><span class="sxs-lookup"><span data-stu-id="70f6e-109">Ensure that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent is running.</span></span>  
  
2.  <span data-ttu-id="70f6e-110">No Pesquisador de Objetos, expanda o nó **Gerenciamento** .</span><span class="sxs-lookup"><span data-stu-id="70f6e-110">In Object Explorer, expand the **Management** node.</span></span>  
  
3.  <span data-ttu-id="70f6e-111">Clique com o botão direito do mouse em **Coleta de Dados**, expanda **Tarefas**e clique em **Configurar Data Warehouse de Gerenciamento**.</span><span class="sxs-lookup"><span data-stu-id="70f6e-111">Right-click **Data Collection**, expand **Tasks**, and then click **Configure Management Data Warehouse**.</span></span>  
  
4.  <span data-ttu-id="70f6e-112">Use o [Assistente para Configurar Data Warehouse de Gerenciamento](#Wizard) para criar um data warehouse de gerenciamento, configurar logons, habilitar a coleta de dados e iniciar os **Conjuntos de Coleta de Dados do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="70f6e-112">Use the [Configure Management Data Warehouse Wizard](#Wizard) to create a management data warehouse, configure logins, enable data collection, and start the **System Data Collection Sets**.</span></span>  
  
     <span data-ttu-id="70f6e-113">Para configurar várias instâncias, continue com a etapa 5.</span><span class="sxs-lookup"><span data-stu-id="70f6e-113">To configure multiple instances, continue with step 5.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="70f6e-114">O uso de proxies é considerado uma prática recomendada em implantações em que o coletor de dados está instalado em várias instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que usam o mesmo data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="70f6e-114">It is considered best practice to use proxies in deployments where the data collector is installed on multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are using the same management data warehouse.</span></span>  
  
5.  <span data-ttu-id="70f6e-115">Abra o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] em outra instância e proceda de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="70f6e-115">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] on another instance and do either of the following:</span></span>  
  
    -   <span data-ttu-id="70f6e-116">Use o Assistente para Configurar Data Warehouse de Gerenciamento para configurar a coleta de dados para o data warehouse de gerenciamento existente.</span><span class="sxs-lookup"><span data-stu-id="70f6e-116">Use the Configure Management Data Warehouse wizard to configure data collection for the existing management data warehouse.</span></span>  
  
    -   <span data-ttu-id="70f6e-117">Clique com o botão direito do mouse em **Coleta de Dados**e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="70f6e-117">Right-click **Data Collection**, and then click **Properties**.</span></span> <span data-ttu-id="70f6e-118">Na guia **Geral** , especifique o data warehouse de gerenciamento existente e o servidor no qual ele está instalado.</span><span class="sxs-lookup"><span data-stu-id="70f6e-118">On the **General** tab, specify the existing management data warehouse and the server that it is installed on.</span></span>  
  
6.  <span data-ttu-id="70f6e-119">Repita a etapa 5 até que todas as instâncias do banco de dados que usam o coletor de dados sejam configuradas para carregar os dados para o data warehouse de gerenciamento compartilhado.</span><span class="sxs-lookup"><span data-stu-id="70f6e-119">Repeat step 5 until all the database instances that use the data collector are configured to upload data to the shared management data warehouse.</span></span>  
  
####  <a name="configure-management-data-warehouse-wizard"></a><a name="Wizard"></a> <span data-ttu-id="70f6e-120">Configurar o Assistente de Data Warehouse de Gerenciamento</span><span class="sxs-lookup"><span data-stu-id="70f6e-120">Configure Management Data Warehouse Wizard</span></span>  
 <span data-ttu-id="70f6e-121">**Página de boas-vindas**</span><span class="sxs-lookup"><span data-stu-id="70f6e-121">**Welcome Page**</span></span>  
  
 <span data-ttu-id="70f6e-122">A página Bem-vindo é a página inicial do Assistente para Configurar Coleta de Dados.</span><span class="sxs-lookup"><span data-stu-id="70f6e-122">The Welcome page is the starting page of the Configure Data Collection Wizard.</span></span> <span data-ttu-id="70f6e-123">A exibição dessa página é opcional.</span><span class="sxs-lookup"><span data-stu-id="70f6e-123">Displaying this page is optional.</span></span>  
  
 <span data-ttu-id="70f6e-124">**Não mostrar essa página inicial novamente.**</span><span class="sxs-lookup"><span data-stu-id="70f6e-124">**Do not show this starting page again.**</span></span>  
 <span data-ttu-id="70f6e-125">Selecione para omitir esta página na próxima vez em que você iniciar o Assistente para Configurar Coleta de Dados.</span><span class="sxs-lookup"><span data-stu-id="70f6e-125">Select to suppress this page the next time you launch the Configure Data Collection Wizard.</span></span>  
  
 <span data-ttu-id="70f6e-126">**Página Armazenamento do Assistente para Configurar Data Warehouse de Gerenciamento**</span><span class="sxs-lookup"><span data-stu-id="70f6e-126">**Configure Management Data Warehouse Storage Page**</span></span>  
  
 <span data-ttu-id="70f6e-127">Use esta página para selecionar um servidor de banco de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e o data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="70f6e-127">Use this page to select a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database server and management data warehouse.</span></span> <span data-ttu-id="70f6e-128">O data warehouse de gerenciamento é um banco de dados relacional que armazenará dados coletados.</span><span class="sxs-lookup"><span data-stu-id="70f6e-128">The management data warehouse is a relational database that will store collected data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="70f6e-129">Você deve ter o nível apropriado de permissões para criar o data warehouse de gerenciamento no servidor.</span><span class="sxs-lookup"><span data-stu-id="70f6e-129">You must have the appropriate level of permissions in order to create the management data warehouse on the server.</span></span> <span data-ttu-id="70f6e-130">Para obter mais informações, consulte [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="70f6e-130">For more information, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span> <span data-ttu-id="70f6e-131">Você também deve ter o nível apropriado de permissões para criar logons para funções de data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="70f6e-131">You also must have the appropriate level of permissions to create logins for management data warehouse roles.</span></span>  
  
 <span data-ttu-id="70f6e-132">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="70f6e-132">**Server name**</span></span>  
 <span data-ttu-id="70f6e-133">Especifica o nome do servidor que hospedará o data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="70f6e-133">Specifies the name of the server that will host the management data warehouse.</span></span>  
  
 <span data-ttu-id="70f6e-134">Ao configurar um data warehouse de gerenciamento, **Nome do servidor** será sempre o nome do servidor local e não será possível alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="70f6e-134">When configuring a management data warehouse, **Server name** is always the name of the local server and cannot be modified.</span></span>  
  
 <span data-ttu-id="70f6e-135">**Nome do banco de dados**</span><span class="sxs-lookup"><span data-stu-id="70f6e-135">**Database name**</span></span>  
 <span data-ttu-id="70f6e-136">Especifica o banco de dados relacional que armazenará os dados coletados.</span><span class="sxs-lookup"><span data-stu-id="70f6e-136">Specifies the relational database that will store collected data.</span></span> <span data-ttu-id="70f6e-137">Selecione na lista um banco de dados existente ou clique em **Novo** para criar um novo banco de dados usando a caixa de diálogo **Novo Banco de Dados** .</span><span class="sxs-lookup"><span data-stu-id="70f6e-137">Use the list to select an existing database or click **New** to create a new database using the **New Database** dialog.</span></span>  
  
 <span data-ttu-id="70f6e-138">O opção **Novo** só estará disponível durante a configuração de um conjunto de coleta de dados.</span><span class="sxs-lookup"><span data-stu-id="70f6e-138">The **New** option is available only when configuring a data collection set</span></span>  
  
 <span data-ttu-id="70f6e-139">**Página Mapear Logons e Usuários**</span><span class="sxs-lookup"><span data-stu-id="70f6e-139">**Map Logins and Users Page**</span></span>  
  
 <span data-ttu-id="70f6e-140">Use esta página para mapear logons para funções de usuário de banco de dados no data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="70f6e-140">Use this page to map logins to database user roles for the management data warehouse.</span></span>  
  
 <span data-ttu-id="70f6e-141">**Usuários mapeados para este logon**</span><span class="sxs-lookup"><span data-stu-id="70f6e-141">**Users mapped to this login**</span></span>  
 <span data-ttu-id="70f6e-142">Exibe os logons existentes no servidor que hospedará o data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="70f6e-142">Displays the existing logins on the server that will host the management data warehouse.</span></span> <span data-ttu-id="70f6e-143">Cada linha contém uma caixa de seleção **Mapear** editável, um nome de **Logon** e um **Tipo** de logon.</span><span class="sxs-lookup"><span data-stu-id="70f6e-143">Each row contains an editable **Map** check box, a **Login** name, and a **Type** of login.</span></span>  
  
 <span data-ttu-id="70f6e-144">Especifique um logon marcando a caixa de seleção **Mapear** para o logon.</span><span class="sxs-lookup"><span data-stu-id="70f6e-144">Specify a login by selecting the **Map** checkbox for the login.</span></span>  
  
 <span data-ttu-id="70f6e-145">**Associação de função de banco de dados para:** *\<data warehouse name>*</span><span class="sxs-lookup"><span data-stu-id="70f6e-145">**Database role membership for:**  *\<data warehouse name>*</span></span>  
 <span data-ttu-id="70f6e-146">Selecione a função do data warehouse de gerenciamento para o qual o logon está mapeado marcando a caixa de seleção em uma ou mais da opções a seguir:</span><span class="sxs-lookup"><span data-stu-id="70f6e-146">Select the management data warehouse role that the login is mapped to by clicking the checkbox by one or more of the following options:</span></span>  
  
-   <span data-ttu-id="70f6e-147">**mdw_admin**</span><span class="sxs-lookup"><span data-stu-id="70f6e-147">**mdw_admin**</span></span>  
  
-   <span data-ttu-id="70f6e-148">**mdw_reader**</span><span class="sxs-lookup"><span data-stu-id="70f6e-148">**mdw_reader**</span></span>  
  
-   <span data-ttu-id="70f6e-149">**mdw_writer**</span><span class="sxs-lookup"><span data-stu-id="70f6e-149">**mdw_writer**</span></span>  
  
 <span data-ttu-id="70f6e-150">**Novo Logon**</span><span class="sxs-lookup"><span data-stu-id="70f6e-150">**New Login**</span></span>  
 <span data-ttu-id="70f6e-151">Abra a caixa de diálogo **Logon - Novo** e crie um novo logon para o data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="70f6e-151">Open the **Login - New** dialog box and create a new login for the management data warehouse.</span></span>  
  
 <span data-ttu-id="70f6e-152">**Página Concluir o Assistente**</span><span class="sxs-lookup"><span data-stu-id="70f6e-152">**Complete the Wizard Page**</span></span>  
  
 <span data-ttu-id="70f6e-153">Use esta página para verificar e concluir a configuração de coleta de dados.</span><span class="sxs-lookup"><span data-stu-id="70f6e-153">Use this page to verify and complete data collection configuration.</span></span> <span data-ttu-id="70f6e-154">A árvore exibida na janela de visualização mostra quais configurações serão aplicadas, além de quais ações serão executadas quando você clicar em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="70f6e-154">The tree displayed in the viewing window shows what configurations will applied as well as what actions will take place when you click **Finish**.</span></span>  
  
 <span data-ttu-id="70f6e-155">**Página Progresso do Assistente para Configurar Coleta de Dados**</span><span class="sxs-lookup"><span data-stu-id="70f6e-155">**Configure Data Collection Wizard Progress Page**</span></span>  
  
 <span data-ttu-id="70f6e-156">Use esta página para exibir os resultados de cada etapa de configuração.</span><span class="sxs-lookup"><span data-stu-id="70f6e-156">Use this page to view the results of each configuration step.</span></span>  
  
 <span data-ttu-id="70f6e-157">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="70f6e-157">**Details**</span></span>  
 <span data-ttu-id="70f6e-158">Exibe cada etapa de configuração como uma linha na grade **Detalhes** .</span><span class="sxs-lookup"><span data-stu-id="70f6e-158">Displays each configuration step as a row in the **Details** grid.</span></span> <span data-ttu-id="70f6e-159">Cada linha contém uma coluna **Ação** que descreve a etapa e uma coluna **Status** que indica o sucesso ou a falha da etapa.</span><span class="sxs-lookup"><span data-stu-id="70f6e-159">Each row contains an **Action** column that describes the step, and a **Status** column that indicates the success or failure of the step.</span></span> <span data-ttu-id="70f6e-160">Se houver um erro, será exibida uma mensagem na coluna **Mensagem** .</span><span class="sxs-lookup"><span data-stu-id="70f6e-160">If there is an error, a message appears in the **Message** column.</span></span>  
  
 <span data-ttu-id="70f6e-161">**Parar**</span><span class="sxs-lookup"><span data-stu-id="70f6e-161">**Stop**</span></span>  
 <span data-ttu-id="70f6e-162">Pare o processamento do assistente.</span><span class="sxs-lookup"><span data-stu-id="70f6e-162">Stop wizard processing.</span></span>  
  
 <span data-ttu-id="70f6e-163">**Report**</span><span class="sxs-lookup"><span data-stu-id="70f6e-163">**Report**</span></span>  
 <span data-ttu-id="70f6e-164">Exiba um relatório da configuração de coleta de dados.</span><span class="sxs-lookup"><span data-stu-id="70f6e-164">View a report of the data collection configuration.</span></span> <span data-ttu-id="70f6e-165">São fornecidas as seguintes opções de relatório:</span><span class="sxs-lookup"><span data-stu-id="70f6e-165">The following report options are provided:</span></span>  
  
-   <span data-ttu-id="70f6e-166">Exibir Relatório</span><span class="sxs-lookup"><span data-stu-id="70f6e-166">View Report</span></span>  
  
-   <span data-ttu-id="70f6e-167">Salvar Relatório no Arquivo</span><span class="sxs-lookup"><span data-stu-id="70f6e-167">Save Report to File</span></span>  
  
-   <span data-ttu-id="70f6e-168">Copiar Relatório na Área de Transferência</span><span class="sxs-lookup"><span data-stu-id="70f6e-168">Copy Report to Clipboard</span></span>  
  
-   <span data-ttu-id="70f6e-169">Enviar Relatório como Email</span><span class="sxs-lookup"><span data-stu-id="70f6e-169">Send Report as E-mail</span></span>  
  
 <span data-ttu-id="70f6e-170">**Fechar**</span><span class="sxs-lookup"><span data-stu-id="70f6e-170">**Close**</span></span>  
 <span data-ttu-id="70f6e-171">Feche o assistente.</span><span class="sxs-lookup"><span data-stu-id="70f6e-171">Close the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70f6e-172">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="70f6e-172">See Also</span></span>  
 <span data-ttu-id="70f6e-173">[sp_syscollector_enable_collector &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syscollector-enable-collector-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="70f6e-173">[sp_syscollector_enable_collector &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syscollector-enable-collector-transact-sql) </span></span>  
 <span data-ttu-id="70f6e-174">[sp_syscollector_disable_collector &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syscollector-disable-collector-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="70f6e-174">[sp_syscollector_disable_collector &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syscollector-disable-collector-transact-sql) </span></span>  
 <span data-ttu-id="70f6e-175">[Coleta de Dados](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="70f6e-175">[Data Collection](data-collection.md) </span></span>  
 [<span data-ttu-id="70f6e-176">Gerenciar coleta de dados</span><span class="sxs-lookup"><span data-stu-id="70f6e-176">Manage Data Collection</span></span>](manage-data-collection.md)  
  
  
