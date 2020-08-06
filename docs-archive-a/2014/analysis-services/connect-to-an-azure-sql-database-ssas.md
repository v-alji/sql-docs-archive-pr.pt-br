---
title: Conectar-se a um banco de dados SQL do Azure (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connsqlazure.f1
ms.assetid: 4e0344e9-1822-4698-ad22-05f1f341ced7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 91ae6f0f5ab95d3013b6348bd43ddb746fff1c22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571015"
---
# <a name="connect-to-an-azure-sql-database-ssas"></a><span data-ttu-id="eb9ba-102">Conectar a um Banco de Dados SQL do Azure (SSAS)</span><span class="sxs-lookup"><span data-stu-id="eb9ba-102">Connect to an Azure SQL Database (SSAS)</span></span>
  <span data-ttu-id="eb9ba-103">Esta página do **Assistente de Importação de Tabela** permite que você se conecte a um [!INCLUDE[ssSDSfull](../includes/sssdsfull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb9ba-103">This page of the **Table Import Wizard** enables you to connect to a [!INCLUDE[ssSDSfull](../includes/sssdsfull-md.md)].</span></span> <span data-ttu-id="eb9ba-104">Para acessar o assistente do [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], no menu **Modelo** , clique em **Importar de Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="eb9ba-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eb9ba-105">Se você estiver se conectando a um conjunto de dados do Azure DataMarket, consulte [Conectar-se a um relatório ou feed de dados &#40;SSAS&#41](connect-to-a-report-or-data-feed-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="eb9ba-105">If you are connecting to an Azure DataMarket dataset, see [Connect to a Report or Data Feed &#40;SSAS&#41;](connect-to-a-report-or-data-feed-ssas.md).</span></span>  
  
 <span data-ttu-id="eb9ba-106">O [!INCLUDE[ssSDS](../includes/sssds-md.md)] é um banco de dados hospedado, relacional, a que você se conecta usando a Autenticação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="eb9ba-106">The [!INCLUDE[ssSDS](../includes/sssds-md.md)] is a hosted, relational database that you connect to by using SQL Server Authentication.</span></span> <span data-ttu-id="eb9ba-107">Para obter mais informações sobre o [!INCLUDE[ssSDS](../includes/sssds-md.md)], consulte o site [Banco de dados SQL](https://go.microsoft.com/fwlink/?LinkID=157856).</span><span class="sxs-lookup"><span data-stu-id="eb9ba-107">For more information about [!INCLUDE[ssSDS](../includes/sssds-md.md)], see the web site [SQL Database](https://go.microsoft.com/fwlink/?LinkID=157856).</span></span> <span data-ttu-id="eb9ba-108">Para conectar uma fonte de dados, você deve ter o provedor apropriado instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="eb9ba-108">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eb9ba-109">As credenciais do usuário atual são usadas na seleção de um banco de dados nesta página.</span><span class="sxs-lookup"><span data-stu-id="eb9ba-109">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="eb9ba-110">Porém, a importação não terá êxito se o usuário especificado na página Informações sobre Representação não tiver privilégios suficientes para ler do banco de dados selecionado.</span><span class="sxs-lookup"><span data-stu-id="eb9ba-110">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="eb9ba-111">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="eb9ba-111">UI element list</span></span>  
 <span data-ttu-id="eb9ba-112">**Nome de conexão amigável**</span><span class="sxs-lookup"><span data-stu-id="eb9ba-112">**Friendly connection name**</span></span>  
 <span data-ttu-id="eb9ba-113">Digite um nome exclusivo para esta conexão de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="eb9ba-113">Type a unique name for this data source connection.</span></span> <span data-ttu-id="eb9ba-114">Esse é um campo obrigatório.</span><span class="sxs-lookup"><span data-stu-id="eb9ba-114">This is a required field.</span></span>  
  
 <span data-ttu-id="eb9ba-115">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="eb9ba-115">**Server name**</span></span>  
 <span data-ttu-id="eb9ba-116">Digite o nome ou o endereço IP do servidor com o qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="eb9ba-116">Type the name, or IP address, of the server to connect to.</span></span>  
  
 <span data-ttu-id="eb9ba-117">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="eb9ba-117">**User name**</span></span>  
 <span data-ttu-id="eb9ba-118">Especifique um nome de usuário para a conexão de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="eb9ba-118">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="eb9ba-119">Este nome de usuário é usado ao construir a cadeia de conexão para a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="eb9ba-119">This user name is used when constructing the connection string for the data source.</span></span> <span data-ttu-id="eb9ba-120">Essas credenciais também são usadas na visualização e filtragem de dados na janela Propriedades de Tabela e no Assistente de Importação.</span><span class="sxs-lookup"><span data-stu-id="eb9ba-120">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="eb9ba-121">Essas credenciais não são usadas para importar ou atualizar dados; em vez disso, utiliza-se as credenciais do Windows especificadas na página Informações sobre Representação.</span><span class="sxs-lookup"><span data-stu-id="eb9ba-121">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="eb9ba-122">**Senha**</span><span class="sxs-lookup"><span data-stu-id="eb9ba-122">**Password**</span></span>  
 <span data-ttu-id="eb9ba-123">Especifique uma senha para a conexão de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="eb9ba-123">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="eb9ba-124">**Salvar minha senha**</span><span class="sxs-lookup"><span data-stu-id="eb9ba-124">**Save my password**</span></span>  
 <span data-ttu-id="eb9ba-125">Especifique se a senha que você inseriu na caixa **Senha** deve ser armazenada.</span><span class="sxs-lookup"><span data-stu-id="eb9ba-125">Specify whether the password you have entered in the **Password** box is stored.</span></span>  
  
 <span data-ttu-id="eb9ba-126">**Nome do banco de dados**</span><span class="sxs-lookup"><span data-stu-id="eb9ba-126">**Database name**</span></span>  
 <span data-ttu-id="eb9ba-127">Selecione um banco de dados da lista de bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="eb9ba-127">Select a database from the list of databases.</span></span>  
  
 <span data-ttu-id="eb9ba-128">**Avançado**</span><span class="sxs-lookup"><span data-stu-id="eb9ba-128">**Advanced**</span></span>  
 <span data-ttu-id="eb9ba-129">Defina as propriedades de conexão adicionais usando a caixa de diálogo **Definir Propriedades Avançadas** .</span><span class="sxs-lookup"><span data-stu-id="eb9ba-129">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="eb9ba-130">Para obter mais informações, consulte [Definir propriedades avançadas &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="eb9ba-130">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="eb9ba-131">**Testar Conexão**</span><span class="sxs-lookup"><span data-stu-id="eb9ba-131">**Test Connection**</span></span>  
 <span data-ttu-id="eb9ba-132">Tente estabelecer uma conexão com a fonte de dados usando as configurações atuais.</span><span class="sxs-lookup"><span data-stu-id="eb9ba-132">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="eb9ba-133">Uma mensagem que indica se a conexão foi bem-sucedida é exibida.</span><span class="sxs-lookup"><span data-stu-id="eb9ba-133">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
