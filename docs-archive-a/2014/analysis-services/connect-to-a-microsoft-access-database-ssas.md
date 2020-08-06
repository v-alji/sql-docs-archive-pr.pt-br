---
title: Conectar-se a um banco de dados do Microsoft Access (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connaccessdb.f1
ms.assetid: 9fa81839-dd8b-41d3-915e-c774a707ed53
author: minewiskan
ms.author: owend
ms.openlocfilehash: fbb180a754b6bc276d588997117eb84fd1a5a873
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571026"
---
# <a name="connect-to-a-microsoft-access-database-ssas"></a><span data-ttu-id="66176-102">Conectar a um banco de dados Microsoft Access (SSAS)</span><span class="sxs-lookup"><span data-stu-id="66176-102">Connect to a Microsoft Access Database (SSAS)</span></span>
  <span data-ttu-id="66176-103">Esta página do **Assistente de Importação de Tabela** o habilita a especificar as configurações de conexão para um banco de dados do Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="66176-103">This page of the **Table Import Wizard** enables you to specify settings to connect to a Microsoft Access database.</span></span> <span data-ttu-id="66176-104">Para acessar o assistente do [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], no menu **Modelo** , clique em **Importar de Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="66176-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="66176-105">Para conectar um banco de dados do Microsoft Access, você deve ter o provedor ACE apropriado instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="66176-105">To connect to a Microsoft Access database, you must have the appropriate ACE provider installed on your computer.</span></span> <span data-ttu-id="66176-106">Para obter mais informações, consulte [Fontes de dados com suporte &#40;SSAS tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="66176-106">For more information, see [Data Sources Supported &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="66176-107">As credenciais do usuário atual são usadas na seleção de um arquivo nesta página.</span><span class="sxs-lookup"><span data-stu-id="66176-107">The credentials of the current user are used when selecting a file in this page.</span></span> <span data-ttu-id="66176-108">Porém, a importação não terá êxito se o usuário especificado na página Informações sobre Representação não tiver privilégios suficientes para ler do arquivo selecionado.</span><span class="sxs-lookup"><span data-stu-id="66176-108">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected file.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="66176-109">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="66176-109">UI element list</span></span>  
 <span data-ttu-id="66176-110">**Nome de conexão amigável**</span><span class="sxs-lookup"><span data-stu-id="66176-110">**Friendly connection name**</span></span>  
 <span data-ttu-id="66176-111">Digite um nome exclusivo para esta conexão de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="66176-111">Type a unique name for this data source connection.</span></span> <span data-ttu-id="66176-112">Esse é um campo obrigatório.</span><span class="sxs-lookup"><span data-stu-id="66176-112">This is a required field.</span></span>  
  
 <span data-ttu-id="66176-113">**Nome do banco de dados**</span><span class="sxs-lookup"><span data-stu-id="66176-113">**Database name**</span></span>  
 <span data-ttu-id="66176-114">Especifique o caminho completo para um arquivo de banco de dados do Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="66176-114">Specify the full path for a Microsoft Access database file.</span></span>  
  
 <span data-ttu-id="66176-115">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="66176-115">**Browse**</span></span>  
 <span data-ttu-id="66176-116">Navegue até um local onde um arquivo de banco de dados do Microsoft Access esteja disponível.</span><span class="sxs-lookup"><span data-stu-id="66176-116">Navigate to a location where a Microsoft Access database file is available.</span></span>  
  
 <span data-ttu-id="66176-117">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="66176-117">**User name**</span></span>  
 <span data-ttu-id="66176-118">Especifique um nome de usuário para a conexão de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="66176-118">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="66176-119">**Senha**</span><span class="sxs-lookup"><span data-stu-id="66176-119">**Password**</span></span>  
 <span data-ttu-id="66176-120">Especifique uma senha para a conexão de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="66176-120">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="66176-121">**Salvar minha senha**</span><span class="sxs-lookup"><span data-stu-id="66176-121">**Save my password**</span></span>  
 <span data-ttu-id="66176-122">Especifique se a senha que você inseriu na caixa **Senha** deve ser armazenada.</span><span class="sxs-lookup"><span data-stu-id="66176-122">Specify whether the password you have entered in the **Password** box is stored.</span></span>  
  
 <span data-ttu-id="66176-123">**Avançado**</span><span class="sxs-lookup"><span data-stu-id="66176-123">**Advanced**</span></span>  
 <span data-ttu-id="66176-124">Defina as propriedades de conexão adicionais usando a caixa de diálogo **Definir Propriedades Avançadas** .</span><span class="sxs-lookup"><span data-stu-id="66176-124">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span>  
  
 <span data-ttu-id="66176-125">**Testar Conexão**</span><span class="sxs-lookup"><span data-stu-id="66176-125">**Test Connection**</span></span>  
 <span data-ttu-id="66176-126">Tente estabelecer uma conexão com a fonte de dados usando as configurações atuais.</span><span class="sxs-lookup"><span data-stu-id="66176-126">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="66176-127">Uma mensagem que indica se a conexão foi bem-sucedida é exibida.</span><span class="sxs-lookup"><span data-stu-id="66176-127">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
