---
title: Conectar-se ao Microsoft SQL Server Analysis Services (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connsqlserveras.f1
ms.assetid: 7f3244ee-b690-471c-893d-68e361c2d416
author: minewiskan
ms.author: owend
ms.openlocfilehash: 984979480e3ea54c86c986fa6dd9771aaf879cb1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571002"
---
# <a name="connect-to-microsoft-sql-server-analysis-services-ssas"></a><span data-ttu-id="f757b-102">Conectar ao Microsoft SQL Server Analysis Services (SSAS)</span><span class="sxs-lookup"><span data-stu-id="f757b-102">Connect to Microsoft SQL Server Analysis Services (SSAS)</span></span>
  <span data-ttu-id="f757b-103">Esta página do **Assistente de Importação de Tabela** o habilita a especificar configurações para importar dados de um cubo do Microsoft SQL Server Analysis Services ou de uma pasta de trabalho PowerPivot que esteja hospedada no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f757b-103">This page of the **Table Import Wizard** enables you to specify settings to import data from a Microsoft SQL Server Analysis Services cube or a PowerPivot workbook that is hosted on SharePoint.</span></span> <span data-ttu-id="f757b-104">Para acessar o assistente do [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], no menu **Modelo** , clique em **Importar de Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="f757b-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="f757b-105">Para conectar uma fonte de dados, você deve ter o provedor apropriado instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="f757b-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f757b-106">As credenciais do usuário atual são usadas na seleção de um banco de dados nesta página.</span><span class="sxs-lookup"><span data-stu-id="f757b-106">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="f757b-107">Porém, a importação não terá êxito se o usuário especificado na página Informações sobre Representação não tiver privilégios suficientes para ler do banco de dados selecionado.</span><span class="sxs-lookup"><span data-stu-id="f757b-107">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="f757b-108">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="f757b-108">UI element list</span></span>  
 <span data-ttu-id="f757b-109">**Nome de conexão amigável**</span><span class="sxs-lookup"><span data-stu-id="f757b-109">**Friendly connection name**</span></span>  
 <span data-ttu-id="f757b-110">Digite um nome exclusivo para esta conexão de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="f757b-110">Type a unique name for this data source connection.</span></span> <span data-ttu-id="f757b-111">Esse é um campo obrigatório.</span><span class="sxs-lookup"><span data-stu-id="f757b-111">This is a required field.</span></span>  
  
 <span data-ttu-id="f757b-112">**Nome do Servidor ou Arquivo**</span><span class="sxs-lookup"><span data-stu-id="f757b-112">**Server or File Name**</span></span>  
 <span data-ttu-id="f757b-113">Insira um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="f757b-113">Enter one of the following:</span></span>  
  
-   <span data-ttu-id="f757b-114">Digite o nome ou o endereço IP do servidor do SQL Server Analysis Services ao qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="f757b-114">Type the name or IP address of the SQL Server Analysis Services server to connect to.</span></span>  
  
     <span data-ttu-id="f757b-115">Você pode usar um ponto (.), (local) ou localhost para indicar o servidor local.</span><span class="sxs-lookup"><span data-stu-id="f757b-115">You can use a period (.), (local), or localhost to indicate the local server.</span></span>  
  
-   <span data-ttu-id="f757b-116">Digite a URL de uma pasta de trabalho do PowerPivot publicada no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f757b-116">Type the URL of a PowerPivot workbook that is published to SharePoint.</span></span>  
  
 <span data-ttu-id="f757b-117">**Usar Autenticação do Windows**</span><span class="sxs-lookup"><span data-stu-id="f757b-117">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="f757b-118">Especifique se a Autenticação do Windows será usada para conectar a um servidor do SQL Server Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="f757b-118">Specify whether Windows Authentication is used to connect to a SQL Server Analysis Services server.</span></span>  
  
 <span data-ttu-id="f757b-119">O modo de Autenticação do Windows permite que um usuário se conecte por meio de uma conta de usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="f757b-119">Windows Authentication mode enables a user to connect through a Windows user account.</span></span> <span data-ttu-id="f757b-120">Sempre que for possível, use a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="f757b-120">Whenever possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="f757b-121">Quando a Autenticação do Windows é usada, as credenciais do usuário atual são usadas na visualização e filtragem de dados na janela Propriedades de Tabela e no Assistente de Importação.</span><span class="sxs-lookup"><span data-stu-id="f757b-121">When Windows Authentication is used, the credentials of the current user are used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="f757b-122">Essas credenciais não são usadas para importar ou atualizar dados; em vez disso, utiliza-se as credenciais do Windows especificadas na página Informações sobre Representação.</span><span class="sxs-lookup"><span data-stu-id="f757b-122">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="f757b-123">**Usar Autenticação do SQL Server**</span><span class="sxs-lookup"><span data-stu-id="f757b-123">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="f757b-124">Especifique se a Autenticação do SQL Server será usada para conectar a um servidor do SQL Server Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="f757b-124">Specify whether SQL Server Authentication is used to connect to a SQL Server Analysis Services server.</span></span>  
  
 <span data-ttu-id="f757b-125">Com a Autenticação do SQL Server, o próprio SQL Server executa a autenticação verificando se foi configurada uma conta de logon do SQL Server e se a senha especificada corresponde a uma senha registrada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f757b-125">With SQL Server Authentication, SQL Server performs the authentication itself by checking to see if a SQL Server login account has been set up and if the specified password matches the one previously recorded.</span></span>  
  
 <span data-ttu-id="f757b-126">A Autenticação do SQL Server é usada para construir a cadeia de conexão para a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="f757b-126">SQL Server Authentication is used to construct the connection string for the data source.</span></span> <span data-ttu-id="f757b-127">Essas credenciais também são usadas na visualização e filtragem de dados na janela Propriedades de Tabela e no Assistente de Importação.</span><span class="sxs-lookup"><span data-stu-id="f757b-127">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="f757b-128">Essas credenciais não são usadas para importar ou atualizar dados; em vez disso, utiliza-se as credenciais do Windows especificadas na página Informações sobre Representação.</span><span class="sxs-lookup"><span data-stu-id="f757b-128">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="f757b-129">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="f757b-129">**User name**</span></span>  
 <span data-ttu-id="f757b-130">Especifique um nome de usuário para a conexão de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f757b-130">Specify a user name for the database connection.</span></span> <span data-ttu-id="f757b-131">Essa opção estará disponível somente se você decidiu conectar-se usando a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="f757b-131">This option is only available if you have selected to connect using Windows Authentication.</span></span>  
  
 <span data-ttu-id="f757b-132">**Senha**</span><span class="sxs-lookup"><span data-stu-id="f757b-132">**Password**</span></span>  
 <span data-ttu-id="f757b-133">Especifique uma senha para a conexão de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f757b-133">Specify a password for the database connection.</span></span> <span data-ttu-id="f757b-134">Esta opção só poderá ser editada se você tiver optado por conectar-se usando a Autenticação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f757b-134">This option is only editable if you have selected to connect using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="f757b-135">**Salvar minha senha**</span><span class="sxs-lookup"><span data-stu-id="f757b-135">**Save my password**</span></span>  
 <span data-ttu-id="f757b-136">Especifique se a senha que você inseriu na caixa **Senha** deve ser armazenada.</span><span class="sxs-lookup"><span data-stu-id="f757b-136">Specify whether the password you have entered in the **Password** box is stored.</span></span> <span data-ttu-id="f757b-137">Esta opção só estará disponível se você tiver optado por conectar-se usando a Autenticação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f757b-137">This option is only available if you have selected to connect using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="f757b-138">**Nome do banco de dados**</span><span class="sxs-lookup"><span data-stu-id="f757b-138">**Database name**</span></span>  
 <span data-ttu-id="f757b-139">Selecione um banco de dados da lista de bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="f757b-139">Select a database from the list of databases.</span></span>  
  
 <span data-ttu-id="f757b-140">**Avançado**</span><span class="sxs-lookup"><span data-stu-id="f757b-140">**Advanced**</span></span>  
 <span data-ttu-id="f757b-141">Defina as propriedades de conexão adicionais usando a caixa de diálogo **Definir Propriedades Avançadas** .</span><span class="sxs-lookup"><span data-stu-id="f757b-141">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="f757b-142">Para obter mais informações, consulte [Definir propriedades avançadas &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="f757b-142">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="f757b-143">**Testar Conexão**</span><span class="sxs-lookup"><span data-stu-id="f757b-143">**Test Connection**</span></span>  
 <span data-ttu-id="f757b-144">Tente estabelecer uma conexão com a fonte de dados usando as configurações atuais.</span><span class="sxs-lookup"><span data-stu-id="f757b-144">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="f757b-145">Uma mensagem que indica se a conexão foi bem-sucedida é exibida.</span><span class="sxs-lookup"><span data-stu-id="f757b-145">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
