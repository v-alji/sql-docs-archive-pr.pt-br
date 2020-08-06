---
title: Conectar-se a um banco de dados Microsoft SQL Server (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connsqlserverdb.f1
ms.assetid: 6ebfe029-dbba-4f0d-a556-328e79ef629f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 64267cd65836cf8e6c8d8b26a177de595894b601
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571025"
---
# <a name="connect-to-a-microsoft-sql-server-database-ssas"></a><span data-ttu-id="5dfa3-102">Conectar a um banco de dados Microsoft SQL Server (SSAS)</span><span class="sxs-lookup"><span data-stu-id="5dfa3-102">Connect to a Microsoft SQL Server Database (SSAS)</span></span>
  <span data-ttu-id="5dfa3-103">Esta página do **Assistente de Importação de Tabela** o habilita a especificar as configurações de conexão a um banco de dados do Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5dfa3-103">This page of the **Table Import Wizard** enables you to specify settings to connect to a Microsoft SQL Server database.</span></span> <span data-ttu-id="5dfa3-104">Para acessar o assistente do [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], no menu **Modelo** , clique em **Importar de Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="5dfa3-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="5dfa3-105">Para conectar uma fonte de dados, você deve ter o provedor apropriado instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="5dfa3-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5dfa3-106">As credenciais do usuário atual são usadas na seleção de um banco de dados nesta página.</span><span class="sxs-lookup"><span data-stu-id="5dfa3-106">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="5dfa3-107">Porém, a importação não terá êxito se o usuário especificado na página Informações sobre Representação não tiver privilégios suficientes para ler do banco de dados selecionado.</span><span class="sxs-lookup"><span data-stu-id="5dfa3-107">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="5dfa3-108">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="5dfa3-108">UI element list</span></span>  
 <span data-ttu-id="5dfa3-109">**Nome de conexão amigável**</span><span class="sxs-lookup"><span data-stu-id="5dfa3-109">**Friendly connection name**</span></span>  
 <span data-ttu-id="5dfa3-110">Digite um nome exclusivo para esta conexão de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="5dfa3-110">Type a unique name for this data source connection.</span></span> <span data-ttu-id="5dfa3-111">Esse é um campo obrigatório.</span><span class="sxs-lookup"><span data-stu-id="5dfa3-111">This is a required field.</span></span>  
  
 <span data-ttu-id="5dfa3-112">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="5dfa3-112">**Server name**</span></span>  
 <span data-ttu-id="5dfa3-113">Selecione ou digite o nome ou o endereço IP da instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] à qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="5dfa3-113">Select the name, or type the name or IP address, of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance to connect to.</span></span>  
  
 <span data-ttu-id="5dfa3-114">Você pode usar um ponto (.), (local) ou localhost para indicar o servidor local.</span><span class="sxs-lookup"><span data-stu-id="5dfa3-114">You can use a period (.), (local), or localhost to indicate the local server.</span></span>  
  
 <span data-ttu-id="5dfa3-115">**Usar Autenticação do Windows**</span><span class="sxs-lookup"><span data-stu-id="5dfa3-115">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="5dfa3-116">Especifique se a Autenticação do Windows será usada para estabelecer conexão com uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5dfa3-116">Specify whether Windows Authentication is used to connect to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="5dfa3-117">O modo de Autenticação do Windows habilita um usuário a se conectar por meio de uma conta de usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="5dfa3-117">Windows Authentication mode enables a user to connect by using a Windows user account.</span></span> <span data-ttu-id="5dfa3-118">Sempre que for possível, use a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="5dfa3-118">Whenever possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="5dfa3-119">Quando a Autenticação do Windows é usada, as credenciais do usuário atual são usadas na visualização e filtragem de dados na janela Propriedades de Tabela e no Assistente de Importação.</span><span class="sxs-lookup"><span data-stu-id="5dfa3-119">When Windows Authentication is used, the credentials of the current user are used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="5dfa3-120">Essas credenciais não são usadas para importar ou atualizar dados; em vez disso, utiliza-se as credenciais do Windows especificadas na página Informações sobre Representação.</span><span class="sxs-lookup"><span data-stu-id="5dfa3-120">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation information page are used instead.</span></span>  
  
 <span data-ttu-id="5dfa3-121">**Usar Autenticação do SQL Server**</span><span class="sxs-lookup"><span data-stu-id="5dfa3-121">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="5dfa3-122">Especifique se a Autenticação do SQL Server será usada para estabelecer conexão com uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5dfa3-122">Specify whether SQL Server Authentication is used to connect to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="5dfa3-123">Com a Autenticação do SQL Server, o próprio SQL Server executa a autenticação verificando se foi configurada uma conta de logon do SQL Server e se a senha especificada corresponde a uma senha registrada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="5dfa3-123">With SQL Server Authentication, SQL Server performs the authentication itself by checking to see if a SQL Server login account has been set up and if the specified password matches the one previously recorded.</span></span>  
  
 <span data-ttu-id="5dfa3-124">A Autenticação do SQL Server é usada para construir a cadeia de conexão para a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="5dfa3-124">SQL Server Authentication is used to construct the connection string for the data source.</span></span> <span data-ttu-id="5dfa3-125">Essas credenciais também são usadas na visualização e filtragem de dados na janela Propriedades de Tabela e no Assistente de Importação.</span><span class="sxs-lookup"><span data-stu-id="5dfa3-125">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="5dfa3-126">Essas credenciais não são usadas para importar ou atualizar dados; em vez disso, utiliza-se as credenciais do Windows especificadas na página Informações sobre Representação.</span><span class="sxs-lookup"><span data-stu-id="5dfa3-126">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="5dfa3-127">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="5dfa3-127">**User name**</span></span>  
 <span data-ttu-id="5dfa3-128">Especifique um nome de usuário para a conexão de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="5dfa3-128">Specify a user name for the database connection.</span></span> <span data-ttu-id="5dfa3-129">Esta opção só estará disponível se você tiver optado por conectar-se usando a Autenticação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5dfa3-129">This option is only available if you have selected to connect using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="5dfa3-130">**Senha**</span><span class="sxs-lookup"><span data-stu-id="5dfa3-130">**Password**</span></span>  
 <span data-ttu-id="5dfa3-131">Especifique uma senha para a conexão de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="5dfa3-131">Specify a password for the database connection.</span></span> <span data-ttu-id="5dfa3-132">Esta opção só poderá ser editada se você tiver optado por conectar-se usando a Autenticação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5dfa3-132">This option is only editable if you have selected to connect using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="5dfa3-133">**Salvar minha senha**</span><span class="sxs-lookup"><span data-stu-id="5dfa3-133">**Save my password**</span></span>  
 <span data-ttu-id="5dfa3-134">Especifique se a senha que você inseriu na caixa **Senha** deve ser armazenada.</span><span class="sxs-lookup"><span data-stu-id="5dfa3-134">Specify whether the password you have entered in the **Password** box is stored.</span></span> <span data-ttu-id="5dfa3-135">Esta opção só estará disponível se você tiver optado por conectar-se usando a Autenticação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5dfa3-135">This option is only available if you have selected to connect using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="5dfa3-136">**Nome do banco de dados**</span><span class="sxs-lookup"><span data-stu-id="5dfa3-136">**Database name**</span></span>  
 <span data-ttu-id="5dfa3-137">Selecione um banco de dados da lista de bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="5dfa3-137">Select a database from the list of databases.</span></span>  
  
 <span data-ttu-id="5dfa3-138">**Avançado**</span><span class="sxs-lookup"><span data-stu-id="5dfa3-138">**Advanced**</span></span>  
 <span data-ttu-id="5dfa3-139">Defina as propriedades de conexão adicionais usando a caixa de diálogo **Definir Propriedades Avançadas** .</span><span class="sxs-lookup"><span data-stu-id="5dfa3-139">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="5dfa3-140">Para obter mais informações, consulte [Definir propriedades avançadas &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="5dfa3-140">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="5dfa3-141">**Testar Conexão**</span><span class="sxs-lookup"><span data-stu-id="5dfa3-141">**Test Connection**</span></span>  
 <span data-ttu-id="5dfa3-142">Tente estabelecer uma conexão com a fonte de dados usando as configurações atuais.</span><span class="sxs-lookup"><span data-stu-id="5dfa3-142">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="5dfa3-143">Uma mensagem que indica se a conexão foi bem-sucedida é exibida.</span><span class="sxs-lookup"><span data-stu-id="5dfa3-143">A message is displayed indicating whether the connection was successful.</span></span>  
  
  
