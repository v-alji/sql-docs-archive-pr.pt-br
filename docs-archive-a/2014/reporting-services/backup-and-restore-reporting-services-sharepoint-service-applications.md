---
title: Backup e restauração Reporting Services aplicativos de serviço do SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: dfb4ed77-90e5-4273-b690-89a945508ed2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 488659d269542381be9bcf1b1b6115acf89f8a98
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573818"
---
# <a name="backup-and-restore-reporting-services-sharepoint-service-applications"></a><span data-ttu-id="009d6-102">Aplicativos de serviço Sharepoint de backup e restauração do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="009d6-102">Backup and Restore Reporting Services SharePoint Service Applications</span></span>
  <span data-ttu-id="009d6-103">Este tópico descreve como fazer backup de um aplicativo de serviços [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] e restaurá-lo usando a Administração Central do SharePoint ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="009d6-103">This topic describes how to backup and restore a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] services application using SharePoint Central Administration or PowerShell.</span></span> <span data-ttu-id="009d6-104">O tópico contém:</span><span class="sxs-lookup"><span data-stu-id="009d6-104">The topic contains:</span></span>  
  
-   [<span data-ttu-id="009d6-105">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="009d6-105">Limitations and Restrictions</span></span>](#bkmk_Restrictions)  
  
-   [<span data-ttu-id="009d6-106">Fazer backup do aplicativo de serviço</span><span class="sxs-lookup"><span data-stu-id="009d6-106">Backup The Service application</span></span>](#bkmk_backup)  
  
-   [<span data-ttu-id="009d6-107">Restaurar o aplicativo de serviço</span><span class="sxs-lookup"><span data-stu-id="009d6-107">Restore the Service Application</span></span>](#bkmk_restore)  
  
##  <a name="before-you-begin"></a><a name="bkmk_BeforeYouBegin"></a> <span data-ttu-id="009d6-108">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="009d6-108">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="bkmk_Restrictions"></a> <span data-ttu-id="009d6-109">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="009d6-109">Limitations and Restrictions</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="009d6-110">Os aplicativos de serviço do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] podem ser parcialmente copiados em backup e restaurados usando a funcionalidade de backup e restauração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="009d6-110">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service applications can partially be backed up and restored using the SharePoint backup and restore functionality.</span></span> <span data-ttu-id="009d6-111">**São necessárias etapas adicionais** e as etapas são documentadas neste tópico.</span><span class="sxs-lookup"><span data-stu-id="009d6-111">**Additional steps are required** and the steps are documented in this topic.</span></span> <span data-ttu-id="009d6-112">No momento, o processo de backup **não** faz backup das chaves de criptografia e das credenciais para UEAs (contas de execução autônomas) ou autenticação de janelas no banco de dados do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="009d6-112">Currently the backup process **does not** backup encryption keys and credentials for unattended execution accounts (UEA) or windows authentication to the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] database.</span></span>  
  
###  <a name="recommendations"></a><a name="bkmk_recommendations"></a> <span data-ttu-id="009d6-113">Recomendações</span><span class="sxs-lookup"><span data-stu-id="009d6-113">Recommendations</span></span>  
  
-   <span data-ttu-id="009d6-114">Faça backup das chave de criptografia antes de iniciar o backup do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="009d6-114">Backup the encryption keys before starting the SharePoint backup.</span></span> <span data-ttu-id="009d6-115">Se você não fizer backup das chave de criptografia, não poderá acessar os dados criptografados, seguindo a restauração do aplicativo de serviço.</span><span class="sxs-lookup"><span data-stu-id="009d6-115">If you do not backup the encryption keys, then you will not be able to access your encrypted data, following the restore of the service application.</span></span> <span data-ttu-id="009d6-116">Você precisará excluir seus dados criptografados.</span><span class="sxs-lookup"><span data-stu-id="009d6-116">You will need to delete your encrypted data.</span></span>  
  
-   <span data-ttu-id="009d6-117">Verifique se o aplicativo de serviço [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] está usando a UEA ou a autenticação do Windows para acesso ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="009d6-117">Verify if your [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application is using UEA or Windows authentication for database access.</span></span> <span data-ttu-id="009d6-118">Se ele estiver usando uma delas, verifique quais são as credenciais apropriadas para que você possa configurar o aplicativo de serviço após o processo de restauração.</span><span class="sxs-lookup"><span data-stu-id="009d6-118">If it is using either, verify what the proper credentials are so you can correctly configure the service application after the restore process.</span></span>  
  
-   <span data-ttu-id="009d6-119">Verifique se o log de backup do SharePoint foi criado na mesma pasta do arquivo de backup.</span><span class="sxs-lookup"><span data-stu-id="009d6-119">Review the SharePoint backup log is created in the same folder as the backup file.</span></span> <span data-ttu-id="009d6-120">O arquivo é geralmente nomeado **spbackup.log**</span><span class="sxs-lookup"><span data-stu-id="009d6-120">The file is typically named **spbackup.log**</span></span>  
  
##  <a name="backup-the-service-application"></a><a name="bkmk_backup"></a> <span data-ttu-id="009d6-121">Backup do aplicativo de serviço</span><span class="sxs-lookup"><span data-stu-id="009d6-121">Backup The Service application</span></span>  
 <span data-ttu-id="009d6-122">Conclua as seguintes etapas nesta ordem:</span><span class="sxs-lookup"><span data-stu-id="009d6-122">Complete the following steps in order:</span></span>  
  
1.  <span data-ttu-id="009d6-123">Backup das chaves de criptografia</span><span class="sxs-lookup"><span data-stu-id="009d6-123">Backup the encryption keys</span></span>  
  
2.  <span data-ttu-id="009d6-124">Backup do aplicativo de serviço</span><span class="sxs-lookup"><span data-stu-id="009d6-124">Backup the Service application</span></span>  
  
3.  <span data-ttu-id="009d6-125">Verifique se o aplicativo de serviço usa uma UEA ou uma autenticação do Windows para acesso ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="009d6-125">Verify if you service application uses an UEA or Windows authentication for database access.</span></span> <span data-ttu-id="009d6-126">Em caso afirmativo, anote as credenciais a fim de que você possa usá-las para configurar o aplicativo de serviço depois que ele for restaurado.</span><span class="sxs-lookup"><span data-stu-id="009d6-126">If it does, make a note of the credentials so you can use them to configure the service application after it is restored.</span></span>  
  
### <a name="backup-the-encryption-keys-using-central-administration"></a><span data-ttu-id="009d6-127">Backup das chaves de criptografia usando a Administração Central</span><span class="sxs-lookup"><span data-stu-id="009d6-127">Backup the Encryption Keys using Central Administration</span></span>  
 <span data-ttu-id="009d6-128">Para obter informações sobre como fazer backup das [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] chaves de criptografia, consulte a seção "chaves de criptografia" de [gerenciar um Reporting Services aplicativo de serviço do SharePoint](../../2014/reporting-services/manage-a-reporting-services-sharepoint-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="009d6-128">For information on backing up the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] encryption keys, see the "Encryption Keys" section of [Manage a Reporting Services SharePoint Service Application](../../2014/reporting-services/manage-a-reporting-services-sharepoint-service-application.md).</span></span>  
  
###  <a name="backup-the-service-application-using-sharepoint-central-administration"></a><a name="bkmk_centraladmin"></a> <span data-ttu-id="009d6-129">Backup do aplicativo de serviço usando a Administração Central do SharePoint</span><span class="sxs-lookup"><span data-stu-id="009d6-129">Backup the Service application Using SharePoint Central Administration</span></span>  
 <span data-ttu-id="009d6-130">Para fazer backup do aplicativo de serviço, conclua as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="009d6-130">To back up the Service Application, complete the following steps:</span></span>  
  
1.  <span data-ttu-id="009d6-131">Na Administração Central do SharePoint, clique em **Executar um backup** no grupo **Backup e restauração** .</span><span class="sxs-lookup"><span data-stu-id="009d6-131">In SharePoint Central Administration Click **Perform a backup** in the **Backup and Restore** group.</span></span>  
  
2.  <span data-ttu-id="009d6-132">No nó **Serviços Compartilhados** , expanda **Aplicativos de Serviços Compartilhados** e selecione seu aplicativo de serviço.</span><span class="sxs-lookup"><span data-stu-id="009d6-132">Under the **Shared Services** node, expand **Shared Service Applications** and select your service application.</span></span> <span data-ttu-id="009d6-133">Seu tipo será **Aplicativo de Serviço SQL Server Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="009d6-133">It will have a type of **SQL Server Reporting Services Service Application**.</span></span>  
  
3.  <span data-ttu-id="009d6-134">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="009d6-134">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="009d6-135">Digite o caminho do **Local do backup:** e clique em **Iniciar Backup**</span><span class="sxs-lookup"><span data-stu-id="009d6-135">Type the path for the **Backup location:** and click **Start Backup**</span></span>  
  
5.  <span data-ttu-id="009d6-136">Repita o processo acima, mas em vez de selecionar o aplicativo de serviço, expanda o nó **Proxies de Serviços Compartilhados** e selecione o proxy do aplicativo de serviço.</span><span class="sxs-lookup"><span data-stu-id="009d6-136">Repeat the process above but instead of selecting the service application, expand the **Shared Services Proxies** node, and select service application proxy.</span></span> <span data-ttu-id="009d6-137">Seu tipo será **Proxy do Aplicativo de Serviço SQL Server Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="009d6-137">It will have a type of **SQL Server Reporting Services Service Application Proxy**.</span></span>  
  
 <span data-ttu-id="009d6-138">Para obter mais informações, consulte os seguintes tópicos na documentação do SharePoint:</span><span class="sxs-lookup"><span data-stu-id="009d6-138">For more information, see the following topics in the SharePoint documentation:</span></span>  
  
 <span data-ttu-id="009d6-139">[Backup de um aplicativo de serviço (SharePoint Foundation 2010) na documentação do SharePoint](https://msdn.microsoft.com/library/ee748601.aspx).</span><span class="sxs-lookup"><span data-stu-id="009d6-139">[Back up a service application (SharePoint Foundation 2010) in the SharePoint documenttation](https://msdn.microsoft.com/library/ee748601.aspx).</span></span>  
  
 [<span data-ttu-id="009d6-140">Backup de um aplicativo de serviço (SharePoint Server 2010)</span><span class="sxs-lookup"><span data-stu-id="009d6-140">Back up a service application (SharePoint Server 2010)</span></span>](https://technet.microsoft.com/library/ee428318.aspx)  
  
### <a name="verify-execution-account-and-database-authentication"></a><span data-ttu-id="009d6-141">Verificar conta de execução e autenticação do banco de dados</span><span class="sxs-lookup"><span data-stu-id="009d6-141">Verify Execution Account and Database Authentication</span></span>  
 <span data-ttu-id="009d6-142">**Conta de Execução:** Para verificar se seu aplicativo de serviço está usando uma conta de execução:</span><span class="sxs-lookup"><span data-stu-id="009d6-142">**Execution Account:** To verify if your service application is using an execution account:</span></span>  
  
1.  <span data-ttu-id="009d6-143">Na administração central do SharePoint, clique em **gerenciar aplicativos de serviço** no grupo **Gerenciamento de aplicativos** .</span><span class="sxs-lookup"><span data-stu-id="009d6-143">In SharePoint Central Administration, click **Manage Service Applications** in the **Application Management** group.</span></span>  
  
2.  <span data-ttu-id="009d6-144">Clique no nome do aplicativo de serviço e, em seguida, clique em **gerenciar** na faixa de das faixas do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="009d6-144">Click the name of your service application and then click **Manage** in the SharePoint Ribbon.</span></span>  
  
3.  <span data-ttu-id="009d6-145">Clique em **Conta de Execução**.</span><span class="sxs-lookup"><span data-stu-id="009d6-145">Click **Execution Account**.</span></span>  
  
4.  <span data-ttu-id="009d6-146">Se uma conta de execução for configurada, você precisará saber as credenciais quando chegar a hora de restaurar o backup do aplicativo de serviço.</span><span class="sxs-lookup"><span data-stu-id="009d6-146">If an execution account is configured, you need to know the credentials when it is time to restore the service application backup.</span></span> <span data-ttu-id="009d6-147">Não continue com o procedimento de backup e restauração até que saiba as credenciais corretas.</span><span class="sxs-lookup"><span data-stu-id="009d6-147">Do not proceed with the backup and restore procedure until you know the correct credentials.</span></span>  
  
 <span data-ttu-id="009d6-148">**Autenticação de Banco de Dados:** Para verificar se o aplicativo de serviço está usando a Autenticação do Windows na autenticação do banco de dados:</span><span class="sxs-lookup"><span data-stu-id="009d6-148">**Database Authentication:** To verify if your service application is using Windows Authentication for the database authentication:</span></span>  
  
1.  <span data-ttu-id="009d6-149">Na administração central do SharePoint, clique em **gerenciar aplicativos de serviço** no grupo **Gerenciamento de aplicativos** .</span><span class="sxs-lookup"><span data-stu-id="009d6-149">In SharePoint Central Administration, click **Manage Service Applications** in the **Application Management** group.</span></span>  
  
2.  <span data-ttu-id="009d6-150">Clique no nome do aplicativo de serviço e, em seguida, clique em **Propriedades** na faixa de opções do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="009d6-150">Click the name of your service application and then click **Properties** in the SharePoint Ribbon.</span></span>  
  
3.  <span data-ttu-id="009d6-151">Leia a seção **Banco de Dados do Serviço SQL Server Reporting Services** .</span><span class="sxs-lookup"><span data-stu-id="009d6-151">Review the **Reporting Services (SSRS) Service Database** section.</span></span>  
  
4.  <span data-ttu-id="009d6-152">Se a Autenticação do Windows estiver configurada, você precisará saber as credenciais para que possa configurar o aplicativo de serviço após sua restauração.</span><span class="sxs-lookup"><span data-stu-id="009d6-152">If Windows Authentication is configured, you need to know the credentials so you can configure the service application after you restore it.</span></span> <span data-ttu-id="009d6-153">Não continue com o procedimento de backup e restauração até que saiba as credenciais corretas.</span><span class="sxs-lookup"><span data-stu-id="009d6-153">Do not proceed with the backup and restore procedure until you know the correct credentials.</span></span>  
  
##  <a name="restore-the-service-application"></a><a name="bkmk_restore"></a><span data-ttu-id="009d6-154">Restaurar o aplicativo de serviço</span><span class="sxs-lookup"><span data-stu-id="009d6-154">Restore the Service Application</span></span>  
 <span data-ttu-id="009d6-155">Conclua as seguintes etapas nesta ordem:</span><span class="sxs-lookup"><span data-stu-id="009d6-155">Complete the following steps in order:</span></span>  
  
1.  <span data-ttu-id="009d6-156">Restaurar o aplicativo de serviço [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="009d6-156">Restore the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>  
  
2.  <span data-ttu-id="009d6-157">Restaurar as chaves de criptografia</span><span class="sxs-lookup"><span data-stu-id="009d6-157">Restore the encryption keys</span></span>  
  
3.  <span data-ttu-id="009d6-158">Se seu aplicativo de serviço estava usando uma conta de execução ou uma autenticação do Windows para acesso ao banco de dados, configure as credenciais.</span><span class="sxs-lookup"><span data-stu-id="009d6-158">If your service application was using an execution account or Windows authentication for database access, configure the credentials.</span></span>  
  
### <a name="restore-the-service-application-using-sharepoint-central-administration"></a><span data-ttu-id="009d6-159">Restaurar o aplicativo de serviço usando a Administração Central do SharePoint</span><span class="sxs-lookup"><span data-stu-id="009d6-159">Restore the Service application Using SharePoint Central Administration</span></span>  
  
1.  <span data-ttu-id="009d6-160">Na Administração Central do SharePoint, clique em **Restaurar de um backup** no grupo **Backup e Restauração** .</span><span class="sxs-lookup"><span data-stu-id="009d6-160">In SharePoint Central Administration Click **Restore from a backup** in the **Backup and Restore** group.</span></span>  
  
2.  <span data-ttu-id="009d6-161">Digite o caminho para o arquivo de backup na caixa **Local do Diretório de Backup** e clique em **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="009d6-161">Type the path to your backup file in **Backup Directory Location** box and click **Refresh**.</span></span>  
  
3.  <span data-ttu-id="009d6-162">Selecione o backup de aplicativo de serviço na lista **Componente Superior** e clique **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="009d6-162">Select your service application backup from the **Top Component** list and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="009d6-163">Selecione o aplicativo [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="009d6-163">Select your [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] application and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="009d6-164">Na seção **Nomes e Senhas de Logon** , digite a senha para o nome de logon.</span><span class="sxs-lookup"><span data-stu-id="009d6-164">In the **Login Names and Passwords** section type the password for the login name.</span></span> <span data-ttu-id="009d6-165">A caixa de nome de logon deve ser preenchida com o logon que o aplicativo de serviço estava usando antes do backup.</span><span class="sxs-lookup"><span data-stu-id="009d6-165">The login name box should be populated with the login the service application was using prior to the backup.</span></span>  
  
6.  <span data-ttu-id="009d6-166">Clique em **Iniciar Restauração**.</span><span class="sxs-lookup"><span data-stu-id="009d6-166">Click **Start Restore**.</span></span>  
  
7.  <span data-ttu-id="009d6-167">Repita o processo acima, mas em vez de restaurar o aplicativo de serviço, expanda o nó **Serviços Compartilhados** e selecione o nó **Aplicativos de Serviços Compartilhados** .</span><span class="sxs-lookup"><span data-stu-id="009d6-167">Repeat the process above but instead of restoring the service application, expand the **Shared Services** node and then expand the **Shared Service Applications** node.</span></span>  
  
 <span data-ttu-id="009d6-168">Para obter mais informações, consulte os seguintes tópicos na documentação do SharePoint:</span><span class="sxs-lookup"><span data-stu-id="009d6-168">For more information, see the following topics in the SharePoint documentation:</span></span>  
  
 <span data-ttu-id="009d6-169">[Restauração de um aplicativo de serviço (SharePoint Foundation 2010)](https://msdn.microsoft.com/library/ee748615.aspx).</span><span class="sxs-lookup"><span data-stu-id="009d6-169">[Restore a service application (SharePoint Foundation 2010)](https://msdn.microsoft.com/library/ee748615.aspx).</span></span>  
  
 <span data-ttu-id="009d6-170">[Restauração de um aplicativo de serviço (SharePoint Server 2010)](https://technet.microsoft.com/library/ee428305.aspx).</span><span class="sxs-lookup"><span data-stu-id="009d6-170">[Restore a service application (SharePoint Server 2010)](https://technet.microsoft.com/library/ee428305.aspx).</span></span>  
  
### <a name="restore-the-encryption-keys-using-central-administration"></a><span data-ttu-id="009d6-171">Restauração das chaves de criptografia usando a Administração Central</span><span class="sxs-lookup"><span data-stu-id="009d6-171">Restore the Encryption Keys using Central Administration</span></span>  
 <span data-ttu-id="009d6-172">Para obter informações sobre como restaurar as [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] chaves de criptografia, consulte a seção "chaves de criptografia" de [gerenciar um Reporting Services aplicativo de serviço do SharePoint](../../2014/reporting-services/manage-a-reporting-services-sharepoint-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="009d6-172">For information on restoring the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] encryption keys, see the "Encryption Keys" section of [Manage a Reporting Services SharePoint Service Application](../../2014/reporting-services/manage-a-reporting-services-sharepoint-service-application.md).</span></span>  
  
### <a name="configure-the-execution-account-and-database-authentication"></a><span data-ttu-id="009d6-173">Configurar a conta de execução e a autenticação do banco de dados</span><span class="sxs-lookup"><span data-stu-id="009d6-173">Configure the Execution Account and Database Authentication</span></span>  
 <span data-ttu-id="009d6-174">**Conta de execução:** Se seu aplicativo de serviço estiver usando uma conta de execução, execute as seguintes etapas para configurá-lo:</span><span class="sxs-lookup"><span data-stu-id="009d6-174">**Execution Account:** If your service application was using an execution account complete the following steps to configure it:</span></span>  
  
1.  <span data-ttu-id="009d6-175">Na administração central do SharePoint, clique em **gerenciar aplicativos de serviço** no grupo **Gerenciamento de aplicativos** .</span><span class="sxs-lookup"><span data-stu-id="009d6-175">In SharePoint Central Administration, click **Manage Service Applications** in the **Application Management** group.</span></span>  
  
2.  <span data-ttu-id="009d6-176">Clique no nome do aplicativo de serviço e, em seguida, clique em **gerenciar** na faixa de das faixas do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="009d6-176">Click the name of your service application and then click **Manage** in the SharePoint Ribbon.</span></span>  
  
3.  <span data-ttu-id="009d6-177">Clique em **Conta de Execução**.</span><span class="sxs-lookup"><span data-stu-id="009d6-177">Click **Execution Account**.</span></span>  
  
4.  <span data-ttu-id="009d6-178">Digite a conta e a senha, e selecione a caixa **Especificar uma Conta de Execução** .</span><span class="sxs-lookup"><span data-stu-id="009d6-178">Type the account, password, and select the **Specify and Execution Account** box.</span></span>  
  
5.  <span data-ttu-id="009d6-179">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="009d6-179">Click **OK**.</span></span>  
  
 <span data-ttu-id="009d6-180">**Autenticação de Banco de Dados:** Se o aplicativo de serviço estiver usando a Autenticação do Windows na autenticação do banco de dados, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="009d6-180">**Database Authentication:** If your service application was using Windows Authentication for the database authentication complete the following steps:</span></span>  
  
1.  <span data-ttu-id="009d6-181">Na administração central do SharePoint, clique em **gerenciar aplicativos de serviço** no grupo **Gerenciamento de aplicativos** .</span><span class="sxs-lookup"><span data-stu-id="009d6-181">In SharePoint Central Administration click **Manage Service Applications** in the **Application Management** group.</span></span>  
  
2.  <span data-ttu-id="009d6-182">Clique no nome do aplicativo de serviço e, em seguida, clique em **Propriedades** na faixa de opções do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="009d6-182">Click the name of your service application and then click **Properties** in the SharePoint Ribbon.</span></span>  
  
3.  <span data-ttu-id="009d6-183">Leia a seção **Banco de Dados do Serviço SQL Server Reporting Services** .</span><span class="sxs-lookup"><span data-stu-id="009d6-183">Review the **Reporting Services (SSRS) Service Database** section.</span></span>  
  
4.  <span data-ttu-id="009d6-184">Selecione **Autenticação do Windows**.</span><span class="sxs-lookup"><span data-stu-id="009d6-184">Select **Windows Authentication**.</span></span>  
  
5.  <span data-ttu-id="009d6-185">Digite a conta e senha.</span><span class="sxs-lookup"><span data-stu-id="009d6-185">Type the account and password.</span></span> <span data-ttu-id="009d6-186">Selecione **Uso como Credenciais do Windows** , se apropriado.</span><span class="sxs-lookup"><span data-stu-id="009d6-186">Select **Use as Windows Credentials** if appropriate.</span></span>  
  
6.  <span data-ttu-id="009d6-187">Clique em **Ok**</span><span class="sxs-lookup"><span data-stu-id="009d6-187">Click **Ok**</span></span>  
  
  
