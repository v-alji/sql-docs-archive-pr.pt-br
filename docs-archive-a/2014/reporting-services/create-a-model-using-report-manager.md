---
title: Criar um modelo usando Report Manager | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report models [Reporting Services], creating
- Report Manager [Reporting Services], model creation
ms.assetid: 8e5d2bd3-48ec-45f3-afee-6d86797c8f28
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 59ce278a22ec9797b001ca37a0bde576483cf5d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682168"
---
# <a name="create-a-model-using-report-manager"></a><span data-ttu-id="73da8-102">Criar um modelo com o Gerenciador de Relatórios</span><span class="sxs-lookup"><span data-stu-id="73da8-102">Create a Model Using Report Manager</span></span>
  <span data-ttu-id="73da8-103">Você pode gerar modelos de um cubo [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , um banco de dados [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ou um banco de dados Oracle usando o Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="73da8-103">You can generate models from an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube, a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database, or an Oracle database using Report Manager.</span></span> <span data-ttu-id="73da8-104">Os modelos de relatório são gerados a partir de fontes de dados compartilhadas que são publicadas no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="73da8-104">Report models are generated from shared data sources that are published on the report server.</span></span> <span data-ttu-id="73da8-105">Se você ainda não tiver uma fonte de dados compartilhada, é preciso criar uma.</span><span class="sxs-lookup"><span data-stu-id="73da8-105">If you do not already have a shared data source, you must create one.</span></span>  
  
 <span data-ttu-id="73da8-106">O modelo de relatório que você gera se baseia totalmente no esquema de fonte de dados compartilhados.</span><span class="sxs-lookup"><span data-stu-id="73da8-106">The report model that you generate is based entirely on the schema of the shared data source.</span></span> <span data-ttu-id="73da8-107">Não é possível escolher quais partes da fonte de dados são incluídas no modelo, nem é possível editar as regras ou metadados de um modelo gerado.</span><span class="sxs-lookup"><span data-stu-id="73da8-107">You cannot choose which parts of the data source are included in the model, nor can you edit the rules or metadata of a generated model.</span></span> <span data-ttu-id="73da8-108">Entretanto, você pode definir propriedades no modelo após ele ser gerado e definir atribuições de funções que restringem o acesso à parte ou a todo o modelo.</span><span class="sxs-lookup"><span data-stu-id="73da8-108">However, you can set properties on the model after it is generated and define role assignments that restrict access to all or part of the model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="73da8-109">Um modelo baseado em Oracle gerado usando Report Manager ou [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[offSPServ](../includes/offspserv-md.md)] 2007 [!INCLUDE[SPS2010](../includes/sps2010-md.md)] incluirá objetos de banco de dados que fazem parte do esquema para a conta de usuário usada para conectar-se à fonte do Oracle Data.</span><span class="sxs-lookup"><span data-stu-id="73da8-109">An Oracle-based model generated using Report Manager or [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[offSPServ](../includes/offspserv-md.md)] 2007 [!INCLUDE[SPS2010](../includes/sps2010-md.md)] will include database objects that are a part of the schema for the user account used to connect to the Oracle data source.</span></span> <span data-ttu-id="73da8-110">O nome de conta de usuário é especificado nas credenciais de propriedades de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="73da8-110">The user account name is specified in the data source properties credentials.</span></span>  
  
### <a name="to-create-a-new-data-source-for-a-report-model-using-report-manager"></a><span data-ttu-id="73da8-111">Para criar uma nova fonte de dados para um modelo de relatório que usa o Gerenciador de Relatórios</span><span class="sxs-lookup"><span data-stu-id="73da8-111">To create a new data source for a report model using Report Manager</span></span>  
  
1.  <span data-ttu-id="73da8-112">No navegador da Web, digite a URL do servidor de relatório na barra de endereços.</span><span class="sxs-lookup"><span data-stu-id="73da8-112">In your Web browser, type the URL for your report server in the address bar.</span></span>  
  
2.  <span data-ttu-id="73da8-113">Clique em **Nova Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="73da8-113">Click **New Data Source**.</span></span>  
  
3.  <span data-ttu-id="73da8-114">Na caixa **Nome** , digite um nome para a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="73da8-114">In the **Name** box, enter a name for the data source.</span></span>  
  
4.  <span data-ttu-id="73da8-115">Opcionalmente, digite uma breve descrição do modo na caixa de texto **Descrição** .</span><span class="sxs-lookup"><span data-stu-id="73da8-115">Optionally, enter a brief description of the mode in the **Description** text box.</span></span>  
  
5.  <span data-ttu-id="73da8-116">Verifique se a caixa de seleção **Habilitar esta fonte de dados** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="73da8-116">Verify that the **Enable this data source** check box is selected.</span></span>  
  
6.  <span data-ttu-id="73da8-117">Na lista **Tipo de conexão** , selecione o tipo de fonte de dados para o qual você deseja se conectar.</span><span class="sxs-lookup"><span data-stu-id="73da8-117">In the **Connection type** list, select the data source type to which you want to connect.</span></span> <span data-ttu-id="73da8-118">O tipo de conexão deve ser um dos seguintes: **Oracle**, **Microsoft SQL Server** ou **Microsoft SQL Server Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="73da8-118">The connection type must be one of the following: **Oracle**, **Microsoft SQL Server** or **Microsoft SQL Server Analysis Services**.</span></span>  
  
7.  <span data-ttu-id="73da8-119">Na caixa **Cadeia de conexão** , digite a cadeia de conexão que aponta para o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="73da8-119">In the **Connection string** box, enter the connection string that points to the database.</span></span>  
  
8.  <span data-ttu-id="73da8-120">Selecione o método de conexão que os usuários do Construtor de Relatórios necessitarão usar para se conectar ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="73da8-120">Select the connection method that Report Builder users will need to use to connect to the database.</span></span>  
  
    -   <span data-ttu-id="73da8-121">Autenticação do Windows: Selecione esta opção quando desejar que o sistema operacional autentique os usuários [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73da8-121">Windows Authentication: Select this option when you want the operating system to authenticate [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] users.</span></span> <span data-ttu-id="73da8-122">Esta opção permite [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] usar os recursos de segurança do Windows como a criptografia de senha para autenticar os usuários.</span><span class="sxs-lookup"><span data-stu-id="73da8-122">This option allows [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to use Windows security features, such as password encryption, to authenticate users.</span></span> <span data-ttu-id="73da8-123">É altamente recomendado que você selecione essa opção.</span><span class="sxs-lookup"><span data-stu-id="73da8-123">It is strongly recommended that you select this option.</span></span>  
  
    -   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]<span data-ttu-id="73da8-124">Autenticação: Selecione esta opção quando desejar que os usuários usem uma [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] conta de logon que você criou.</span><span class="sxs-lookup"><span data-stu-id="73da8-124">Authentication: Select this option when you want users to use a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login account that you created.</span></span> <span data-ttu-id="73da8-125">Os usuários devem fornecer um nome de logon e senha válidos [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73da8-125">Users must supply a valid [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login name and password.</span></span>  
  
        > [!CAUTION]  
        >  <span data-ttu-id="73da8-126">Sempre que for possível, use a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="73da8-126">Whenever possible, use Windows Authentication.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
### <a name="to-create-a-report-model-using-report-manager"></a><span data-ttu-id="73da8-127">Para criar um modelo de relatório usando o Gerenciador de Relatórios</span><span class="sxs-lookup"><span data-stu-id="73da8-127">To create a report model using Report Manager</span></span>  
  
1.  <span data-ttu-id="73da8-128">No Gerenciador de Relatórios, selecione a fonte de dados que você deseja usar em seu modelo.</span><span class="sxs-lookup"><span data-stu-id="73da8-128">In Report Manager, select the data source that you want to use for your model.</span></span>  
  
     <span data-ttu-id="73da8-129">A página Propriedades é exibida.</span><span class="sxs-lookup"><span data-stu-id="73da8-129">The Properties page is displayed.</span></span>  
  
2.  <span data-ttu-id="73da8-130">Verifique se você deseja usar as opções especificadas para a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="73da8-130">Verify that you want to use the options specified for the data source.</span></span>  
  
3.  <span data-ttu-id="73da8-131">Clique em **Gerar Modelo**.</span><span class="sxs-lookup"><span data-stu-id="73da8-131">Click **Generate Model**.</span></span>  
  
     <span data-ttu-id="73da8-132">A página Geral é exibida para a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="73da8-132">The General page is displayed for the data source.</span></span>  
  
4.  <span data-ttu-id="73da8-133">Na caixa **Nome** , digite um nome para o modelo de relatório.</span><span class="sxs-lookup"><span data-stu-id="73da8-133">In the **Name** box, enter a name for the report model.</span></span>  
  
5.  <span data-ttu-id="73da8-134">Na caixa **Descrição** , digite uma breve descrição do modelo.</span><span class="sxs-lookup"><span data-stu-id="73da8-134">In the **Description** box, enter a brief description of the model.</span></span>  
  
6.  <span data-ttu-id="73da8-135">Para especificar um novo local para salvar o modelo de relatório, clique em **Alterar Local**.</span><span class="sxs-lookup"><span data-stu-id="73da8-135">To specify a new location to save the report model to, click **Change Location**.</span></span>  
  
     <span data-ttu-id="73da8-136">Por padrão, o modelo de relatório é salvo na página inicial do Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="73da8-136">By default, the report model is saved to Report Manager Home.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="73da8-137">O modelo de relatório é criado e salvo no local por você especificado.</span><span class="sxs-lookup"><span data-stu-id="73da8-137">The report model is created and saved to the location that you specified.</span></span> <span data-ttu-id="73da8-138">Você pode atribuir permissões a este modelo usando o Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="73da8-138">You can assign permissions to this model by using Report Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73da8-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="73da8-139">See Also</span></span>  
 <span data-ttu-id="73da8-140">[Concedendo permissões em um servidor de relatório no modo nativo](security/granting-permissions-on-a-native-mode-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="73da8-140">[Granting Permissions on a Native Mode Report Server](security/granting-permissions-on-a-native-mode-report-server.md) </span></span>  
 <span data-ttu-id="73da8-141">[Conexões de dados, fontes de dados e cadeias de conexão no Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="73da8-141">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="73da8-142">Página Nova Fonte de Dados &#40;Gerenciador de Relatórios&#41;</span><span class="sxs-lookup"><span data-stu-id="73da8-142">New Data Source Page &#40;Report Manager&#41;</span></span>](../../2014/reporting-services/new-data-source-page-report-manager.md)  
  
  
