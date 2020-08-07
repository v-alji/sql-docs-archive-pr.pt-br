---
title: Desinstalar uma instância existente do SQL Server (configuração) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- removing instances of SQL Server
- uninstalling instances of SQL Server
- removing SQL Server
- instances of SQL Server, uninstalling
- uninstalling SQL Server
ms.assetid: 3c64b29d-61d7-4b86-961c-0de62261c6a1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 51d426a12a2f7f1b7bedbfb7770c4d9cb369f12b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573443"
---
# <a name="uninstall-an-existing-instance-of-sql-server-setup"></a><span data-ttu-id="1cad6-102">Desinstalar uma instância existente do SQL Server (Instalação)</span><span class="sxs-lookup"><span data-stu-id="1cad6-102">Uninstall an Existing Instance of SQL Server (Setup)</span></span>
  <span data-ttu-id="1cad6-103">Este artigo descreve como desinstalar uma instância autônoma do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1cad6-103">This article describes how to uninstall a stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1cad6-104">Seguindo as etapas deste tópico, você também prepara o sistema para que seja possível reinstalar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1cad6-104">By following the steps in this topic, you also prepare the system so that you can reinstall [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1cad6-105">Para desinstalar uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], você deve ser um administrador local com permissão para fazer logon como um serviço.</span><span class="sxs-lookup"><span data-stu-id="1cad6-105">To uninstall an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must be a local administrator with permission to log on as a service.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1cad6-106">Para desinstalar um cluster de failover do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , use a função Remover Nó fornecida na instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para remover cada nó individualmente.</span><span class="sxs-lookup"><span data-stu-id="1cad6-106">To uninstall a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, use the Remove Node functionality provided by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup to remove each node individually.</span></span> <span data-ttu-id="1cad6-107">Para obter mais informações, consulte [Adicionar ou remover nós em um cluster de failover do SQL Server &#40;Instalação&#41;](../failover-clusters/install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md)</span><span class="sxs-lookup"><span data-stu-id="1cad6-107">For more information, see [Add or Remove Nodes in a SQL Server Failover Cluster &#40;Setup&#41;](../failover-clusters/install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md)</span></span>  
  
 <span data-ttu-id="1cad6-108">Considere as seguintes informações importantes antes de desinstalar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="1cad6-108">Consider the following important information before you uninstall [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="1cad6-109">Antes de remover componentes do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de um computador que tenha a quantidade mínima necessária de memória física, verifique se o tamanho do arquivo de paginação é suficiente.</span><span class="sxs-lookup"><span data-stu-id="1cad6-109">Before you remove [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components from a computer that has the minimum required amount of physical memory, make sure that the page file size is sufficient.</span></span> <span data-ttu-id="1cad6-110">O tamanho do arquivo de paginação deve ser igual a duas vezes a quantidade de memória física.</span><span class="sxs-lookup"><span data-stu-id="1cad6-110">The page file size must be equal to two times the amount of physical memory.</span></span> <span data-ttu-id="1cad6-111">Memória virtual insuficiente pode provocar uma remoção incompleta do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1cad6-111">Insufficient virtual memory can cause an incomplete removal of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="1cad6-112">Se você tiver várias instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], o Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] será desinstalado automaticamente quando a última instância do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] for desinstalada.</span><span class="sxs-lookup"><span data-stu-id="1cad6-112">If you have multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser uninstalls automatically when the last instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] is uninstalled.</span></span>  
  
     <span data-ttu-id="1cad6-113">Se desejar desinstalar todos os componentes do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], você deverá desinstalar manualmente o componente Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em **Programas e Recursos** no **Painel de Controle**.</span><span class="sxs-lookup"><span data-stu-id="1cad6-113">If you want to uninstall all components of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you must uninstall the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser component manually from **Programs and Features** in **Control Panel**.</span></span>  
  
### <a name="before-you-uninstall"></a><span data-ttu-id="1cad6-114">Antes da desinstalação</span><span class="sxs-lookup"><span data-stu-id="1cad6-114">Before You Uninstall</span></span>  
  
1.  <span data-ttu-id="1cad6-115">**Faça backup dos dados.**</span><span class="sxs-lookup"><span data-stu-id="1cad6-115">**Back up your data.**</span></span> <span data-ttu-id="1cad6-116">Embora essa não seja uma etapa necessária, pode haver bancos de dados que você queira salvar em seu estado atual.</span><span class="sxs-lookup"><span data-stu-id="1cad6-116">Although this is not a required step, you might have databases that you want to save in their present state.</span></span> <span data-ttu-id="1cad6-117">Você também pode desejar salvar alterações que foram feitas nos bancos de dados do sistema.</span><span class="sxs-lookup"><span data-stu-id="1cad6-117">You might also want to save changes that were made to the system databases.</span></span> <span data-ttu-id="1cad6-118">Se qualquer situação for verdadeira, certifique-se de fazer backup dos dados antes de desinstalar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1cad6-118">If either situation is true, make sure that back up the data before you uninstall [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1cad6-119">Como alternativa, salve uma cópia de todos os dados e arquivos de log em uma pasta que não seja a pasta do MSSQL.</span><span class="sxs-lookup"><span data-stu-id="1cad6-119">Alternatively, save a copy of all the data and log files in a folder other than the MSSQL folder.</span></span> <span data-ttu-id="1cad6-120">A pasta do MSSQL é excluída durante a desinstalação.</span><span class="sxs-lookup"><span data-stu-id="1cad6-120">The MSSQL folder is deleted during uninstallation.</span></span>  
  
     <span data-ttu-id="1cad6-121">Os arquivos que você deve salvar incluem os arquivos de banco de dados a seguir:</span><span class="sxs-lookup"><span data-stu-id="1cad6-121">The files that you must save include the following database files:</span></span>  
  
    -   <span data-ttu-id="1cad6-122">Master.mdf</span><span class="sxs-lookup"><span data-stu-id="1cad6-122">Master.mdf</span></span>  
  
    -   <span data-ttu-id="1cad6-123">Mastlog.ldf</span><span class="sxs-lookup"><span data-stu-id="1cad6-123">Mastlog.ldf</span></span>  
  
    -   <span data-ttu-id="1cad6-124">Model.mdf</span><span class="sxs-lookup"><span data-stu-id="1cad6-124">Model.mdf</span></span>  
  
    -   <span data-ttu-id="1cad6-125">Modellog.ldf</span><span class="sxs-lookup"><span data-stu-id="1cad6-125">Modellog.ldf</span></span>  
  
    -   <span data-ttu-id="1cad6-126">Msdbdata.mdf</span><span class="sxs-lookup"><span data-stu-id="1cad6-126">Msdbdata.mdf</span></span>  
  
    -   <span data-ttu-id="1cad6-127">Msdblog.ldf</span><span class="sxs-lookup"><span data-stu-id="1cad6-127">Msdblog.ldf</span></span>  
  
    -   <span data-ttu-id="1cad6-128">Mssqlsystemresource.mdf</span><span class="sxs-lookup"><span data-stu-id="1cad6-128">Mssqlsystemresource.mdf</span></span>  
  
    -   <span data-ttu-id="1cad6-129">Mssqlsystemresource.ldf</span><span class="sxs-lookup"><span data-stu-id="1cad6-129">Mssqlsustemresource.ldf</span></span>  
  
    -   <span data-ttu-id="1cad6-130">Tempdb.mdf</span><span class="sxs-lookup"><span data-stu-id="1cad6-130">Tempdb.mdf</span></span>  
  
    -   <span data-ttu-id="1cad6-131">Templog.ldf</span><span class="sxs-lookup"><span data-stu-id="1cad6-131">Templog.ldf</span></span>  
  
    -   <span data-ttu-id="1cad6-132">`ReportServer[$InstanceName]`(Isso é o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] banco de dados padrão.)</span><span class="sxs-lookup"><span data-stu-id="1cad6-132">`ReportServer[$InstanceName]` (Thisis the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] default database.)</span></span>  
  
    -   <span data-ttu-id="1cad6-133">ReportServer[$InstanceName]TempDB (Este é o banco de dados temporário padrão do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .)</span><span class="sxs-lookup"><span data-stu-id="1cad6-133">ReportServer[$InstanceName]TempDB (This is the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] default temporary database.)</span></span>  
  
2.  <span data-ttu-id="1cad6-134">**Exclua os grupos de segurança locais.**</span><span class="sxs-lookup"><span data-stu-id="1cad6-134">**Delete the local security groups.**</span></span> <span data-ttu-id="1cad6-135">Antes de desinstalar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], exclua os grupos de segurança locais dos componentes do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1cad6-135">Before you uninstall [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], delete the local security groups for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components.</span></span>  
  
3.  <span data-ttu-id="1cad6-136">**Interromper todos**  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **os serviços do .**</span><span class="sxs-lookup"><span data-stu-id="1cad6-136">**Stop all**  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **services.**</span></span> <span data-ttu-id="1cad6-137">É recomendável interromper todos os serviços do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] antes de desinstalar os componentes do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1cad6-137">We recommend that you stop all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services before you uninstall [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components.</span></span> <span data-ttu-id="1cad6-138">Conexões ativas podem impedir a desinstalação com êxito.</span><span class="sxs-lookup"><span data-stu-id="1cad6-138">Active connections can prevent successful uninstallation.</span></span>  
  
4.  <span data-ttu-id="1cad6-139">**Use uma conta que tenha as permissões apropriadas.**</span><span class="sxs-lookup"><span data-stu-id="1cad6-139">**Use an account that has the appropriate permissions.**</span></span> <span data-ttu-id="1cad6-140">Faça logon no servidor usando a conta de serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou usando uma conta que tenha permissões equivalentes.</span><span class="sxs-lookup"><span data-stu-id="1cad6-140">Log on to the server by using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account or by using an account that has equivalent permissions.</span></span> <span data-ttu-id="1cad6-141">Por exemplo, é possível fazer logon no servidor com uma conta que seja membro do grupo Administradores local.</span><span class="sxs-lookup"><span data-stu-id="1cad6-141">For example, you can log on to the server by using an account that is a member of the local Administrators group.</span></span>  
  
### <a name="to-uninstall-an-instance-of-ssnoversion"></a><span data-ttu-id="1cad6-142">To Uninstall an Instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1cad6-142">To Uninstall an Instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
1.  <span data-ttu-id="1cad6-143">Para começar o processo de desinstalação, vá para o **Painel de Controle** e clique em **Programa e Recursos**.</span><span class="sxs-lookup"><span data-stu-id="1cad6-143">To begin the uninstall process, go to **Control Panel** and then **Programs and Features**.</span></span>  
  
2.  <span data-ttu-id="1cad6-144">Clique com o botão direito do mouse **[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]** e selecione **desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="1cad6-144">Right click **[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]** and select **Uninstall**.</span></span> <span data-ttu-id="1cad6-145">Clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="1cad6-145">Then click **Remove**.</span></span> <span data-ttu-id="1cad6-146">Isso inicia o Assistente de Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1cad6-146">This starts the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard.</span></span>  
  
     <span data-ttu-id="1cad6-147">As Regras de Suporte à Instalação são executadas para verificar a configuração do computador.</span><span class="sxs-lookup"><span data-stu-id="1cad6-147">Setup Support Rules runs to verify your computer configuration.</span></span> <span data-ttu-id="1cad6-148">Para continuar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1cad6-148">To continue, click **Next**.</span></span>  
  
3.  <span data-ttu-id="1cad6-149">Na página Selecionar Instância, use a caixa suspensa para especificar uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a ser removida ou especifique a opção para remover somente os recursos compartilhados e as ferramentas de gerenciamento do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1cad6-149">On the Select Instance page, use the drop-down box to specify an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to remove, or specify the option to remove only the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] shared features and management tools.</span></span> <span data-ttu-id="1cad6-150">Para continuar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1cad6-150">To continue, click **Next**.</span></span>  
  
4.  <span data-ttu-id="1cad6-151">Na página Selecionar Recursos, especifique os recursos a serem removidos da instância especificada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1cad6-151">On the Select Features page, specify the features to remove from the specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="1cad6-152">As regras de remoção são executadas para verificar se a operação pode ser concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="1cad6-152">Removal rules runs to verify that the operation can complete successfully.</span></span>  
  
5.  <span data-ttu-id="1cad6-153">Na página **Pronto para Desinstalar** , examine a lista de componentes e de recursos que serão desinstalados.</span><span class="sxs-lookup"><span data-stu-id="1cad6-153">On the **Ready to Remove** page, review the list of components and features that will be uninstalled.</span></span> <span data-ttu-id="1cad6-154">Clique em **Remover** para começar a desinstalação</span><span class="sxs-lookup"><span data-stu-id="1cad6-154">Click **Remove** to begin uninstalling</span></span>  
  
6.  <span data-ttu-id="1cad6-155">Imediatamente após desinstalar a última instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , os outros programas associados com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ainda estarão visíveis na lista de programas em **Programas e Recursos**.</span><span class="sxs-lookup"><span data-stu-id="1cad6-155">Immediately after you uninstall the last [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance, the other programs associated with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will still be visible in the list of programs in **Programs and Features**.</span></span> <span data-ttu-id="1cad6-156">No entanto, se você fechar **Programas e Recursos**, na próxima vez que abrir **Programas e Recursos**, ele atualizará a lista de programas, para mostrar apenas o que realmente ainda está instalado.</span><span class="sxs-lookup"><span data-stu-id="1cad6-156">However, if you close **Programs and Features**, the next time you open **Programs and Features**, it will refresh the list of programs, to show only the ones that are actually still installed.</span></span>  
  
### <a name="if-the-uninstallation-fails"></a><span data-ttu-id="1cad6-157">Em caso de falha na desinstalação</span><span class="sxs-lookup"><span data-stu-id="1cad6-157">If the Uninstallation Fails</span></span>  
  
1.  <span data-ttu-id="1cad6-158">Se o processo de desinstalação não for concluído com êxito, tente corrigir o problema que causou a falha na desinstalação.</span><span class="sxs-lookup"><span data-stu-id="1cad6-158">If the uninstallation process does not complete successfully, attempt to fix the problem that caused the uninstallation to fail.</span></span> <span data-ttu-id="1cad6-159">Os seguintes artigos podem ajudá-lo a compreender a causa da falha na desinstalação:</span><span class="sxs-lookup"><span data-stu-id="1cad6-159">The following articles can help you understand the cause of the failed uninstallation:</span></span>  
  
    -   [<span data-ttu-id="1cad6-160">Como identificar problemas de instalação do SQL Server 2008 nos arquivos de log de instalação</span><span class="sxs-lookup"><span data-stu-id="1cad6-160">How to identify SQL Server 2008 setup issues in the setup log files</span></span>](https://support.microsoft.com/kb/955396/en-us)  
  
    -   [<span data-ttu-id="1cad6-161">Exibir e ler arquivos de log da Instalação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="1cad6-161">View and Read SQL Server Setup Log Files</span></span>](../../database-engine/install-windows/view-and-read-sql-server-setup-log-files.md)  
  
2.  <span data-ttu-id="1cad6-162">Se você não conseguir corrigir a causa da falha na desinstalação, entre em contato com o suporte da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1cad6-162">If you are unable to fix the cause of the uninstallation failure, you can contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Support.</span></span> <span data-ttu-id="1cad6-163">Em alguns casos, como a exclusão não intencional de arquivos importantes, talvez seja necessário reinstalar o sistema operacional antes de reinstalar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no computador.</span><span class="sxs-lookup"><span data-stu-id="1cad6-163">In some cases, such as unintentional deletion of important files, reinstalling the operating system may be required before reinstalling [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on the computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cad6-164">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1cad6-164">See Also</span></span>  
 [<span data-ttu-id="1cad6-165">Exibir e ler arquivos de log da Instalação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="1cad6-165">View and Read SQL Server Setup Log Files</span></span>](../../database-engine/install-windows/view-and-read-sql-server-setup-log-files.md)  
  
  
