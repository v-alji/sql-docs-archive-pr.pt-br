---
title: Editor de destino SQL (página Gerenciador de conexões) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sqlserverdestadapter.connection.f1
helpviewer_keywords:
- SQL Server Destination Editor
ms.assetid: 423e1654-54af-47c6-ab6f-98670534557d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4f3a552968cb297de337e1f0c406b444d95dc5a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572598"
---
# <a name="sql-destination-editor-connection-manager-page"></a><span data-ttu-id="eb03b-102">Editor do Destino SQL (página Gerenciador de Conexões)</span><span class="sxs-lookup"><span data-stu-id="eb03b-102">SQL Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="eb03b-103">Use a página **Gerenciador de Conexões** da caixa de diálogo **Editor de Destinos SQL** para especificar informações de fonte de dados e visualizar os resultados.</span><span class="sxs-lookup"><span data-stu-id="eb03b-103">Use the **Connection Manager** page of the **SQL Destination Editor** dialog box to specify data source information, and to preview the results.</span></span> <span data-ttu-id="eb03b-104">O [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] destino carrega dados em tabelas ou exibições em um banco de dados [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="eb03b-104">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] destination loads data into tables or views in a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="eb03b-105">Para obter mais informações sobre destino do SQL Server, consulte [SQL Server Destination](data-flow/sql-server-destination.md).</span><span class="sxs-lookup"><span data-stu-id="eb03b-105">To learn more about the SQL Server destination, see [SQL Server Destination](data-flow/sql-server-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="eb03b-106">Opções</span><span class="sxs-lookup"><span data-stu-id="eb03b-106">Options</span></span>  
 <span data-ttu-id="eb03b-107">**Gerenciador de conexões OLE DB**</span><span class="sxs-lookup"><span data-stu-id="eb03b-107">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="eb03b-108">Selecione uma conexão existente na lista ou crie uma nova conexão clicando em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="eb03b-108">Select an existing connection from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="eb03b-109">**Novo**</span><span class="sxs-lookup"><span data-stu-id="eb03b-109">**New**</span></span>  
 <span data-ttu-id="eb03b-110">Crie uma nova conexão usando a caixa de diálogo **Configurar Gerenciador de Conexões OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="eb03b-110">Create a new connection by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="eb03b-111">**Use uma tabela ou exibição**</span><span class="sxs-lookup"><span data-stu-id="eb03b-111">**Use a table or view**</span></span>  
 <span data-ttu-id="eb03b-112">Selecione uma tabela ou exibição existente na lista ou crie uma nova conexão clicando em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="eb03b-112">Select an existing table or view from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="eb03b-113">**Novo**</span><span class="sxs-lookup"><span data-stu-id="eb03b-113">**New**</span></span>  
 <span data-ttu-id="eb03b-114">Crie uma nova tabela usando a caixa de diálogo **Criar Tabela** .</span><span class="sxs-lookup"><span data-stu-id="eb03b-114">Create a new table by using the **Create Table** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eb03b-115">Ao clicar em **Novo**, o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] gera uma instrução CREATE TABLE padrão com base na fonte de dados conectada.</span><span class="sxs-lookup"><span data-stu-id="eb03b-115">When you click **New**, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] generates a default CREATE TABLE statement based on the connected data source.</span></span> <span data-ttu-id="eb03b-116">A instrução CREATE TABLE padrão não incluirá o atributo FILESTREAM mesmo que a tabela de origem inclua uma coluna com o atributo FILESTREAM declarado.</span><span class="sxs-lookup"><span data-stu-id="eb03b-116">This default CREATE TABLE statement will not include the FILESTREAM attribute even if the source table includes a column with the FILESTREAM attribute declared.</span></span> <span data-ttu-id="eb03b-117">Para executar um componente [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] com o atributo FILESTREAM, implemente primeiro o armazenamento FILESTREAM no banco de dados de destino.</span><span class="sxs-lookup"><span data-stu-id="eb03b-117">To run an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] component with the FILESTREAM attribute, first implement FILESTREAM storage on the destination database.</span></span> <span data-ttu-id="eb03b-118">Em seguida, adicione o atributo FILESTREAM à instrução CREATE TABLE na caixa de diálogo **Criar Tabela** .</span><span class="sxs-lookup"><span data-stu-id="eb03b-118">Then, add the FILESTREAM attribute to the CREATE TABLE statement in the **Create Table** dialog box.</span></span> <span data-ttu-id="eb03b-119">Para obter mais informações, consulte [Dados de blob &#40;objeto binário grande&#41; &#40;SQL Server&#41;](../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="eb03b-119">For more information, see [Binary Large Object &#40;Blob&#41; Data &#40;SQL Server&#41;](../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="eb03b-120">**Visualização**</span><span class="sxs-lookup"><span data-stu-id="eb03b-120">**Preview**</span></span>  
 <span data-ttu-id="eb03b-121">Visualize os resultados usando a caixa de diálogo **Visualizar Resultados da Consulta** .</span><span class="sxs-lookup"><span data-stu-id="eb03b-121">Preview results by using the **Preview Query Results** dialog box.</span></span> <span data-ttu-id="eb03b-122">A visualização pode exibir até 200 linhas.</span><span class="sxs-lookup"><span data-stu-id="eb03b-122">Preview can display up to 200 rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb03b-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="eb03b-123">See Also</span></span>  
 <span data-ttu-id="eb03b-124">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="eb03b-124">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="eb03b-125">[Página Mapeamentos de &#40;do editor de destinos SQL&#41;](../../2014/integration-services/sql-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="eb03b-125">[SQL Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/sql-destination-editor-mappings-page.md) </span></span>  
 <span data-ttu-id="eb03b-126">[Editor de destinos SQL &#40;página avançado&#41;](../../2014/integration-services/sql-destination-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="eb03b-126">[SQL Destination Editor &#40;Advanced Page&#41;](../../2014/integration-services/sql-destination-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="eb03b-127">Carregar dados em massa por meio do destino do SQL Server</span><span class="sxs-lookup"><span data-stu-id="eb03b-127">Bulk Load Data by Using the SQL Server Destination</span></span>](data-flow/bulk-load-data-by-using-the-sql-server-destination.md)  
  
  
