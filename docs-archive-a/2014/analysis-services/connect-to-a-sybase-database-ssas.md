---
title: Conectar-se a um banco de dados Sybase (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connsybasedb.f1
ms.assetid: b4ebdc57-8b2a-4950-b489-88360e6c82c5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 111334ca21d04ad27d306fcb27a6d9b8210e26eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571017"
---
# <a name="connect-to-a-sybase-database-ssas"></a><span data-ttu-id="65e8b-102">Conectar a um banco de dados Sybase (SSAS)</span><span class="sxs-lookup"><span data-stu-id="65e8b-102">Connect to a Sybase Database (SSAS)</span></span>
  <span data-ttu-id="65e8b-103">Esta página do **Assistente de Importação de Tabela** o habilita a especificar as configurações de conexão a um banco de dados Sybase.</span><span class="sxs-lookup"><span data-stu-id="65e8b-103">This page of the **Table Import Wizard** enables you to specify settings to connect to an Sybase database.</span></span> <span data-ttu-id="65e8b-104">Para acessar o assistente do [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], no menu **Modelo** , clique em **Importar de Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="65e8b-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="65e8b-105">Para conectar uma fonte de dados, você deve ter o provedor apropriado instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="65e8b-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="65e8b-106">As credenciais do usuário atual são usadas na seleção de um banco de dados nesta página.</span><span class="sxs-lookup"><span data-stu-id="65e8b-106">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="65e8b-107">Porém, a importação não terá êxito se o usuário especificado na página Informações sobre Representação não tiver privilégios suficientes para ler do banco de dados selecionado.</span><span class="sxs-lookup"><span data-stu-id="65e8b-107">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="65e8b-108">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="65e8b-108">UI element list</span></span>  
 <span data-ttu-id="65e8b-109">**Nome de conexão amigável**</span><span class="sxs-lookup"><span data-stu-id="65e8b-109">**Friendly connection name**</span></span>  
 <span data-ttu-id="65e8b-110">Digite um nome exclusivo para esta conexão de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="65e8b-110">Type a unique name for this data source connection.</span></span> <span data-ttu-id="65e8b-111">Esse é um campo obrigatório.</span><span class="sxs-lookup"><span data-stu-id="65e8b-111">This is a required field.</span></span>  
  
 <span data-ttu-id="65e8b-112">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="65e8b-112">**Server name**</span></span>  
 <span data-ttu-id="65e8b-113">Digite ou selecione a instância do servidor com a qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="65e8b-113">Type or select the server instance to connect to.</span></span>  
  
 <span data-ttu-id="65e8b-114">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="65e8b-114">**User name**</span></span>  
 <span data-ttu-id="65e8b-115">Especifique um nome de usuário para a conexão de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="65e8b-115">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="65e8b-116">Este nome de usuário é usado ao construir a cadeia de conexão para a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="65e8b-116">This user name is used when constructing the connection string for the data source.</span></span> <span data-ttu-id="65e8b-117">Essas credenciais também são usadas na visualização e filtragem de dados na janela Propriedades de Tabela e no Assistente de Importação.</span><span class="sxs-lookup"><span data-stu-id="65e8b-117">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="65e8b-118">Essas credenciais não são usadas para importar ou atualizar dados; em vez disso, utiliza-se as credenciais do Windows especificadas na página Informações sobre Representação.</span><span class="sxs-lookup"><span data-stu-id="65e8b-118">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="65e8b-119">**Senha**</span><span class="sxs-lookup"><span data-stu-id="65e8b-119">**Password**</span></span>  
 <span data-ttu-id="65e8b-120">Especifique uma senha para a conexão de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="65e8b-120">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="65e8b-121">**Salvar minha senha**</span><span class="sxs-lookup"><span data-stu-id="65e8b-121">**Save my password**</span></span>  
 <span data-ttu-id="65e8b-122">Especifique se a senha que você inseriu na caixa **Senha** deve ser armazenada.</span><span class="sxs-lookup"><span data-stu-id="65e8b-122">Specify whether the password you have entered in the **Password** box is stored.</span></span>  
  
 <span data-ttu-id="65e8b-123">**Database Name**</span><span class="sxs-lookup"><span data-stu-id="65e8b-123">**Database Name**</span></span>  
 <span data-ttu-id="65e8b-124">Selecione um banco de dados da lista de bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="65e8b-124">Select a database from the list of databases.</span></span>  
  
 <span data-ttu-id="65e8b-125">**Avançado**</span><span class="sxs-lookup"><span data-stu-id="65e8b-125">**Advanced**</span></span>  
 <span data-ttu-id="65e8b-126">Defina as propriedades de conexão adicionais usando a caixa de diálogo **Definir Propriedades Avançadas** .</span><span class="sxs-lookup"><span data-stu-id="65e8b-126">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="65e8b-127">Para obter mais informações, consulte [Definir propriedades avançadas &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="65e8b-127">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="65e8b-128">**Testar Conexão**</span><span class="sxs-lookup"><span data-stu-id="65e8b-128">**Test Connection**</span></span>  
 <span data-ttu-id="65e8b-129">Tente estabelecer uma conexão com a fonte de dados usando as configurações atuais.</span><span class="sxs-lookup"><span data-stu-id="65e8b-129">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="65e8b-130">Uma mensagem que indica se a conexão foi bem-sucedida é exibida.</span><span class="sxs-lookup"><span data-stu-id="65e8b-130">A message is displayed indicating whether the connection is successful.</span></span>  
  
  