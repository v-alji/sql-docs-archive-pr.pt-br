---
title: Provisionar assinaturas e alertas para aplicativos de serviço do SSRS | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services Shared Service
- SharePoint Mode [Reporting Services]
- SharePoint Mode
- Reporting Services Service Application
- SSRS service application
ms.assetid: d0de3f1f-4887-47fb-bacf-46aaad74c4be
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9c09033b6a31295b8fbe42058cba9059f5d05629
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686116"
---
# <a name="provision-subscriptions-and-alerts-for-ssrs-service-applications"></a><span data-ttu-id="dc714-102">Provisionar Assinaturas e Alertas para aplicativos de serviço SSRS</span><span class="sxs-lookup"><span data-stu-id="dc714-102">Provision Subscriptions and Alerts for SSRS Service Applications</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="dc714-103">as assinaturas e os alertas de dados exigem o SQL Server Agent e a configuração de permissões para o SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="dc714-103">subscriptions and data alerts require SQL Server Agent and require the configuration of permissions for SQL Server Agent.</span></span> <span data-ttu-id="dc714-104">Se você visualizar mensagens de erro que indicam que um SQL Server Agent é necessário e tiver verificado que o SQL Server Agent está em execução; em seguida, atualize ou verifique as permissões.</span><span class="sxs-lookup"><span data-stu-id="dc714-104">If you see error messages that indicate SQL Server Agent is required and you have verified SQL Server Agent is running, then update or verify permissions.</span></span> <span data-ttu-id="dc714-105">O escopo deste tópico é [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] no modo do SharePoint e o tópico descreve três maneiras de atualizar as permissões do SQL Server Agent com assinaturas do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dc714-105">The scope of this topic is [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in SharePoint mode and the topic describes three ways you can update the permissions of SQL Server Agent with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] subscriptions.</span></span> <span data-ttu-id="dc714-106">As credenciais que você usa para as etapas neste tópico precisam ter permissões suficientes para conceder permissões execute a RSExecRole para objetos nos bancos de dados de aplicativos de serviço, msdb e mestre.</span><span class="sxs-lookup"><span data-stu-id="dc714-106">The credentials you use for the steps in this topic need to have sufficient permissions to grant execute permissions to the RSExecRole for objects in the service application, msdb, and master databases.</span></span>

||
|-|
|<span data-ttu-id="dc714-107">**[!INCLUDE[applies](../../includes/applies-md.md)]** SharePoint 2013 &#124; SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="dc714-107">**[!INCLUDE[applies](../../includes/applies-md.md)]**  SharePoint 2013 &#124; SharePoint 2010</span></span>|

 <span data-ttu-id="dc714-108">![Permissões do SQL Agent para bancos de dados de aplicativo de serviço](../../../2014/sql-server/install/media/rs-provisionsqlagent.gif "Permissões do SQL Agent para bancos de dados de aplicativo de serviço")</span><span class="sxs-lookup"><span data-stu-id="dc714-108">![SQL Agent permissions to Service Application DBs](../../../2014/sql-server/install/media/rs-provisionsqlagent.gif "SQL Agent permissions to Service Application DBs")</span></span>

||<span data-ttu-id="dc714-109">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="dc714-109">Description</span></span>|
|------|-----------------|
|<span data-ttu-id="dc714-110">**1**</span><span class="sxs-lookup"><span data-stu-id="dc714-110">**1**</span></span>|<span data-ttu-id="dc714-111">A instância do mecanismo de banco de dados do SQL Server que está hospedando os bancos de dados do aplicativo do serviço Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="dc714-111">The instance of SQL Server Database engine that is hosting the Reporting Services service application databases.</span></span>|
|<span data-ttu-id="dc714-112">**2**</span><span class="sxs-lookup"><span data-stu-id="dc714-112">**2**</span></span>|<span data-ttu-id="dc714-113">A instância do SQL Server Agent para a instância do mecanismo de banco de dados SQL.</span><span class="sxs-lookup"><span data-stu-id="dc714-113">The instance of SQL Server agent for the instance of the SQL database engine.</span></span>|
|<span data-ttu-id="dc714-114">**3**</span><span class="sxs-lookup"><span data-stu-id="dc714-114">**3**</span></span>|<span data-ttu-id="dc714-115">Os bancos de dados do aplicativo do serviço Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="dc714-115">The Reporting Services service application databases.</span></span> <span data-ttu-id="dc714-116">Os nomes são baseados nas informações usadas para criar o aplicativo de serviço.</span><span class="sxs-lookup"><span data-stu-id="dc714-116">The names are based on the information used for creating the service application.</span></span> <span data-ttu-id="dc714-117">Veja a seguir nomes de bancos de dados de exemplo:</span><span class="sxs-lookup"><span data-stu-id="dc714-117">The following are example database names:</span></span><br /><br /> <span data-ttu-id="dc714-118">ReportingService_2fbae157295d49df86d0b85760c704b0</span><span class="sxs-lookup"><span data-stu-id="dc714-118">ReportingService_2fbae157295d49df86d0b85760c704b0</span></span><br /><br /> <span data-ttu-id="dc714-119">ReportingService_2fbae157295d49df86d0b85760c704b0_Alerting</span><span class="sxs-lookup"><span data-stu-id="dc714-119">ReportingService_2fbae157295d49df86d0b85760c704b0_Alerting</span></span><br /><br /> <span data-ttu-id="dc714-120">ReportingService_2fbae157295d49df86d0b85760c704b0TempDB</span><span class="sxs-lookup"><span data-stu-id="dc714-120">ReportingService_2fbae157295d49df86d0b85760c704b0TempDB</span></span>|
|<span data-ttu-id="dc714-121">**4**</span><span class="sxs-lookup"><span data-stu-id="dc714-121">**4**</span></span>|<span data-ttu-id="dc714-122">O banco de dados mestre e MSDB da instância do mecanismo de Banco de Dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dc714-122">The master and MSDB database of the instance of the SQL Server Database engine.</span></span>|

 <span data-ttu-id="dc714-123">Use um dos três métodos a seguir para atualizar as permissões:</span><span class="sxs-lookup"><span data-stu-id="dc714-123">Use one the following three methods to update the permissions:</span></span>

1.  <span data-ttu-id="dc714-124">Na página **Provisionar Assinaturas e Alertas** , digite as credenciais e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc714-124">From the **Provisions and Subscriptions and Alerts** page, type credentials and click **ok**.</span></span>

2.  <span data-ttu-id="dc714-125">Na página Provisionar Assinaturas e Alertas, clique no botão **Baixar Script** para baixar um script Transact-SQL que possa ser usado para configurar permissões.</span><span class="sxs-lookup"><span data-stu-id="dc714-125">From the Provisions and Subscriptions and Alerts page, click the **Download Script** button to download a transact SQL script that can be used to configure permissions.</span></span>

3.  <span data-ttu-id="dc714-126">Execute um cmdlet do PowerShell para criar um script transact SQL que pode ser usado para configurar permissões.</span><span class="sxs-lookup"><span data-stu-id="dc714-126">Run a PowerShell cmdlet to build a transact SQL script that can be used to configure permissions.</span></span>

### <a name="to-update-permissions-using-the-provision-page"></a><span data-ttu-id="dc714-127">Para atualizar permissões usando a página de provisão</span><span class="sxs-lookup"><span data-stu-id="dc714-127">To update permissions using the provision page</span></span>

1.  <span data-ttu-id="dc714-128">Na Administração Central do SharePoint, no grupo **Gerenciamento de Aplicativo** , clique em **Gerenciar Aplicativos de Serviço**</span><span class="sxs-lookup"><span data-stu-id="dc714-128">From SharePoint Central Administration, in the **Application Management** group click **Manage Service Applications**</span></span>

2.  <span data-ttu-id="dc714-129">Encontre seu aplicativo de serviço na lista e clique no nome do aplicativo ou clique na coluna **Type** para selecionar o aplicativo de serviços e clique no botão **Gerenciar** na faixa de opções do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="dc714-129">Find your service application in the list and click the name of the application or click the **Type** column to select the services application and click the **Manage** button in the SharePoint ribbon.</span></span>

3.  <span data-ttu-id="dc714-130">Na página **Gerenciar Aplicativo Reporting Services** , clique em **Provisionar Assinaturas e Alertas**.</span><span class="sxs-lookup"><span data-stu-id="dc714-130">On the **Manage Reporting Services Application** page, click **Provision Subscriptions and Alerts**.</span></span>

4.  <span data-ttu-id="dc714-131">Se o administrador do SharePoint tiver privilégios suficientes ao banco de dados Mestre e aos bancos de dados de aplicativo de serviço, digite as credenciais.</span><span class="sxs-lookup"><span data-stu-id="dc714-131">If the SharePoint administrator has enough privileges to the Master database and the service application databases, type those credentials.</span></span>

5.  <span data-ttu-id="dc714-132">Clique no botão **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc714-132">Click the **OK** button.</span></span>

##  <a name="to-download-the-transact-sql-script"></a><a name="bkmk_download"></a> <span data-ttu-id="dc714-133">Para baixar o script Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dc714-133">To download the Transact-SQL Script</span></span>

1.  <span data-ttu-id="dc714-134">Na Administração Central do SharePoint, no grupo **Gerenciamento de Aplicativo** , clique em **Gerenciar Aplicativos de Serviço**</span><span class="sxs-lookup"><span data-stu-id="dc714-134">From SharePoint Central Administration, in the **Application Management** group click **Manage Service Applications**</span></span>

2.  <span data-ttu-id="dc714-135">Encontre seu aplicativo de serviço na lista e clique no nome do aplicativo ou clique na coluna **Type** para selecionar o aplicativo de serviços e clique no botão **Gerenciar** na faixa de opções do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="dc714-135">Find your service application in the list and click the name of the application or click the **Type** column to select the services application and click the **Manage** button in the SharePoint ribbon.</span></span>

3.  <span data-ttu-id="dc714-136">Na página **Gerenciar Aplicativo Reporting Services** , clique em **Provisionar Assinaturas e Alertas**.</span><span class="sxs-lookup"><span data-stu-id="dc714-136">On the **Manage Reporting Services Application** page, click **Provision Subscriptions and Alerts**.</span></span>

4.  <span data-ttu-id="dc714-137">Na área **Exibir Status** , verifique se o SQL Server Agent está em execução.</span><span class="sxs-lookup"><span data-stu-id="dc714-137">In the **View Status** area, verify SQL Server Agent is running.</span></span>

5.  <span data-ttu-id="dc714-138">Clique em **Baixar Script** para baixar um script Transact-SQL que você pode executar no SQL Server Management Studio para conceder permissões.</span><span class="sxs-lookup"><span data-stu-id="dc714-138">Click **Download Script** to download a transact SQL script you can run in SQL Server Management studio to grant permissions.</span></span> <span data-ttu-id="dc714-139">O nome do arquivo de script que é criado conterá o nome de seu aplicativo de serviço do Reporting Services, por exemplo **[nome do aplicativo de serviço]-GrantRights.sql**.</span><span class="sxs-lookup"><span data-stu-id="dc714-139">The script file name that is created will contain the name of your Reporting Services service application name, for example **[name of the service application]-GrantRights.sql**.</span></span>

### <a name="to-generate-the-transact-sql-statement-with-powershell"></a><span data-ttu-id="dc714-140">Para gerar a instrução Transact-SQL com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="dc714-140">To generate the Transact-SQL statement with PowerShell</span></span>

1.  <span data-ttu-id="dc714-141">Você também pode usar um cmdlet do Windows PowerShell no Shell de Gerenciamento do SharePoint 2010 para criar o script Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="dc714-141">You can also use a Windows PowerShell cmdlet in the SharePoint 2010 Management Shell to create the Transact-SQL script.</span></span>

2.  <span data-ttu-id="dc714-142">No menu **Iniciar** , clique em **Todos os Programas**.</span><span class="sxs-lookup"><span data-stu-id="dc714-142">On the **Start** menu, click **All Programs**.</span></span>

3.  <span data-ttu-id="dc714-143">Expanda **produtos do Microsoft SharePoint 2010** e clique em **Shell de gerenciamento do SharePoint 2010**.</span><span class="sxs-lookup"><span data-stu-id="dc714-143">Expand **Microsoft SharePoint 2010 Products** and click **SharePoint 2010 Management Shell**.</span></span>

4.  <span data-ttu-id="dc714-144">Atualize o seguinte cmdlet do PowerShell substituindo o nome do banco de dados do servidor de relatório, a conta do pool de aplicativos e o caminho da instrução.</span><span class="sxs-lookup"><span data-stu-id="dc714-144">Update the following PowerShell cmdlet by replacing the name of the report server database, application pool account, and the path of the statement.</span></span>

     <span data-ttu-id="dc714-145">**Sintaxe do cmdlet:** `Get-SPRSDatabaseRightsScript -DatabaseName <ReportingServices database name> -UserName <app pool account> -IsWindowsUser | Out-File <path of statement>`</span><span class="sxs-lookup"><span data-stu-id="dc714-145">**Syntax of cmdlet:** `Get-SPRSDatabaseRightsScript -DatabaseName <ReportingServices database name> -UserName <app pool account> -IsWindowsUser | Out-File <path of statement>`</span></span>

     <span data-ttu-id="dc714-146">**Cmdlet de exemplo:** `Get-SPRSDatabaseRightsScript -DatabaseName ReportingService_46fd00359f894b828907b254e3f6257c -UserName "NT AUTHORITY\NETWORK SERVICE" -IsWindowsUser | Out-File c:\SQLServerAgentrights.sql`</span><span class="sxs-lookup"><span data-stu-id="dc714-146">**Sample cmdlet:** `Get-SPRSDatabaseRightsScript -DatabaseName ReportingService_46fd00359f894b828907b254e3f6257c -UserName "NT AUTHORITY\NETWORK SERVICE" -IsWindowsUser | Out-File c:\SQLServerAgentrights.sql`</span></span>

## <a name="using-the-transact-sql-script"></a><span data-ttu-id="dc714-147">Usando o script Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dc714-147">Using the Transact-SQL Script</span></span>
 <span data-ttu-id="dc714-148">Os seguintes procedimentos podem ser usados com o download de scripts da página de provisões ou scripts criados usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dc714-148">The following procedures can be used with scripts download from the provisions page or scripts created using PowerShell.</span></span>

#### <a name="to-load-the-transact-sql-script-in-sql-server-management-studio"></a><span data-ttu-id="dc714-149">Para carregar o script Transact-SQL no SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dc714-149">To load the Transact-SQL script in SQL Server Management Studio</span></span>

1.  <span data-ttu-id="dc714-150">Para abrir SQL Server Management Studio, no menu **Iniciar** , clique em **Microsoft SQL Server 2012** e clique em **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="dc714-150">To open SQL Server Management Studio, on the **Start** menu, click **Microsoft SQL Server 2012** and click **SQL Server Management Studio**.</span></span>

2.  <span data-ttu-id="dc714-151">Na caixa de diálogo **Conectar ao Servidor** , defina as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="dc714-151">In the **Connect to Server** dialog box set the following options:</span></span>

    -   <span data-ttu-id="dc714-152">Na lista **Tipo de servidor** , selecione **Mecanismo de Banco de Dados**</span><span class="sxs-lookup"><span data-stu-id="dc714-152">In the **Server type** list, select **Database Engine**</span></span>

    -   <span data-ttu-id="dc714-153">Na caixa **Nome do Servidor**, digite o nome da instância do SQL Server no qual você deseja configurar o SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="dc714-153">In **Server Name**, type the name of the SQL Server instance on which you want to configure SQL Server Agent.</span></span>

    -   <span data-ttu-id="dc714-154">Selecione um modo de autenticação.</span><span class="sxs-lookup"><span data-stu-id="dc714-154">Select an authentication mode.</span></span>

    -   <span data-ttu-id="dc714-155">Se estiver conectando usando a Autenticação do SQL Server, forneça um logon e uma senha.</span><span class="sxs-lookup"><span data-stu-id="dc714-155">If connecting using SQL Server Authentication, provide a login and password.</span></span>

3.  <span data-ttu-id="dc714-156">Clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="dc714-156">Click **Connect**.</span></span>

#### <a name="to-run-the-transact-sql-statement"></a><span data-ttu-id="dc714-157">Para executar a instrução Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dc714-157">To run the Transact-SQL statement</span></span>

1.  <span data-ttu-id="dc714-158">Na barra de ferramentas do SQL Server Management Studio, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="dc714-158">On the toolbar of SQL Server Management Studio, click **New Query**.</span></span>

2.  <span data-ttu-id="dc714-159">No menu **Arquivo** , clique em **Abrir**e em **Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="dc714-159">On the **File** menu, click **Open**, and then click **File**.</span></span>

3.  <span data-ttu-id="dc714-160">Navegue até a pasta em que você salvou a instrução Transact-SQL gerada no Shell de Gerenciamento do SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="dc714-160">Navigate to the folder where you saved the Transact-SQL statement that you generated in SharePoint 2010 Management Shell.</span></span>

4.  <span data-ttu-id="dc714-161">Clique no arquivo e em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="dc714-161">Click the file and then click **Open**.</span></span>

     <span data-ttu-id="dc714-162">A instrução é adicionada à janela de consulta.</span><span class="sxs-lookup"><span data-stu-id="dc714-162">The statement is added to the query window.</span></span>

5.  <span data-ttu-id="dc714-163">Clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="dc714-163">Click **Execute**.</span></span>


