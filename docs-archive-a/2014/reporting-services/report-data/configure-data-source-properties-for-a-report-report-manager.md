---
title: Configurar as propriedades de fonte de dados de um relatório (Gerenciador de Relatórios) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- data sources [Reporting Services], embedded
ms.assetid: 27af5195-c845-40e0-9a9c-efe569424022
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 42969b4667dd71e4c6413f38e4deadb96491169c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570462"
---
# <a name="configure-data-source-properties-for-a-report--report-manager"></a><span data-ttu-id="f23cd-102">Configurar propriedades de fonte de dados para um relatório (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="f23cd-102">Configure Data Source Properties for a Report  (Report Manager)</span></span>
  <span data-ttu-id="f23cd-103">Quando um relatório é executado, o servidor de relatório recupera informações de propriedade para determinar como conectar-se a uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="f23cd-103">When you run a report, the report server retrieves property information to determine how to connect to a data source.</span></span> <span data-ttu-id="f23cd-104">O tipo de fonte de dados, a cadeia de conexão e as informações de credenciais são especificados nas páginas de propriedade Fonte de Dados do relatório publicado.</span><span class="sxs-lookup"><span data-stu-id="f23cd-104">The data source type, connection string, and credential information are specified in the Data Source property pages of the published report.</span></span> <span data-ttu-id="f23cd-105">É possível definir as propriedades para variar as informações de conexão da fonte de dados com relação aos valores originais que foram especificados quando o relatório foi criado.</span><span class="sxs-lookup"><span data-stu-id="f23cd-105">You can set the properties to vary the data source connection information from the original values that were specified when the report was created.</span></span>  
  
 <span data-ttu-id="f23cd-106">De maneira alternativa, se houver uma fonte de dados compartilhada predefinida que já especifica as informações de conexão que você deseja usar, você poderá especificar uma fonte de dados compartilhada.</span><span class="sxs-lookup"><span data-stu-id="f23cd-106">Alternatively, if you have a predefined shared data source that already specifies the connection information you want to use, you can specify a shared data source instead.</span></span> <span data-ttu-id="f23cd-107">Para usar uma fonte de dados compartilhada, clique em **Fonte de Dados Compartilhada** na página de propriedades Fonte de Dados do relatório.</span><span class="sxs-lookup"><span data-stu-id="f23cd-107">To use a shared data source, click **A shared data source** on the Data Source properties page of the report.</span></span>  
  
### <a name="to-configure-an-embedded-data-source"></a><span data-ttu-id="f23cd-108">Para configurar uma fonte de dados inserida</span><span class="sxs-lookup"><span data-stu-id="f23cd-108">To configure an embedded data source</span></span>  
  
1.  <span data-ttu-id="f23cd-109">Inicie o [Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="f23cd-109">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="f23cd-110">Em Report Manager, navegue até a página **conteúdo** .</span><span class="sxs-lookup"><span data-stu-id="f23cd-110">In Report Manager, navigate to the **Contents** page.</span></span> <span data-ttu-id="f23cd-111">Navegue até o relatório para o qual deseja configurar uma fonte de dados específica e abra o relatório.</span><span class="sxs-lookup"><span data-stu-id="f23cd-111">Navigate to the report that you want to configure a report-specific data source for, and open the report.</span></span>  
  
3.  <span data-ttu-id="f23cd-112">Clique na guia **Propriedades** . A página Propriedades **gerais** é aberta.</span><span class="sxs-lookup"><span data-stu-id="f23cd-112">Click the **Properties** tab. The **General** properties page opens.</span></span>  
  
4.  <span data-ttu-id="f23cd-113">Clique na guia **fontes de dados** . Isso abre a página Propriedades da fonte de dados do relatório.</span><span class="sxs-lookup"><span data-stu-id="f23cd-113">Click the **Data Sources** tab. This opens the Data Source properties page of the report.</span></span>  
  
5.  <span data-ttu-id="f23cd-114">Clique em **Uma fonte de dados personalizada** para especificar informações de conexão de fonte de dados no relatório.</span><span class="sxs-lookup"><span data-stu-id="f23cd-114">Click **A custom data source** to specify data source connection information within the report.</span></span>  
  
6.  <span data-ttu-id="f23cd-115">Na lista **Tipo de Conexão** , especifique a extensão de processamento de dados usada para processar dados da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="f23cd-115">In the **Connection Type** list, specify the data processing extension that is used to process data from the data source.</span></span>  
  
7.  <span data-ttu-id="f23cd-116">Para **cadeia de conexão**, especifique a cadeia de conexão que o servidor de relatório usa para se conectar à fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="f23cd-116">For **Connection String**, specify the connection string that the report server uses to connect to the data source.</span></span> <span data-ttu-id="f23cd-117">Recomendamos que você não especifique credenciais na cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="f23cd-117">It is recommended that you do not specify credentials in the connection string.</span></span>  
  
     <span data-ttu-id="f23cd-118">O exemplo a seguir ilustra uma cadeia de conexão para se conectar ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] banco de dados local:</span><span class="sxs-lookup"><span data-stu-id="f23cd-118">The following example illustrates a connection string for connecting to the local [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database:</span></span>  
  
    ```  
    data source=<localservername>; initial catalog=AdventureWorks2012  
    ```  
  
8.  <span data-ttu-id="f23cd-119">Em **Conectar usando**, especifique como são obtidas as credenciais na execução do relatório:</span><span class="sxs-lookup"><span data-stu-id="f23cd-119">For **Connect using**, specify how credentials are obtained when the report runs:</span></span>  
  
    -   <span data-ttu-id="f23cd-120">Se desejar solicitar ao usuário o nome de logon e a senha, clique em **Credenciais fornecidas pelo usuário que está executando o relatório**.</span><span class="sxs-lookup"><span data-stu-id="f23cd-120">If you want to prompt the user for a logon name and password, click **Credentials supplied by the user running the report**.</span></span>  
  
    -   <span data-ttu-id="f23cd-121">Se você pretende usar a fonte de dados com relatórios que dão suporte a assinaturas ou a outras operações agendadas (como geração automatizada do histórico de relatórios, por exemplo), clique em **Credenciais armazenadas com segurança no servidor de relatório**.</span><span class="sxs-lookup"><span data-stu-id="f23cd-121">If you intend to use the data source with reports that support subscriptions or other scheduled operations (such as automated report history generation), click **Credentials stored securely in the report server**.</span></span>  
  
    -   <span data-ttu-id="f23cd-122">Se desejar que o servidor de relatório passe as credenciais do usuário que está acessando o relatório para o servidor que está hospedando a fonte de dados externa, clique em **Segurança Integrada do Windows**.</span><span class="sxs-lookup"><span data-stu-id="f23cd-122">If you want the report server to pass the credentials of the user accessing the report to the server hosting the external data source, click **Windows Integrated Security**.</span></span> <span data-ttu-id="f23cd-123">Nesse caso, não é solicitado que o usuário digite um nome de usuário ou senha.</span><span class="sxs-lookup"><span data-stu-id="f23cd-123">In this case, the user is not prompted to type a user name or password.</span></span>  
  
    -   <span data-ttu-id="f23cd-124">Se a fonte de dados não usar credenciais (se a fonte de dados for um arquivo XML acessado pelo sistema de arquivos, por exemplo), clique em **Não são necessárias credenciais**.</span><span class="sxs-lookup"><span data-stu-id="f23cd-124">If the data source does not use credentials (for example, if the data source is an XML file that is accessed from the file system), click **Credentials are not required**.</span></span> <span data-ttu-id="f23cd-125">Você deve especificar esse tipo de credencial somente se ele for válido para a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="f23cd-125">You should only specify this credential type if it is valid for the data source.</span></span> <span data-ttu-id="f23cd-126">Se você selecionar essa opção para uma fonte de dados que requer autenticação, a conexão falhará.</span><span class="sxs-lookup"><span data-stu-id="f23cd-126">If you select this option for a data source that requires authentication, the connection will fail.</span></span> <span data-ttu-id="f23cd-127">Se essa opção for selecionada, certifique-se de configurar a conta de execução autônoma que permite que o servidor de relatório se conecte a outros computadores para recuperar dados ou arquivos quando as credenciais do usuário não estiverem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="f23cd-127">If you select this option, be sure to configure the unattended execution account that allows the report server to connect to other computers to retrieve data or files when user credentials are not available.</span></span>  
  
 <span data-ttu-id="f23cd-128">Para obter mais informações sobre como configurar as credenciais, consulte [Especificar informações de credenciais e de conexão para fontes de dados de relatório](specify-credential-and-connection-information-for-report-data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="f23cd-128">For more information about configuring credentials, see [Specify Credential and Connection Information for Report Data Sources](specify-credential-and-connection-information-for-report-data-sources.md).</span></span> <span data-ttu-id="f23cd-129">Para obter mais informações sobre a conta de execução autônoma, consulte [Configurar a conta de execução autônoma &#40; 	Gerenciador de Configurações do SSRS&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="f23cd-129">For more information about the unattended execution account, see [Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f23cd-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f23cd-130">See Also</span></span>  
 <span data-ttu-id="f23cd-131">[Página de conteúdo &#40;Report Manager&#41;](../contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="f23cd-131">[Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="f23cd-132">[Nova página de fonte de dados &#40;Report Manager&#41;](../new-data-source-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="f23cd-132">[New Data Source Page &#40;Report Manager&#41;](../new-data-source-page-report-manager.md) </span></span>  
 <span data-ttu-id="f23cd-133">[Criar, modificar e excluir fontes de dados compartilhadas &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f23cd-133">[Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md) </span></span>  
 <span data-ttu-id="f23cd-134">[Gerenciar fontes de dados de relatório](manage-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="f23cd-134">[Manage Report Data Sources](manage-report-data-sources.md) </span></span>  
 <span data-ttu-id="f23cd-135">[Criar, excluir ou modificar uma fonte de dados compartilhada &#40;Report Manager&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="f23cd-135">[Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span></span>  
 [<span data-ttu-id="f23cd-136">Página de propriedades Fontes de Dados &#40;Gerenciador de Relatórios&#41;</span><span class="sxs-lookup"><span data-stu-id="f23cd-136">Data Sources Properties Page &#40;Report Manager&#41;</span></span>](../data-sources-properties-page-report-manager.md)  
  
  
