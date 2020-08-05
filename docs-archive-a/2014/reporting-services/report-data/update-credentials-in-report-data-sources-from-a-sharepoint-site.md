---
title: Atualizar as credenciais em fontes de dados de relatório por meio de um site do SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e0c50b6e-89e7-4b4d-8fe5-c90682c5d1b1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 923fee5656ed6032201fb4276fcca75be799e42d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569113"
---
# <a name="update-credentials-in-report-data-sources-from-a-sharepoint-site"></a><span data-ttu-id="de300-102">Atualizar credenciais em fontes de dados de relatório de um site do SharePoint</span><span class="sxs-lookup"><span data-stu-id="de300-102">Update Credentials in Report Data Sources from a SharePoint Site</span></span>
  <span data-ttu-id="de300-103">Este tópico descreve como atualizar as fontes de dados incorporadas nos relatórios e nas fontes de dados compartilhadas salvas em uma biblioteca de documentos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="de300-103">This topic describes how to update data sources embedded in reports and shared data sources that are saved in a SharePoint document library.</span></span>  
  
 <span data-ttu-id="de300-104">Muitos de seus relatórios poderiam incluir fontes de dados ou usar fontes de dados compartilhadas configuradas para usar a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="de300-104">Many of your reports might include data sources or use shared data sources that are configured to use Windows Authentication.</span></span> <span data-ttu-id="de300-105">Em algumas circunstâncias, como a criação de alertas de dados em relatórios salvos em uma biblioteca de documentos do SharePoint, você precisa atualizar as credenciais de fonte de dados para credenciais armazenadas ou não requerer nenhuma credencial.</span><span class="sxs-lookup"><span data-stu-id="de300-105">Under some circumstances, such as creating data alerts on reports saved to a SharePoint document library, you need to update the data source credentials to stored credentials or require no credentials.</span></span>  
  
 <span data-ttu-id="de300-106">Para usar credenciais armazenadas em relatórios, você poderia optar por criar e usar um novo logon do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="de300-106">To use stored credentials in reports, you might decide to create and use a new SQL Server login.</span></span> <span data-ttu-id="de300-107">Para obter mais informações, consulte [Crie um logon](../../relational-databases/security/authentication-access/create-a-login.md).</span><span class="sxs-lookup"><span data-stu-id="de300-107">For more information, see [Create a Login](../../relational-databases/security/authentication-access/create-a-login.md).</span></span>  
  
### <a name="to-update-an-embedded-data-source-to-use-stored-credentials"></a><span data-ttu-id="de300-108">Para atualizar uma fonte de dados incorporada para usar credenciais armazenadas</span><span class="sxs-lookup"><span data-stu-id="de300-108">To update an embedded data source to use stored credentials</span></span>  
  
1.  <span data-ttu-id="de300-109">Vá para a biblioteca de documentos do SharePoint onde salvou o relatório.</span><span class="sxs-lookup"><span data-stu-id="de300-109">Go to the SharePoint document library where you saved the report.</span></span>  
  
2.  <span data-ttu-id="de300-110">Clique no ícone para expandir o menu suspenso no relatório e clique em **Gerenciar Fontes de Dados**.</span><span class="sxs-lookup"><span data-stu-id="de300-110">Click the icon for the expand drop-down menu on the report and then click **Manage Data Sources**.</span></span>  
  
     <span data-ttu-id="de300-111">A página Gerenciar Fontes de Dados será aberta.</span><span class="sxs-lookup"><span data-stu-id="de300-111">The Manage Data Sources page opens.</span></span>  
  
3.  <span data-ttu-id="de300-112">Na coluna **Nome** , clique na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="de300-112">In the **Name** column, click the data source.</span></span>  
  
4.  <span data-ttu-id="de300-113">Em **Tipo de Conexão** , verifique se a opção **Fonte de dados personalizada** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="de300-113">For **Connection Type** verify that the **Custom data source** option is selected.</span></span>  
  
     <span data-ttu-id="de300-114">Essa opção indica que a fonte de dados está incorporada no relatório.</span><span class="sxs-lookup"><span data-stu-id="de300-114">This option indicates that the data source is embedded in the report.</span></span>  
  
5.  <span data-ttu-id="de300-115">Deixe as opções **Tipo de Fonte de Dados** e **Cadeia de conexão** como estão, a menos que você deseje que o relatório se conecte a outro tipo de fonte de dados, a outro servidor ou a um armazenamento de dados.</span><span class="sxs-lookup"><span data-stu-id="de300-115">Leave the **Data Source Type** and **Connection string** options as they are, unless you want the report to connect to different type of data source, a different server, or data store.</span></span>  
  
6.  <span data-ttu-id="de300-116">Em **Credenciais**, selecione **Credenciais armazenadas**.</span><span class="sxs-lookup"><span data-stu-id="de300-116">For **Credentials**, select **Stored credentials**.</span></span> <span data-ttu-id="de300-117">Essa opção só funcionará se a fonte de dados não aceitar credenciais ou se você estiver passando as credenciais de alguma outra forma.</span><span class="sxs-lookup"><span data-stu-id="de300-117">This option works only if the data source does not accept credentials or if you are passing credentials some other way.</span></span>  
  
     <span data-ttu-id="de300-118">A opção **Não são necessárias credenciais** também pode ser usada em algumas circunstâncias.</span><span class="sxs-lookup"><span data-stu-id="de300-118">The **Credentials are not required** option can also be used under some circumstances.</span></span>  
  
     <span data-ttu-id="de300-119">Em alguns tipos de fonte de dados, a conta de execução autônoma deve estar configurada no servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="de300-119">From some data source types, the unattended execution account must be configured on the report server.</span></span> <span data-ttu-id="de300-120">Para obter mais informações, consulte o tópico do tipo de fonte de dados correspondente em [Adicionar dados de fontes de dados externas &#40;SSRS&#41;](add-data-from-external-data-sources-ssrs.md) e [Configurar a conta de execução autônoma &#40;Gerenciador de Configurações do SSRS&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="de300-120">For more information, see the topic for the corresponding data source type in [Add Data from External Data Sources &#40;SSRS&#41;](add-data-from-external-data-sources-ssrs.md) and [Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span></span>  
  
7.  <span data-ttu-id="de300-121">Digite um nome de usuário e uma senha.</span><span class="sxs-lookup"><span data-stu-id="de300-121">Type a user name and password.</span></span>  
  
    -   <span data-ttu-id="de300-122">Se a conta for uma conta de usuário de domínio do Windows, especifique-a neste formato: \<domain> \\<conta \> e, em seguida, selecione **usar as credenciais do Windows ao conectar-se à fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="de300-122">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials when connecting to the data source**.</span></span>  
  
    -   <span data-ttu-id="de300-123">Se o nome de usuário e a senha forem credenciais do banco de dados, não selecione **Usar as credenciais do Windows ao conectar-se à fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="de300-123">If the user name and password are database credentials, do not select **Use as Windows credentials when connecting to the data source**.</span></span> <span data-ttu-id="de300-124">Se o servidor de banco de dados oferecer suporte à representação ou delegação, você poderá selecionar **Definir o contexto de execução para esta conta**.</span><span class="sxs-lookup"><span data-stu-id="de300-124">If the database server supports impersonation or delegation, you can select **Set execution context to this account**.</span></span>  
  
8.  <span data-ttu-id="de300-125">Para verificar se a fonte de dados pode se conectar usando as credenciais atualizadas, clique em **Testar conexão**.</span><span class="sxs-lookup"><span data-stu-id="de300-125">To verify the data source can connect by using the updated credentials, click **Test connection**.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-update-a-shared-data-source-to-use-stored-credentials"></a><span data-ttu-id="de300-126">Para atualizar uma fonte de dados compartilhada para usar credenciais armazenadas</span><span class="sxs-lookup"><span data-stu-id="de300-126">To update a shared data source to use stored credentials</span></span>  
  
1.  <span data-ttu-id="de300-127">Vá para a biblioteca de documentos do SharePoint onde salvou a fonte de dados compartilhada.</span><span class="sxs-lookup"><span data-stu-id="de300-127">Go to the SharePoint document library where you saved the shared data source.</span></span>  
  
2.  <span data-ttu-id="de300-128">Clique no ícone para expandir o menu suspenso na fonte de dados compartilhada e clique em **Editar Definição da Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="de300-128">Click the icon for the expand drop-down menu on shared data source, and then click **Edit Data Source Definition**.</span></span>  
  
     <span data-ttu-id="de300-129">A página Fonte de Dados será aberta.</span><span class="sxs-lookup"><span data-stu-id="de300-129">The Data Source page opens.</span></span>  
  
3.  <span data-ttu-id="de300-130">Deixe as opções **Tipo de Fonte de Dados** e **Cadeia de conexão** como estão, a menos que você deseje que a fonte de dados compartilhada se conecte a outro tipo de fonte de dados, a outro servidor ou a um armazenamento de dados.</span><span class="sxs-lookup"><span data-stu-id="de300-130">Leave the **Data Source Type** and **Connection string** options as they are, unless you want the shared data source to connect to different type of data source, a different server, or data store.</span></span>  
  
4.  <span data-ttu-id="de300-131">Em **Credenciais**, selecione **Credenciais armazenadas**.</span><span class="sxs-lookup"><span data-stu-id="de300-131">For **Credentials**, select **Stored credentials**.</span></span>  
  
     <span data-ttu-id="de300-132">A opção **Não são necessárias credenciais** também pode ser usada em algumas circunstâncias.</span><span class="sxs-lookup"><span data-stu-id="de300-132">The **Credentials are not required** option can also be used under some circumstances.</span></span> <span data-ttu-id="de300-133">Essa opção só funcionará se a fonte de dados não aceitar credenciais ou se você estiver passando as credenciais de alguma outra forma.</span><span class="sxs-lookup"><span data-stu-id="de300-133">This option works only if the data source does not accept credentials or if you are passing credentials some other way.</span></span>  
  
     <span data-ttu-id="de300-134">Em alguns tipos de fonte de dados, a conta de execução autônoma deve estar configurada no servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="de300-134">From some data source types, the unattended execution account must be configured on the report server.</span></span> <span data-ttu-id="de300-135">Para obter mais informações, consulte o tópico do tipo de fonte de dados correspondente em [Adicionar dados de fontes de dados externas &#40;SSRS&#41;](add-data-from-external-data-sources-ssrs.md) e [Configurar a conta de execução autônoma &#40;Gerenciador de Configurações do SSRS&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="de300-135">For more information, see the topic for the corresponding data source type in [Add Data from External Data Sources &#40;SSRS&#41;](add-data-from-external-data-sources-ssrs.md) and [Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span></span>  
  
5.  <span data-ttu-id="de300-136">Digite um nome de usuário e uma senha.</span><span class="sxs-lookup"><span data-stu-id="de300-136">Type a user name and password.</span></span>  
  
    -   <span data-ttu-id="de300-137">Se a conta for uma conta de usuário de domínio do Windows, especifique-a neste formato: \<domain> \\<conta \> e, em seguida, selecione **usar as credenciais do Windows ao conectar-se à fonte de dados.**</span><span class="sxs-lookup"><span data-stu-id="de300-137">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials when connecting to the data source.**</span></span>  
  
    -   <span data-ttu-id="de300-138">Se o nome de usuário e a senha forem credenciais do banco de dados, não selecione **Usar as credenciais do Windows ao conectar-se à fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="de300-138">If the user name and password are database credentials, do not select **Use as Windows credentials when connecting to the data source**.</span></span> <span data-ttu-id="de300-139">Se o servidor de banco de dados oferecer suporte à representação ou delegação, você poderá selecionar **Definir o contexto de execução para esta conta**.</span><span class="sxs-lookup"><span data-stu-id="de300-139">If the database server supports impersonation or delegation, you can select **Set execution context to this account**.</span></span>  
  
6.  <span data-ttu-id="de300-140">Para verificar se a fonte de dados pode se conectar usando as credenciais atualizadas, clique em **Testar conexão**.</span><span class="sxs-lookup"><span data-stu-id="de300-140">To verify the data source can connect using the updated credentials, **Test connection**.</span></span>  
  
7.  <span data-ttu-id="de300-141">Verifique se a opção Habilitar esta fonte de dados está selecionada.</span><span class="sxs-lookup"><span data-stu-id="de300-141">Verify that Enable this data source is selected.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="de300-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="de300-142">See Also</span></span>  
 [<span data-ttu-id="de300-143">Carregar documentos em uma biblioteca do SharePoint &#40;Reporting Services no modo do SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="de300-143">Upload Documents to a SharePoint Library &#40;Reporting Services in SharePoint Mode&#41;</span></span>](../upload-documents-to-a-sharepoint-library-reporting-services-in-sharepoint-mode.md)  
  
  
