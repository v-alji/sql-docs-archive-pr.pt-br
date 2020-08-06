---
title: Criar, excluir ou modificar uma fonte de dados compartilhada (Report Manager) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- shared data sources [Reporting Services]
- removing shared data sources
- data sources [Reporting Services], shared
- deleting shared data sources
- modifying shared data sources
ms.assetid: cd7bace3-f8ec-4ee3-8a9f-2f217cdca9f2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c6f4ff658e656b159995087df3121806b462e687
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574555"
---
# <a name="create-delete-or-modify-a-shared-data-source-report-manager"></a><span data-ttu-id="1b1f0-102">Criar, excluir ou modificar uma fonte de dados compartilhada (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="1b1f0-102">Create, Delete, or Modify a Shared Data Source (Report Manager)</span></span>
  <span data-ttu-id="1b1f0-103">Uma fonte de dados compartilhada especifica propriedades de conexão para uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-103">A shared data source specifies connection properties for a data source.</span></span> <span data-ttu-id="1b1f0-104">Se você tiver uma fonte de dados usada por um número grande de relatórios, modelos ou assinaturas controladas por dados, considere a criação de uma fonte de dados compartilhada para eliminar a sobrecarga em manter as mesmas informações de conexão em vários lugares.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-104">If you have a data source that is used by a large number of reports, models, or data-driven subscriptions, consider creating a shared data source to eliminate the overhead of having to maintain the same connection information in multiple places.</span></span>  
  
 <span data-ttu-id="1b1f0-105">O ícone seguinte indica uma fonte de dados compartilhada na hierarquia da pasta do Gerenciador de Relatórios:</span><span class="sxs-lookup"><span data-stu-id="1b1f0-105">The following icon indicates a shared data source in the Report Manager folder hierarchy:</span></span>  
  
 <span data-ttu-id="1b1f0-106">![Ícone da fonte de dados compartilhada](media/hlp-16datasource.png "Ícone da fonte de dados compartilhada")</span><span class="sxs-lookup"><span data-stu-id="1b1f0-106">![Shared data source icon](media/hlp-16datasource.png "Shared data source icon")</span></span>  
<span data-ttu-id="1b1f0-107">ícone de fonte de dados compartilhada</span><span class="sxs-lookup"><span data-stu-id="1b1f0-107">shared data source icon</span></span>  
  
### <a name="to-create-a-shared-data-source"></a><span data-ttu-id="1b1f0-108">Para criar uma fonte de dados compartilhada</span><span class="sxs-lookup"><span data-stu-id="1b1f0-108">To create a shared data source</span></span>  
  
1.  <span data-ttu-id="1b1f0-109">Inicie o [Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="1b1f0-109">Start [Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="1b1f0-110">Em Report Manager, navegue até a página **conteúdo** .</span><span class="sxs-lookup"><span data-stu-id="1b1f0-110">In Report Manager, navigate to the **Contents** page.</span></span>  
  
3.  <span data-ttu-id="1b1f0-111">Clique em **Nova Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-111">Click **New Data Source**.</span></span> <span data-ttu-id="1b1f0-112">A página **Nova Fonte de Dados** será aberta.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-112">The **New Data Source** page opens.</span></span>  
  
4.  <span data-ttu-id="1b1f0-113">Digite um nome para o item.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-113">Type a name for the item.</span></span> <span data-ttu-id="1b1f0-114">Um nome deve conter pelo menos um caractere e deve começar com uma letra.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-114">A name must contain at least one character and it must start with a letter.</span></span> <span data-ttu-id="1b1f0-115">Ele também pode incluir certos símbolos, mas não espaços nem os caracteres ; ?</span><span class="sxs-lookup"><span data-stu-id="1b1f0-115">It can also include certain symbols, but not spaces or the characters ; ?</span></span> <span data-ttu-id="1b1f0-116">: \@ & = +, $/\* \< > | " /.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-116">: \@ & = + , $ / \* \< > | " /.</span></span>  
  
5.  <span data-ttu-id="1b1f0-117">Como opção, digite uma descrição para oferecer aos usuários informações sobre a conexão.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-117">Optionally type a description to provide users with information about the connection.</span></span> <span data-ttu-id="1b1f0-118">Essa descrição será exibida na página **Conteúdo** no Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-118">This description will appear on the **Contents** page in Report Manager.</span></span>  
  
6.  <span data-ttu-id="1b1f0-119">Na lista **Tipo de fonte de dados** , especifique a extensão de processamento de dados usada para processar dados da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-119">In the **Data source type** list, specify the data processing extension that is used to process data from the data source.</span></span>  
  
7.  <span data-ttu-id="1b1f0-120">Em **Cadeia de conexão**, especifique a cadeia de conexão usada pelo servidor de relatório para se conectar à fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-120">For **Connection string**, specify the connection string that the report server uses to connect to the data source.</span></span> <span data-ttu-id="1b1f0-121">Recomendamos que você não especifique credenciais na cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-121">It is recommended that you do not specify credentials in the connection string.</span></span>  
  
     <span data-ttu-id="1b1f0-122">O exemplo a seguir ilustra uma cadeia de conexão para se conectar ao [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] banco de dados local:</span><span class="sxs-lookup"><span data-stu-id="1b1f0-122">The following example illustrates a connection string for connecting to the local [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database:</span></span>  
  
    ```  
    data source=<localservername>; initial catalog=AdventureWorks2012  
    ```  
  
8.  <span data-ttu-id="1b1f0-123">Em **Conectar usando**, especifique como são obtidas as credenciais na execução do relatório:</span><span class="sxs-lookup"><span data-stu-id="1b1f0-123">For **Connect using**, specify how credentials are obtained when the report runs:</span></span>  
  
    -   <span data-ttu-id="1b1f0-124">Se desejar solicitar ao usuário o nome de logon e a senha, clique em **Credenciais fornecidas pelo usuário que está executando o relatório**.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-124">If you want to prompt the user for a logon name and password, click **Credentials supplied by the user running the report**.</span></span> <span data-ttu-id="1b1f0-125">Para usar as credenciais inseridas pelo usuário como credenciais do Windows, clique em **Usar as credenciais do Windows ao conectar-se à fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-125">To use the credentials that the user enters as Windows credentials, click **Use as Windows credentials when connecting to the data source**.</span></span> <span data-ttu-id="1b1f0-126">Se o nome de usuário e a senha forem credenciais de banco de dados, não selecione esta opção.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-126">If the user name and password are database credentials, do not select this option.</span></span>  
  
    -   <span data-ttu-id="1b1f0-127">Caso pretenda usar a fonte de dados como uma fonte de dados compartilhada com credenciais salvas que são gerenciadas pelo proprietário da fonte de dados, ou para relatórios que dão suporte a assinaturas ou outras operações agendadas (como a geração automatizada de histórico de relatório), clique em **Credenciais armazenadas com segurança no servidor de relatório**.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-127">If you intend to use the data source as a shared data source with saved credentials that are managed by the owner of the data source, or for reports that support subscriptions or other scheduled operations (such as automated report history generation), click **Credentials stored securely in the report server**.</span></span> <span data-ttu-id="1b1f0-128">Se o servidor do banco de dados oferecer suporte a representação ou delegação, é possível selecionar **Representar o usuário autenticado depois que uma conexão é estabelecida com a fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-128">If the database server supports impersonation or delegation, you can select **Impersonate the authenticated user after a connection has been made to the data source**.</span></span>  
  
    -   <span data-ttu-id="1b1f0-129">Se desejar que o servidor de relatório passe as credenciais do usuário que está acessando o relatório para o servidor que está hospedando a fonte de dados externa, clique em **Segurança Integrada do Windows**.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-129">If you want the report server to pass the credentials of the user accessing the report to the server hosting the external data source, click **Windows Integrated Security**.</span></span> <span data-ttu-id="1b1f0-130">Nesse caso, não é solicitado que o usuário digite um nome de usuário ou senha.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-130">In this case, the user is not prompted to type a user name or password.</span></span>  
  
    -   <span data-ttu-id="1b1f0-131">Se a fonte de dados não usar credenciais (se a fonte de dados for um arquivo XML acessado pelo sistema de arquivos, por exemplo), clique em **Não são necessárias credenciais**.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-131">If the data source does not use credentials (for example, if the data source is an XML file that is accessed from the file system), click **Credentials are not required**.</span></span> <span data-ttu-id="1b1f0-132">Você deve especificar esse tipo de credencial somente se ele for válido para a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-132">You should only specify this credential type if it is valid for the data source.</span></span> <span data-ttu-id="1b1f0-133">Se você selecionar essa opção para uma fonte de dados que requer autenticação, a conexão falhará.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-133">If you select this option for a data source that requires authentication, the connection will fail.</span></span> <span data-ttu-id="1b1f0-134">Se essa opção for selecionada, certifique-se de configurar a conta de execução autônoma que permite que o servidor de relatório se conecte a outros computadores para recuperar dados ou arquivos quando as credenciais do usuário não estiverem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-134">If you select this option, be sure to configure the unattended execution account that allows the report server to connect to other computers to retrieve data or files when user credentials are not available.</span></span>  
  
     <span data-ttu-id="1b1f0-135">Para obter mais informações sobre como configurar as credenciais, consulte [Especificar informações de credenciais e de conexão para fontes de dados de relatório](report-data/specify-credential-and-connection-information-for-report-data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="1b1f0-135">For more information about configuring credentials, see [Specify Credential and Connection Information for Report Data Sources](report-data/specify-credential-and-connection-information-for-report-data-sources.md).</span></span> <span data-ttu-id="1b1f0-136">Para obter mais informações sobre a conta de execução autônoma, consulte [Configurar a conta de execução autônoma &#40; 	Gerenciador de Configurações do SSRS&#41;](install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="1b1f0-136">For more information about the unattended execution account, see [Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span></span>  
  
9. <span data-ttu-id="1b1f0-137">Clique no botão **Testar Conexão** para validar a configuração da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-137">Click the **Test Connection** button to validate the data source configuration.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1b1f0-138">O botão Testar Conexão não tem suporte para o tipo de fonte de dados XML.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-138">The Test Connection button is not supported for the XML data source type.</span></span>  
  
10. <span data-ttu-id="1b1f0-139">Clique em **OK**</span><span class="sxs-lookup"><span data-stu-id="1b1f0-139">Click **OK**</span></span>  
  
### <a name="to-modify-a-shared-data-source"></a><span data-ttu-id="1b1f0-140">Para modificar uma fonte de dados compartilhada</span><span class="sxs-lookup"><span data-stu-id="1b1f0-140">To modify a shared data source</span></span>  
  
1.  <span data-ttu-id="1b1f0-141">No Gerenciador de Relatórios, navegue até a página Conteúdo.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-141">In Report Manager, navigate to the Contents page.</span></span>  
  
2.  <span data-ttu-id="1b1f0-142">Navegue até o item de fonte de dados compartilhada, focalize o item, clique na lista suspensa e, no menu de contexto, clique em **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-142">Navigate to the shared data source item, hover over the item, click the drop-down list, and from the context menu, click **Manage**.</span></span> <span data-ttu-id="1b1f0-143">A página **Propriedades** é exibida.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-143">The **Properties** page opens.</span></span>  
  
3.  <span data-ttu-id="1b1f0-144">Modifique a fonte de dados e clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-144">Modify the data source, and then click **Apply**.</span></span>  
  
### <a name="to-delete-a-shared-data-source"></a><span data-ttu-id="1b1f0-145">Para excluir uma fonte de dados compartilhada</span><span class="sxs-lookup"><span data-stu-id="1b1f0-145">To delete a shared data source</span></span>  
  
-   <span data-ttu-id="1b1f0-146">No Gerenciador de Relatórios, navegue até a página **Conteúdo** e execute uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="1b1f0-146">In Report Manager, navigate to the **Contents** page and do one of the following:</span></span>  
  
    -   <span data-ttu-id="1b1f0-147">Navegue até o item da fonte de dados compartilhada.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-147">Navigate to the shared data source item.</span></span>  
  
         <span data-ttu-id="1b1f0-148">Clique no item para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-148">Click the item to open it.</span></span> <span data-ttu-id="1b1f0-149">A página Propriedades Gerais será aberta.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-149">The General Properties page opens.</span></span>  
  
         <span data-ttu-id="1b1f0-150">Clique em **Excluir** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-150">Click **Delete**, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="1b1f0-151">Na página **Conteúdo** , navegue até a pasta que contém a fonte de dados que você quer excluir.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-151">In the **Contents** page, navigate to the folder that contains the data source you want to delete.</span></span>  
  
         <span data-ttu-id="1b1f0-152">Focalize o item, clique na lista suspensa e, no menu de contexto, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="1b1f0-152">Hover over the item, click the drop-down list, and from the context menu, click **Delete**.</span></span>  
  
         [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1b1f0-153">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1b1f0-153">See Also</span></span>  
 <span data-ttu-id="1b1f0-154">[Conexões de dados, fontes de dados e cadeias de conexão no Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="1b1f0-154">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 <span data-ttu-id="1b1f0-155">[Página de conteúdo &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="1b1f0-155">[Contents Page &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="1b1f0-156">[Criar, modificar e excluir fontes de dados compartilhadas &#40;SSRS&#41;](report-data/create-modify-and-delete-shared-data-sources-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1b1f0-156">[Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](report-data/create-modify-and-delete-shared-data-sources-ssrs.md) </span></span>  
 <span data-ttu-id="1b1f0-157">[Gerenciar fontes de dados de relatório](report-data/manage-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="1b1f0-157">[Manage Report Data Sources](report-data/manage-report-data-sources.md) </span></span>  
 [<span data-ttu-id="1b1f0-158">Configurar as propriedades de fonte de dados de um relatório &#40;Gerenciador de Relatórios&#41;</span><span class="sxs-lookup"><span data-stu-id="1b1f0-158">Configure Data Source Properties for a Report  &#40;Report Manager&#41;</span></span>](report-data/configure-data-source-properties-for-a-report-report-manager.md)  
  
  
