---
title: Armazenar credenciais em uma fonte de dados do Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 09/23/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- credentials [Reporting Services]
- security [Analysis Services], data sources
- stored credentials [Reporting Services]
- data sources [Reporting Services], stored credentials
ms.assetid: dc700922-97fa-4b30-9547-05bbbec4f09c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fccf8669d1f39d19a26b443ffcead8e86db66a34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576229"
---
# <a name="store-credentials-in-a-reporting-services-data-source"></a><span data-ttu-id="051e1-102">Store Credentials in a Reporting Services Data Source</span><span class="sxs-lookup"><span data-stu-id="051e1-102">Store Credentials in a Reporting Services Data Source</span></span>
  <span data-ttu-id="051e1-103">Você pode configurar credenciais armazenadas usadas por um servidor de relatórios do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] para acessar dados externos de um relatório.</span><span class="sxs-lookup"><span data-stu-id="051e1-103">You can configure stored credentials that a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] report server uses to access external data for a report.</span></span> <span data-ttu-id="051e1-104">As credenciais armazenadas serão usadas se o relatório for executado autônomo, por exemplo, uma assinatura do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] que publica um relatório como um email.</span><span class="sxs-lookup"><span data-stu-id="051e1-104">Stored credentials are used if the report runs unattended, for example a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] subscription that publishes a report as an e-mail.</span></span> <span data-ttu-id="051e1-105">O servidor de relatórios recupera e usa as credenciais quando o processamento do relatório é agendado ou disparado.</span><span class="sxs-lookup"><span data-stu-id="051e1-105">The report server retrieves and uses the credentials when report processing is scheduled or triggered.</span></span> <span data-ttu-id="051e1-106">Este tópico explica como configurar credenciais armazenadas para servidores de relatórios tanto no modo nativo quanto no modo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="051e1-106">This topic walks you through configuring stored credentials for both Native mode and SharePoint mode report servers.</span></span>

||
|-|
|<span data-ttu-id="051e1-107">**[!INCLUDE[applies](../../includes/applies-md.md)]** Modo nativo do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] &#124; modo do SharePoint para [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="051e1-107">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Native mode &#124; [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] SharePoint mode</span></span>|

 <span data-ttu-id="051e1-108">**Neste tópico:**</span><span class="sxs-lookup"><span data-stu-id="051e1-108">**In this topic:**</span></span>

-   [<span data-ttu-id="051e1-109">Configurar credenciais armazenadas para uma fonte de dados específica do relatório (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="051e1-109">Configure stored credentials for a report-specific data source (Native mode)</span></span>](#bkmk_stored_credentials_data_source_native)

-   [<span data-ttu-id="051e1-110">Configurar credenciais armazenadas para uma fonte de dados específica do relatório (modo SharePoint)</span><span class="sxs-lookup"><span data-stu-id="051e1-110">Configure stored credentials for a report-specific data source (SharePoint mode)</span></span>](#bkmk_stored_credentials_data_source_sharepoint)

-   [<span data-ttu-id="051e1-111">Configurar credenciais armazenadas para uma fonte de dados compartilhada (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="051e1-111">Configure stored credentials for a shared data source (Native mode)</span></span>](#bkmk_stored_credentials_shared_data_source_native)

-   [<span data-ttu-id="051e1-112">Configurar credenciais armazenadas para uma fonte de dados compartilhada (modo SharePoint)</span><span class="sxs-lookup"><span data-stu-id="051e1-112">Configure stored credentials for a shared data source (SharePoint mode)</span></span>](#bkmk_stored_credentials_shared_data_source_sharepoint)

##  <a name="security-policy-requirements-for-stored-credentials"></a><a name="bkmk_top"></a> <span data-ttu-id="051e1-113">Requisitos da política de segurança para credenciais armazenadas</span><span class="sxs-lookup"><span data-stu-id="051e1-113">Security policy requirements for stored credentials</span></span>
 <span data-ttu-id="051e1-114">![as_powerpivot_refresh_sss_set_key](../../analysis-services/media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key") é necessário que a conta usada para as credenciais armazenadas esteja configurada para uma das políticas de segurança a seguir no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="051e1-114">![as_powerpivot_refresh_sss_set_key](../../analysis-services/media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key") It is required that the account you use for stored credentials, is configured for one of the following security policies on the report server.</span></span> <span data-ttu-id="051e1-115">É recomendável escolher a política com o nível mínimo de permissões que você precisa para o ambiente.</span><span class="sxs-lookup"><span data-stu-id="051e1-115">It is recommended you select the policy with the minimum level of permissions you require for your environment.</span></span>

1.  <span data-ttu-id="051e1-116">**Permitir logon local**.</span><span class="sxs-lookup"><span data-stu-id="051e1-116">**Allow log on locally**.</span></span> <span data-ttu-id="051e1-117">Para obter mais informações, consulte [Permitir logon localmente](https://technet.microsoft.com/library/cc756809\(v=WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="051e1-117">For more information, see [Allow log on locally](https://technet.microsoft.com/library/cc756809\(v=WS.10\).aspx).</span></span>

2.  <span data-ttu-id="051e1-118">**Fazer logon como um trabalho em lotes**.</span><span class="sxs-lookup"><span data-stu-id="051e1-118">**Log on as a batch job**.</span></span> <span data-ttu-id="051e1-119">Para obter mais informações, consulte [Fazer logon como um trabalho em lotes](https://technet.microsoft.com/library/cc755659\(v=ws.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="051e1-119">For more information, see [Log on as a batch job](https://technet.microsoft.com/library/cc755659\(v=ws.10\).aspx).</span></span>

3.  <span data-ttu-id="051e1-120">Para obter informações gerais sobre as políticas, consulte [Editar configurações de segurança em um objeto de política de grupo](https://technet.microsoft.com/library/cc736516\(v=ws.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="051e1-120">For general information on policies, see [Edit security settings on a Group Policy object](https://technet.microsoft.com/library/cc736516\(v=ws.10\).aspx).</span></span>

##  <a name="configure-stored-credentials-for-a-report-specific-data-source-native-mode"></a><a name="bkmk_stored_credentials_data_source_native"></a> <span data-ttu-id="051e1-121">Configurar credenciais armazenadas para uma fonte de dados específica do relatório (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="051e1-121">Configure stored credentials for a report-specific data source (Native mode)</span></span>

1.  <span data-ttu-id="051e1-122">No Gerenciador de Relatórios no modo nativo, navegue até a pasta que contém o relatório.</span><span class="sxs-lookup"><span data-stu-id="051e1-122">In Native mode Report Manager, browse to the folder that contains the report.</span></span> <span data-ttu-id="051e1-123">Clique no menu de contexto do menu de contexto do item ![no Gerenciador de relatórios para itens do SSRS](../media/ssrs-report-manager-item-context-menu.png "menu de contexto no gerenciador de relatórios para itens ssrs").</span><span class="sxs-lookup"><span data-stu-id="051e1-123">Click the item context menu ![context menu in report manager for ssrs items](../media/ssrs-report-manager-item-context-menu.png "context menu in report manager for ssrs items").</span></span>

2.  <span data-ttu-id="051e1-124">Clique em **Gerenciar** e clique em **Fontes de Dados**.</span><span class="sxs-lookup"><span data-stu-id="051e1-124">Click **Manage** and then click **Data Sources**.</span></span>

3.  <span data-ttu-id="051e1-125">Selecione **Uma fonte de dados personalizada**.</span><span class="sxs-lookup"><span data-stu-id="051e1-125">Select **A custom data source**.</span></span>

4.  <span data-ttu-id="051e1-126">Na lista **Tipo de Fonte de Dados** , selecione a extensão de processamento de dados usada para processar os dados da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="051e1-126">In the **Data Source Type** list, select the data processing extension that is used to process data from the data source.</span></span>

5.  <span data-ttu-id="051e1-127">Para **cadeia de conexão**, especifique a cadeia de conexão que o servidor de relatório usa para se conectar à fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="051e1-127">For **Connection String**, specify the connection string that the report server uses to connect to the data source.</span></span> <span data-ttu-id="051e1-128">O exemplo a seguir ilustra uma cadeia de conexão usada para se conectar ao [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] banco de dados:</span><span class="sxs-lookup"><span data-stu-id="051e1-128">The following example illustrates a connection string used to connect to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database:</span></span>

    ```
    data source=<servername>;initial catalog=AdventureWorks2012
    ```

6.  <span data-ttu-id="051e1-129">Para **Conectar usando**, selecione **Credenciais armazenadas com segurança no servidor de relatório**.</span><span class="sxs-lookup"><span data-stu-id="051e1-129">For **Connect Using**, select **Credentials stored securely in the report server**.</span></span>

7.  <span data-ttu-id="051e1-130">Digite um nome de usuário e uma senha.</span><span class="sxs-lookup"><span data-stu-id="051e1-130">Type a user name and password.</span></span>

    -   <span data-ttu-id="051e1-131">Se a conta for uma conta de usuário de domínio do Windows, especifique-a neste formato: \<domain> \\<conta \> e, em seguida, selecione **usar as credenciais do Windows ao conectar-se à fonte de dados.**</span><span class="sxs-lookup"><span data-stu-id="051e1-131">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials when connecting to the data source.**</span></span>

    -   <span data-ttu-id="051e1-132">Se o nome de usuário e a senha forem credenciais do banco de dados, não selecione **Usar as credenciais do Windows ao conectar-se à fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="051e1-132">If the user name and password are database credentials, do not select **Use as Windows credentials when connecting to the data source**.</span></span> <span data-ttu-id="051e1-133">Se o servidor do banco de dados oferecer suporte a representação ou delegação, é possível selecionar **Representar o usuário autenticado depois que uma conexão é estabelecida com a fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="051e1-133">If the database server supports impersonation or delegation, you can select **Impersonate the authenticated user after a connection has been made to the data source**.</span></span>

8.  <span data-ttu-id="051e1-134">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="051e1-134">Click **Apply**.</span></span>

     <span data-ttu-id="051e1-135">![Ícone de seta usado com o link Voltar ao Início](../../2014-toc/media/uparrow16x16.gif "Ícone de seta usado com o link Voltar ao Início") [Requisitos da política de segurança para credenciais armazenadas](#bkmk_top)</span><span class="sxs-lookup"><span data-stu-id="051e1-135">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Security policy requirements for stored credentials](#bkmk_top)</span></span>

##  <a name="configure-stored-credentials-for-a-report-specific-data-source-sharepoint-mode"></a><a name="bkmk_stored_credentials_data_source_sharepoint"></a><span data-ttu-id="051e1-136">Configurar credenciais armazenadas para uma fonte de dados específica do relatório (modo do SharePoint)</span><span class="sxs-lookup"><span data-stu-id="051e1-136">Configure stored credentials for a report-specific data source (SharePoint mode)</span></span>

1.  <span data-ttu-id="051e1-137">Navegue até a biblioteca de documentos que contém o relatório e, em seguida, clique no menu aberto ![menu de contexto da biblioteca de documentos para itens do SSRS](../media/ssrs-sharepoint-item-context-menu.png "menu de contexto da biblioteca de documentos para itens SSRS").</span><span class="sxs-lookup"><span data-stu-id="051e1-137">Browse to the document library that contains the report and then click the open menu ![document library context menu for ssrs items](../media/ssrs-sharepoint-item-context-menu.png "document library context menu for ssrs items").</span></span>

2.  <span data-ttu-id="051e1-138">Clique no segundo menu aberto ![menu de contexto da biblioteca de documentos para itens do SSRS](../media/ssrs-sharepoint-item-context-menu.png "menu de contexto da biblioteca de documentos para itens SSRS") e, em seguida, clique em **Gerenciar Fontes de Dados**.</span><span class="sxs-lookup"><span data-stu-id="051e1-138">Click second open menu ![document library context menu for ssrs items](../media/ssrs-sharepoint-item-context-menu.png "document library context menu for ssrs items") and then click **Manage Data Sources**.</span></span>

3.  <span data-ttu-id="051e1-139">Clique no nome da fonte de dados **Personalizado** que deseja configurar com as credenciais armazenadas.</span><span class="sxs-lookup"><span data-stu-id="051e1-139">Click the name of the **Custom** data source you want to configure with stored credentials.</span></span>

4.  <span data-ttu-id="051e1-140">Na lista **Tipo de Fonte de Dados** , selecione a extensão de processamento de dados usada para processar os dados da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="051e1-140">In the **Data Source Type** list, select the data processing extension that is used to process data from the data source.</span></span>

5.  <span data-ttu-id="051e1-141">Para **cadeia de conexão**, especifique a cadeia de conexão que o servidor de relatório usa para se conectar à fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="051e1-141">For **Connection String**, specify the connection string that the report server uses to connect to the data source.</span></span> <span data-ttu-id="051e1-142">O exemplo a seguir ilustra uma cadeia de conexão usada para se conectar ao [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] banco de dados:</span><span class="sxs-lookup"><span data-stu-id="051e1-142">The following example illustrates a connection string used to connect to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database:</span></span>

    ```
    data source=<servername>;initial catalog=AdventureWorks2012
    ```

6.  <span data-ttu-id="051e1-143">Em **Credenciais**, selecione **Credenciais Armazenadas**.</span><span class="sxs-lookup"><span data-stu-id="051e1-143">For **Credentials**, select **Stored Credentials**.</span></span>

7.  <span data-ttu-id="051e1-144">Digite um **nome de usuário** e uma **senha**.</span><span class="sxs-lookup"><span data-stu-id="051e1-144">Type a **user name** and **password**.</span></span>

    -   <span data-ttu-id="051e1-145">Se a conta for uma conta de usuário de domínio do Windows, especifique-a neste formato: \<domain> \\<conta \> e, em seguida, selecione **usar as credenciais do Windows ao conectar-se à fonte de dados.**</span><span class="sxs-lookup"><span data-stu-id="051e1-145">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials when connecting to the data source.**</span></span>

    -   <span data-ttu-id="051e1-146">Se o nome de usuário e a senha forem credenciais de banco de dados, não selecione **Usar como credenciais do Windows**.</span><span class="sxs-lookup"><span data-stu-id="051e1-146">If the user name and password are database credentials, do not select **Use as Windows credentials**.</span></span> <span data-ttu-id="051e1-147">Se o servidor de banco de dados oferecer suporte à representação ou delegação, você poderá selecionar **Definir contexto de execução para esta conta**.</span><span class="sxs-lookup"><span data-stu-id="051e1-147">If the database server supports impersonation or delegation, you can select **Set execution context to this account**.</span></span>

8.  <span data-ttu-id="051e1-148">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="051e1-148">Click **ok**.</span></span>

     <span data-ttu-id="051e1-149">![Ícone de seta usado com o link Voltar ao Início](../../2014-toc/media/uparrow16x16.gif "Ícone de seta usado com o link Voltar ao Início") [Requisitos da política de segurança para credenciais armazenadas](#bkmk_top)</span><span class="sxs-lookup"><span data-stu-id="051e1-149">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Security policy requirements for stored credentials](#bkmk_top)</span></span>

##  <a name="configure-stored-credentials-for-a-shared-data-source-native-mode"></a><a name="bkmk_stored_credentials_shared_data_source_native"></a> <span data-ttu-id="051e1-150">Configurar credenciais armazenadas para uma fonte de dados compartilhada (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="051e1-150">Configure stored credentials for a shared data source (Native mode)</span></span>

1.  <span data-ttu-id="051e1-151">No Gerenciador de Relatórios no modo nativo, navegue até o item da fonte de dados compartilhada.</span><span class="sxs-lookup"><span data-stu-id="051e1-151">In Native mode Report Manager, browse to the shared data source item.</span></span> <span data-ttu-id="051e1-152">![Ícone da fonte de dados compartilhada](../media/hlp-16datasource.png "Ícone da fonte de dados compartilhada")</span><span class="sxs-lookup"><span data-stu-id="051e1-152">![Shared data source icon](../media/hlp-16datasource.png "Shared data source icon")</span></span>

2.  <span data-ttu-id="051e1-153">Clique no menu de contexto do menu de contexto ![no Gerenciador de relatórios para itens do SSRS](../media/ssrs-report-manager-item-context-menu.png "menu de contexto no gerenciador de relatórios para itens ssrs") e clique em **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="051e1-153">Click the context menu ![context menu in report manager for ssrs items](../media/ssrs-report-manager-item-context-menu.png "context menu in report manager for ssrs items") and then click **Manage**.</span></span>

3.  <span data-ttu-id="051e1-154">Na lista **tipo de fonte de dados** , especifique a extensão de processamento de dados usada para processar dados da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="051e1-154">In the **Data Source Type** list, specify the data processing extension that is used to process data from the data source.</span></span>

4.  <span data-ttu-id="051e1-155">Para **cadeia de conexão**, especifique a cadeia de conexão que o servidor de relatório usa para se conectar à fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="051e1-155">For **Connection String**, specify the connection string that the report server uses to connect to the data source.</span></span> [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="051e1-156">recomenda não especificar credenciais na cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="051e1-156">recommends that you do not specify credentials in the connection string.</span></span>

     <span data-ttu-id="051e1-157">O exemplo a seguir ilustra uma cadeia de conexão usada para se conectar ao [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] banco de dados local:</span><span class="sxs-lookup"><span data-stu-id="051e1-157">The following example illustrates a connection string used to connect to the local [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database:</span></span>

    ```
    data source=<localservername>; initial catalog=AdventureWorks2012
    ```

5.  <span data-ttu-id="051e1-158">Digite um nome de usuário e uma senha.</span><span class="sxs-lookup"><span data-stu-id="051e1-158">Type a user name and password.</span></span>

    -   <span data-ttu-id="051e1-159">Se a conta for uma conta de usuário de domínio do Windows, especifique-a neste formato: \<domain> \\<conta \> e, em seguida, selecione **usar as credenciais do Windows ao conectar-se à fonte de dados.**</span><span class="sxs-lookup"><span data-stu-id="051e1-159">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials when connecting to the data source.**</span></span>

    -   <span data-ttu-id="051e1-160">Se o nome de usuário e a senha forem credenciais do banco de dados, não selecione **Usar as credenciais do Windows ao conectar-se à fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="051e1-160">If the user name and password are database credentials, do not select **Use as Windows credentials when connecting to the data source**.</span></span> <span data-ttu-id="051e1-161">Se o servidor do banco de dados oferecer suporte a representação ou delegação, é possível selecionar **Representar o usuário autenticado depois que uma conexão é estabelecida com a fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="051e1-161">If the database server supports impersonation or delegation, you can select **Impersonate the authenticated user after a connection has been made to the data source**.</span></span>

6.  <span data-ttu-id="051e1-162">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="051e1-162">Click **Apply**.</span></span>

     <span data-ttu-id="051e1-163">![Ícone de seta usado com o link Voltar ao Início](../../2014-toc/media/uparrow16x16.gif "Ícone de seta usado com o link Voltar ao Início") [Requisitos da política de segurança para credenciais armazenadas](#bkmk_top)</span><span class="sxs-lookup"><span data-stu-id="051e1-163">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Security policy requirements for stored credentials](#bkmk_top)</span></span>

##  <a name="configure-stored-credentials-for-a-shared-data-source-sharepoint-mode"></a><a name="bkmk_stored_credentials_shared_data_source_sharepoint"></a><span data-ttu-id="051e1-164">Configurar credenciais armazenadas para uma fonte de dados compartilhada (modo do SharePoint)</span><span class="sxs-lookup"><span data-stu-id="051e1-164">Configure stored credentials for a shared data source (SharePoint mode)</span></span>

1.  <span data-ttu-id="051e1-165">Na biblioteca de documentos, navegue até o item de fonte de dados compartilhada.![Ícone de fonte de dados compartilhada](../media/hlp-16datasource.png "Ícone da fonte de dados compartilhada")</span><span class="sxs-lookup"><span data-stu-id="051e1-165">In the document library, browse to the shared data source item.![Shared data source icon](../media/hlp-16datasource.png "Shared data source icon")</span></span>

2.  <span data-ttu-id="051e1-166">Clique no menu de contexto ![menu de contexto da biblioteca de documentos para itens do SSRS](../media/ssrs-sharepoint-item-context-menu.png "menu de contexto da biblioteca de documentos para itens SSRS") e, em seguida, clique no segundo menu de contexto ![menu de contexto da biblioteca de documentos para itens SSRS](../media/ssrs-sharepoint-item-context-menu.png "menu de contexto da biblioteca de documentos para itens SSRS").</span><span class="sxs-lookup"><span data-stu-id="051e1-166">Click the context menu ![document library context menu for ssrs items](../media/ssrs-sharepoint-item-context-menu.png "document library context menu for ssrs items") and then click the second context menu ![document library context menu for ssrs items](../media/ssrs-sharepoint-item-context-menu.png "document library context menu for ssrs items").</span></span>

3.  <span data-ttu-id="051e1-167">Clique em **Editar Definição da Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="051e1-167">Click **Edit Data Source Definition**.</span></span>

4.  <span data-ttu-id="051e1-168">Na lista **tipo de fonte de dados** , especifique a extensão de processamento de dados usada para processar dados da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="051e1-168">In the **Data Source Type** list, specify the data processing extension that is used to process data from the data source.</span></span>

5.  <span data-ttu-id="051e1-169">Para **cadeia de conexão**, especifique a cadeia de conexão que o servidor de relatório usa para se conectar à fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="051e1-169">For **Connection String**, specify the connection string that the report server uses to connect to the data source.</span></span> [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="051e1-170">recomenda não especificar credenciais na cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="051e1-170">recommends that you do not specify credentials in the connection string.</span></span>

     <span data-ttu-id="051e1-171">O exemplo a seguir ilustra uma cadeia de conexão usada para se conectar ao [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] banco de dados local:</span><span class="sxs-lookup"><span data-stu-id="051e1-171">The following example illustrates a connection string used to connect to the local [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database:</span></span>

    ```
    data source=<localservername>; initial catalog=AdventureWorks2012
    ```

6.  <span data-ttu-id="051e1-172">Digite um nome de usuário e uma senha.</span><span class="sxs-lookup"><span data-stu-id="051e1-172">Type a user name and password.</span></span>

    -   <span data-ttu-id="051e1-173">Se a conta for uma conta de usuário de domínio do Windows, especifique-a neste formato: \<domain> \\<conta \> e, em seguida, selecione **usar como credenciais do Windows.**</span><span class="sxs-lookup"><span data-stu-id="051e1-173">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials.**</span></span>

    -   <span data-ttu-id="051e1-174">Se o nome de usuário e a senha forem credenciais de banco de dados, não selecione **Usar como credenciais do Windows**.</span><span class="sxs-lookup"><span data-stu-id="051e1-174">If the user name and password are database credentials, do not select **Use as Windows credentials**.</span></span> <span data-ttu-id="051e1-175">Se o servidor de banco de dados oferecer suporte à representação ou delegação, você poderá selecionar **Definir o contexto de execução para esta conta**.</span><span class="sxs-lookup"><span data-stu-id="051e1-175">If the database server supports impersonation or delegation, you can select **Set Execution context to this account**.</span></span>

7.  <span data-ttu-id="051e1-176">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="051e1-176">Click **Ok**.</span></span>

     <span data-ttu-id="051e1-177">![Ícone de seta usado com o link Voltar ao Início](../../2014-toc/media/uparrow16x16.gif "Ícone de seta usado com o link Voltar ao Início") [Requisitos da política de segurança para credenciais armazenadas](#bkmk_top)</span><span class="sxs-lookup"><span data-stu-id="051e1-177">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Security policy requirements for stored credentials](#bkmk_top)</span></span>

## <a name="see-also"></a><span data-ttu-id="051e1-178">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="051e1-178">See Also</span></span>
 <span data-ttu-id="051e1-179">[Especificar informações de credencial e de conexão para fontes de dados de relatório](../../integration-services/connection-manager/data-sources.md) [Configurar Propriedades da fonte de dados para um relatório &#40;Report Manager&#41;](configure-data-source-properties-for-a-report-report-manager.md) [criar, excluir ou modificar uma fonte de dados compartilhada &#40;Report Manager](../create-delete-or-modify-a-shared-data-source-report-manager.md)&#41;[página de propriedades de fontes de dados](../data-sources-properties-page-report-manager.md) &#40;Report Manager página&#41;[nova fonte de dados &#40;Report Manager](../new-data-source-page-report-manager.md)&#41;</span><span class="sxs-lookup"><span data-stu-id="051e1-179">[Specify Credential and Connection Information for Report Data Sources](../../integration-services/connection-manager/data-sources.md) [Configure Data Source Properties for a Report  &#40;Report Manager&#41;](configure-data-source-properties-for-a-report-report-manager.md) [Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) [Data Sources Properties Page &#40;Report Manager&#41;](../data-sources-properties-page-report-manager.md) [New Data Source Page &#40;Report Manager&#41;](../new-data-source-page-report-manager.md)</span></span>


