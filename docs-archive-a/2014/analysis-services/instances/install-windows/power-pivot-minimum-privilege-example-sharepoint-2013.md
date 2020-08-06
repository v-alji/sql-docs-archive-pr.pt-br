---
title: Exemplo de uma configuração de privilégio mínimo para o PowerPivot para SharePoint 2013 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c1e09e6c-52d3-48ab-8c70-818d5d775087
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0188f314e4c354b33d03e6e7948aed1ba4cf8be2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679574"
---
# <a name="example-of-a-minimum-privilege-configuration-for-powerpivot-for-sharepoint-2013"></a><span data-ttu-id="cf4f3-102">Exemplo de uma configuração de privilégios mínimos para o PowerPivot para SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="cf4f3-102">Example of a Minimum-Privilege Configuration for PowerPivot for SharePoint 2013</span></span>
  <span data-ttu-id="cf4f3-103">Este tópico descreve um exemplo da configuração do PowerPivot para SharePoint 2013 com privilégios mínimos.</span><span class="sxs-lookup"><span data-stu-id="cf4f3-103">This topic describes an example PowerPivot for SharePoint 2013 configuration with minimum privileges.</span></span> <span data-ttu-id="cf4f3-104">A configuração utiliza uma conta diferente para cada um dos três componentes e cada conta tem o nível mínimo de privilégios.</span><span class="sxs-lookup"><span data-stu-id="cf4f3-104">The configuration utilizes a different account for each of the three components and each account has the minimum level of privileges.</span></span>  
  
## <a name="summary-of-accounts"></a><span data-ttu-id="cf4f3-105">Resumo de contas</span><span class="sxs-lookup"><span data-stu-id="cf4f3-105">Summary of Accounts</span></span>  
 <span data-ttu-id="cf4f3-106">O PowerPivot para SharePoint 2013 dá suporte ao uso da conta de serviço de rede para a conta de serviço do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="cf4f3-106">PowerPivot for SharePoint 2013 supports the use of the Network Service account for the Analysis Services service account.</span></span> <span data-ttu-id="cf4f3-107">A conta de serviço de rede não é um cenário com suporte com o SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="cf4f3-107">The Network Service account is not a supported scenario with SharePoint 2010.</span></span> <span data-ttu-id="cf4f3-108">Para obter mais informações sobre contas de serviço, consulte [Configurar contas de serviço e permissões do Windows](../../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md) ( https://msdn.microsoft.com/library/ms143504.aspx) .</span><span class="sxs-lookup"><span data-stu-id="cf4f3-108">For more information on Service accounts, see [Configure Windows Service Accounts and Permissions](../../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md) (https://msdn.microsoft.com/library/ms143504.aspx).</span></span>  
  
 <span data-ttu-id="cf4f3-109">A tabela a seguir resume as três contas usadas neste exemplo de uma configuração com privilégios mínimos.</span><span class="sxs-lookup"><span data-stu-id="cf4f3-109">The following table summarizes the three accounts used in this example of a minimum privileged configuration.</span></span>  
  
|<span data-ttu-id="cf4f3-110">Escopo</span><span class="sxs-lookup"><span data-stu-id="cf4f3-110">Scope</span></span>|<span data-ttu-id="cf4f3-111">Nome</span><span class="sxs-lookup"><span data-stu-id="cf4f3-111">Name</span></span>|  
|-----------|----------|  
|<span data-ttu-id="cf4f3-112">Conta do administrador do SharePoint</span><span class="sxs-lookup"><span data-stu-id="cf4f3-112">SharePoint Administrator account</span></span>|<span data-ttu-id="cf4f3-113">**SPAdmin**</span><span class="sxs-lookup"><span data-stu-id="cf4f3-113">**SPAdmin**</span></span>|  
|<span data-ttu-id="cf4f3-114">Conta do farm do SharePoint</span><span class="sxs-lookup"><span data-stu-id="cf4f3-114">SharePoint Farm account</span></span>|<span data-ttu-id="cf4f3-115">**SPFarm**</span><span class="sxs-lookup"><span data-stu-id="cf4f3-115">**SPFarm**</span></span>|  
|<span data-ttu-id="cf4f3-116">Conta de serviço do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="cf4f3-116">Analysis Services service account</span></span>|<span data-ttu-id="cf4f3-117">**SPsvc**</span><span class="sxs-lookup"><span data-stu-id="cf4f3-117">**SPsvc**</span></span>|  
  
### <a name="the-sharepoint-administrator-account-spadmin"></a><span data-ttu-id="cf4f3-118">A conta do administrador do SharePoint (SpAdmin)</span><span class="sxs-lookup"><span data-stu-id="cf4f3-118">The SharePoint Administrator account (SpAdmin)</span></span>  
 <span data-ttu-id="cf4f3-119">**SPAdmin** é uma conta de domínio usada para instalar e configurar o farm.</span><span class="sxs-lookup"><span data-stu-id="cf4f3-119">**SPAdmin** is a domain account you use to install and configure the farm.</span></span> <span data-ttu-id="cf4f3-120">É a conta usada para executar o assistente de configuração do SharePoint e a ferramenta de configuração do PowerPivot para SharePoint 2013. a conta de **administrador** é a única conta que exige direitos de administrador local.</span><span class="sxs-lookup"><span data-stu-id="cf4f3-120">It is the account used to run the SharePoint Configuration Wizard and the PowerPivot Configuration Tool for SharePoint 2013.The **SPAdmin** account is the only account that requires local Administrator rights.</span></span> <span data-ttu-id="cf4f3-121">Antes de executar a ferramenta de configuração do PowerPivot, conceda os privilégios da conta de **administrador** para a instância de banco de dados SQL Server, em que o SharePoint cria o conteúdo e banco de dados de configuração.</span><span class="sxs-lookup"><span data-stu-id="cf4f3-121">Before running the PowerPivot Configuration tool, grant the **SPAdmin** account privileges to the SQL Server database instance where SharePoint creates content and configuration databases.</span></span> <span data-ttu-id="cf4f3-122">Para configurar a conta SPAdmin em um cenário de privilégios mínimos, ela deve ser um membro das funções **securityadmin** e **dbcreator**.</span><span class="sxs-lookup"><span data-stu-id="cf4f3-122">To configure the SPAdmin account in a minimum privilege scenario, it should be a member of the roles **securityadmin** and **dbcreator**.</span></span>  
  
### <a name="the-farm-account-spfarm"></a><span data-ttu-id="cf4f3-123">A conta do farm (SPFarm)</span><span class="sxs-lookup"><span data-stu-id="cf4f3-123">The Farm account (SPFarm)</span></span>  
 <span data-ttu-id="cf4f3-124">**SPFarm** é uma conta de domínio que o serviço de timer do SharePoint e o aplicativo Web para a Administração Central usam para acessar o banco de dados de conteúdo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cf4f3-124">**SPFarm** is a domain account that the SharePoint Timer service and the web application for Central Administration use to access the SharePoint content database.</span></span> <span data-ttu-id="cf4f3-125">Esta conta não precisa ser um administrador local.</span><span class="sxs-lookup"><span data-stu-id="cf4f3-125">This account does not need to be a local administrator.</span></span> <span data-ttu-id="cf4f3-126">O assistente de configuração do SharePoint concede o privilégio mínimo apropriado no banco de dados do SQL Server de back-end. A configuração de privilégios mínimos do SQL Server é a associação nas funções **securityadmin** e **dbcreator**.</span><span class="sxs-lookup"><span data-stu-id="cf4f3-126">The SharePoint configuration wizard grants the proper minimal privilege in the back-end SQL Server database.The minimum SQL Server privilege configuration is membership in the roles **securityadmin** and **dbcreator**.</span></span>  
  
### <a name="the-service-account-for-powerpivot-service-spsvc"></a><span data-ttu-id="cf4f3-127">A conta de serviço para o serviço PowerPivot (SPsvc)</span><span class="sxs-lookup"><span data-stu-id="cf4f3-127">The Service Account for PowerPivot Service (SPsvc)</span></span>  
 <span data-ttu-id="cf4f3-128">Se um novo farm do SharePoint não estiver configurado antes de você executar a ferramenta de configuração do PowerPivot, por padrão a ferramenta configuração do PowerPivot criará o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cf4f3-128">If a new SharePoint farm is not configured before you run the PowerPivot Configuration tool, then by default the PowerPivot Configuration tool will create the following:</span></span>  
  
-   <span data-ttu-id="cf4f3-129">Aplicativo de serviço PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="cf4f3-129">PowerPivot Service application.</span></span>  
  
-   <span data-ttu-id="cf4f3-130">Aplicativo de Serviços do Excel.</span><span class="sxs-lookup"><span data-stu-id="cf4f3-130">Excel Services application.</span></span>  
  
-   <span data-ttu-id="cf4f3-131">Aplicativo de Repositório Seguro.</span><span class="sxs-lookup"><span data-stu-id="cf4f3-131">Secure Store application.</span></span>  
  
 <span data-ttu-id="cf4f3-132">A ferramenta de configuração do PowerPivot configura todos os três aplicativos de serviço no pool de aplicativos padrão.</span><span class="sxs-lookup"><span data-stu-id="cf4f3-132">The PowerPivot configuration tool configures all three of the service applications in the default application pool.</span></span> <span data-ttu-id="cf4f3-133">Esse pool de aplicativos normalmente é configurado para ser executado como a conta SPFarm, que tem acesso a vários recursos que uma conta de serviço não necessita. Para tornar o ambiente um ambiente de privilégios mínimos, configure uma nova conta de domínio para ser usada pelo pool de aplicativos e aplicativo Web apropriados.</span><span class="sxs-lookup"><span data-stu-id="cf4f3-133">That application pool is typically configured to run as the SPFarm account, which has access to many resources that a service account does not require.To make the environment a minimum-privileged environment, configure a new domain account to be use by the appropriate application pool and web application.</span></span>  
  
 <span data-ttu-id="cf4f3-134">**Para criar uma nova conta de domínio SPsvc para ser usada como uma conta de serviço do SharePoint:**</span><span class="sxs-lookup"><span data-stu-id="cf4f3-134">**To create a new domain account SPsvc to be used as a SharePoint Service account:**</span></span>  
  
1.  <span data-ttu-id="cf4f3-135">Na administração central do SharePoint, clique em **segurança**.</span><span class="sxs-lookup"><span data-stu-id="cf4f3-135">In SharePoint Central Administration, click **Security**.</span></span>  
  
2.  <span data-ttu-id="cf4f3-136">Clique em **Configurar contas de serviço**</span><span class="sxs-lookup"><span data-stu-id="cf4f3-136">Click **Configure Service Accounts**</span></span>  
  
3.  <span data-ttu-id="cf4f3-137">Clique em **registrar nova conta gerenciada**.</span><span class="sxs-lookup"><span data-stu-id="cf4f3-137">Click **Register new managed account**.</span></span>  
  
 <span data-ttu-id="cf4f3-138">A conta **SPSvc** não tem privilégios de administrador local e SPsvc não terá nenhum privilégio no banco de dados do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cf4f3-138">The **SPSvc** account has no local administrator privileges and SPsvc will not have any privileges in the SharePoint database.</span></span> <span data-ttu-id="cf4f3-139">Os únicos privilégios que o SPsvc exige são direitos administrativos à instância do PowerPivot do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="cf4f3-139">The only privileges SPsvc requires is administrative rights to the PowerPivot Instance of the Analysis Services.</span></span>  
  
 <span data-ttu-id="cf4f3-140">**Para configurar o pool de aplicativos apropriado para usar a conta SPsvc:**</span><span class="sxs-lookup"><span data-stu-id="cf4f3-140">**To configure the appropriate application pool to use the SPsvc account :**</span></span>  
  
1.  <span data-ttu-id="cf4f3-141">Na administração central do SharePoint, clique em **segurança**.</span><span class="sxs-lookup"><span data-stu-id="cf4f3-141">In SharePoint Central Administration, click **Security**.</span></span>  
  
2.  <span data-ttu-id="cf4f3-142">Clique em **Configurar contas de serviço**.</span><span class="sxs-lookup"><span data-stu-id="cf4f3-142">Click **Configure Service Accounts**.</span></span>  
  
3.  <span data-ttu-id="cf4f3-143">Selecione o pool de aplicativo de serviço usado pelo aplicativo de serviço PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="cf4f3-143">Select the service application pool used by the PowerPivot Service application.</span></span> <span data-ttu-id="cf4f3-144">Selecione a conta SPSvc.</span><span class="sxs-lookup"><span data-stu-id="cf4f3-144">Then select the SPSvc account.</span></span>  
  
 <span data-ttu-id="cf4f3-145">**Para conceder acesso ao aplicativo Web com o PowerShell:**</span><span class="sxs-lookup"><span data-stu-id="cf4f3-145">**To Grant access to the web application with PowerShell:**</span></span>  
  
1.  <span data-ttu-id="cf4f3-146">Execute o Shell de Gerenciamento do SharePoint 2013 com privilégios de administrador.</span><span class="sxs-lookup"><span data-stu-id="cf4f3-146">Run the SharePoint 2013 Management Shell with administrator privileges.</span></span>  
  
2.  <span data-ttu-id="cf4f3-147">Execute o seguinte código do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="cf4f3-147">Run the following PowerShell code:</span></span>  
  
    ```powershell
    $webApp = Get-SPWebApplication "http://<servername>"  
    $webApp.GrantAccessToProcessIdentity("DOMAIN\<ServiceAccountName>")
    ```  
