---
title: Conectar-se a um banco de dados DB2 (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.conndb2db.f1
ms.assetid: eeef3697-a4fd-4263-ba7e-f86afa1f46cc
author: minewiskan
ms.author: owend
ms.openlocfilehash: f36a583956c1fe75bb0a6acd827d083a6c7562f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571031"
---
# <a name="connect-to-a-db2-database-ssas"></a><span data-ttu-id="7aea0-102">Conectar a um banco de dados DB2 (SSAS)</span><span class="sxs-lookup"><span data-stu-id="7aea0-102">Connect to a DB2 Database (SSAS)</span></span>
  <span data-ttu-id="7aea0-103">Esta página do **Assistente de Importação de Tabela** permite que você especifique as configurações de conexão a um banco de dados DB2.</span><span class="sxs-lookup"><span data-stu-id="7aea0-103">This page of the **Table Import Wizard** enables you to specify settings to connect to a DB2 database.</span></span> <span data-ttu-id="7aea0-104">Para acessar o assistente do [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], no menu **Modelo** , clique em **Importar de Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="7aea0-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="7aea0-105">Para conectar uma fonte de dados, você deve ter o provedor apropriado instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="7aea0-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7aea0-106">Quando você seleciona um banco de dados nesta página, são usadas as credenciais de usuário especificadas.</span><span class="sxs-lookup"><span data-stu-id="7aea0-106">When selecting a database in this page, the credentials of the user specified are used.</span></span> <span data-ttu-id="7aea0-107">Porém, a importação não terá êxito se o usuário especificado na página Informações sobre Representação não tiver privilégios suficientes para ler do banco de dados selecionado.</span><span class="sxs-lookup"><span data-stu-id="7aea0-107">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="7aea0-108">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="7aea0-108">UI element list</span></span>  
 <span data-ttu-id="7aea0-109">**Nome de conexão amigável**</span><span class="sxs-lookup"><span data-stu-id="7aea0-109">**Friendly connection name**</span></span>  
 <span data-ttu-id="7aea0-110">Digite um nome exclusivo para esta conexão de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="7aea0-110">Type a unique name for this data source connection.</span></span> <span data-ttu-id="7aea0-111">Esse é um campo obrigatório.</span><span class="sxs-lookup"><span data-stu-id="7aea0-111">This is a required field.</span></span>  
  
 <span data-ttu-id="7aea0-112">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="7aea0-112">**Server name**</span></span>  
 <span data-ttu-id="7aea0-113">Digite ou selecione a instância do servidor com a qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="7aea0-113">Type or select the server instance to connect to.</span></span>  
  
 <span data-ttu-id="7aea0-114">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="7aea0-114">**User name**</span></span>  
 <span data-ttu-id="7aea0-115">Especifique um nome de usuário para a conexão de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7aea0-115">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="7aea0-116">Este nome de usuário é usado ao construir a cadeia de conexão para a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="7aea0-116">This user name is used when constructing the connection string for the data source.</span></span> <span data-ttu-id="7aea0-117">Essas credenciais também são usadas na visualização e filtragem de dados na janela Propriedades de Tabela e no Assistente de Importação.</span><span class="sxs-lookup"><span data-stu-id="7aea0-117">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="7aea0-118">Essas credenciais não são usadas para importar ou atualizar dados; em vez disso, utiliza-se as credenciais do Windows especificadas na página Informações sobre Representação.</span><span class="sxs-lookup"><span data-stu-id="7aea0-118">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="7aea0-119">**Senha**</span><span class="sxs-lookup"><span data-stu-id="7aea0-119">**Password**</span></span>  
 <span data-ttu-id="7aea0-120">Especifique uma senha para a conexão de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7aea0-120">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="7aea0-121">**Salvar minha senha**</span><span class="sxs-lookup"><span data-stu-id="7aea0-121">**Save my password**</span></span>  
 <span data-ttu-id="7aea0-122">Especifique se a senha que você inseriu na caixa **Senha** deve ser armazenada.</span><span class="sxs-lookup"><span data-stu-id="7aea0-122">Specify whether the password you have entered in the **Password** box is stored.</span></span>  
  
 <span data-ttu-id="7aea0-123">**Nome do banco de dados**</span><span class="sxs-lookup"><span data-stu-id="7aea0-123">**Database name**</span></span>  
 <span data-ttu-id="7aea0-124">Selecione um banco de dados da lista de bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="7aea0-124">Select a database from the list of databases.</span></span>  
  
 <span data-ttu-id="7aea0-125">**Coleção de Pacotes**</span><span class="sxs-lookup"><span data-stu-id="7aea0-125">**Package Collection**</span></span>  
 <span data-ttu-id="7aea0-126">Especifique o nome da coleção de pacotes DB2.</span><span class="sxs-lookup"><span data-stu-id="7aea0-126">Specify the name of the collection for the DB2 packages.</span></span> <span data-ttu-id="7aea0-127">Um provedor usa pacotes para emitir instruções SQL e chamar procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="7aea0-127">A provider uses packages to issue SQL statements and call stored procedures.</span></span>  
  
 <span data-ttu-id="7aea0-128">**Esquema Padrão**</span><span class="sxs-lookup"><span data-stu-id="7aea0-128">**Default Schema**</span></span>  
 <span data-ttu-id="7aea0-129">Especifique o nome do esquema padrão para o banco de dados selecionado.</span><span class="sxs-lookup"><span data-stu-id="7aea0-129">Specify the name of the default schema for the selected database.</span></span>  
  
 <span data-ttu-id="7aea0-130">**Avançado**</span><span class="sxs-lookup"><span data-stu-id="7aea0-130">**Advanced**</span></span>  
 <span data-ttu-id="7aea0-131">Defina propriedades de conexão adicionais usando a caixa de diálogo **definir propriedades avançadas** .</span><span class="sxs-lookup"><span data-stu-id="7aea0-131">Set additional connection properties by using the **Set Advanced Properties** dialog box..</span></span>  
  
 <span data-ttu-id="7aea0-132">**Testar Conexão**</span><span class="sxs-lookup"><span data-stu-id="7aea0-132">**Test Connection**</span></span>  
 <span data-ttu-id="7aea0-133">Tente estabelecer uma conexão com a fonte de dados usando as configurações atuais.</span><span class="sxs-lookup"><span data-stu-id="7aea0-133">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="7aea0-134">Uma mensagem que indica se a conexão foi bem-sucedida é exibida.</span><span class="sxs-lookup"><span data-stu-id="7aea0-134">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
