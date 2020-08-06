---
title: Recuperar e compreender os dados de alterações | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],retrieving data
ms.assetid: af366697-6942-42bb-aea5-18fdef018965
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 62f60bf4a79c39b4f0cb7d1ba8fb3f52680a1f11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683140"
---
# <a name="retrieve-and-understand-the-change-data"></a><span data-ttu-id="294c4-102">Recuperar e compreender os dados de alteração</span><span class="sxs-lookup"><span data-stu-id="294c4-102">Retrieve and Understand the Change Data</span></span>
  <span data-ttu-id="294c4-103">No fluxo de dados de um pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que executa uma carga incremental de dados de alteração, a primeira tarefa é executar a consulta que recupera os dados de alteração.</span><span class="sxs-lookup"><span data-stu-id="294c4-103">In the data flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the first task is to run the query that retrieves the change data.</span></span> <span data-ttu-id="294c4-104">Você executa esta consulta dentro de um componente de origem em uma tarefa Fluxo de Dados.</span><span class="sxs-lookup"><span data-stu-id="294c4-104">You execute this query inside a source component in a Data Flow task.</span></span> <span data-ttu-id="294c4-105">As transformações downstream e os destinos podem ser usados para aplicar os dados de alteração em seu destino.</span><span class="sxs-lookup"><span data-stu-id="294c4-105">You can then use downstream transformations and destinations to apply the change data to your destination.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="294c4-106">A criação de uma consulta que contém uma função com valor de tabela é a terceira etapa no processo de criação de um pacote que execute uma carga incremental dos dados de alteração.</span><span class="sxs-lookup"><span data-stu-id="294c4-106">The creation of a query that contains a table-valued function is the third step in the process of creating a package that performs an incremental load of change data.</span></span> <span data-ttu-id="294c4-107">Para obter mais informações sobre esta consulta, veja [Criar a função para recuperar os dados de alteração](create-the-function-to-retrieve-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="294c4-107">For more information about this query, see, [Create the Function to Retrieve the Change Data](create-the-function-to-retrieve-the-change-data.md).</span></span> <span data-ttu-id="294c4-108">Para obter uma descrição do processo geral para criar um pacote que realiza uma carga incremental de dados de alteração, consulte [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="294c4-108">For a description of the overall process for creating a package that performs an incremental load of change data, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="adding-the-data-flow-task"></a><span data-ttu-id="294c4-109">Adicionando a tarefa Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="294c4-109">Adding the Data Flow Task</span></span>  
 <span data-ttu-id="294c4-110">No fluxo de dados do pacote, você recupera os dados de alteração, separa as linhas com base no tipo de alteração ocorrida e aplica as alterações ao destino.</span><span class="sxs-lookup"><span data-stu-id="294c4-110">In the data flow of the package, you retrieve the change data, separate the rows based on the type of change that occurred, and then apply the changes to the destination.</span></span>  
  
#### <a name="to-add-a-data-flow-task-to-the-package"></a><span data-ttu-id="294c4-111">Adicionar uma tarefa Fluxo de Dados ao pacote</span><span class="sxs-lookup"><span data-stu-id="294c4-111">To add a Data Flow task to the package</span></span>  
  
1.  <span data-ttu-id="294c4-112">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], na guia **Fluxo de Controle** , adicione uma tarefa Fluxo de Dados.</span><span class="sxs-lookup"><span data-stu-id="294c4-112">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], on the **Control Flow** tab, add a Data Flow task.</span></span>  
  
2.  <span data-ttu-id="294c4-113">Conecte a tarefa de precedência que preparou a cadeia de caracteres de consulta à tarefa Fluxo de Dados.</span><span class="sxs-lookup"><span data-stu-id="294c4-113">Connect the preceding task that prepared the query string to the Data Flow task.</span></span>  
  
## <a name="configuring-the-source-component-to-query-for-changes"></a><span data-ttu-id="294c4-114">Configurando o componente de origem para a consulta de alterações</span><span class="sxs-lookup"><span data-stu-id="294c4-114">Configuring the Source Component to Query for Changes</span></span>  
 <span data-ttu-id="294c4-115">O componente de origem usa a cadeia de caracteres de consulta que foi preparada e armazenada em uma variável para chamar a função com valor de tabela que recupera os dados alterados.</span><span class="sxs-lookup"><span data-stu-id="294c4-115">The source component uses the query string that was prepared and stored in a variable to calls the table-valued function that retrieves the changed data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="294c4-116">Para obter mais informações sobre a cadeia de caracteres de consulta que foi preparada e armazenada em uma variável, consulte [Preparar para consultar os dados de alteração](prepare-to-query-for-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="294c4-116">For more information about the query string that was prepared and stored in a variable, see [Prepare to Query for the Change Data](prepare-to-query-for-the-change-data.md).</span></span> <span data-ttu-id="294c4-117">Para obter mais informações sobre a função com valor de tabela que recupera os dados de alteração, consulte [Criar a função para recuperar os dados de alteração](create-the-function-to-retrieve-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="294c4-117">For more information about the table-valued function that retrieves the change data, see [Create the Function to Retrieve the Change Data](create-the-function-to-retrieve-the-change-data.md).</span></span>  
  
#### <a name="to-configure-an-ole-db-source-to-retrieve-the-change-data"></a><span data-ttu-id="294c4-118">Configurar uma fonte OLE DB para recuperar os dados de alteração</span><span class="sxs-lookup"><span data-stu-id="294c4-118">To configure an OLE DB source to retrieve the change data</span></span>  
  
1.  <span data-ttu-id="294c4-119">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], na guia **Fluxo de Dados** , adicione uma fonte OLE DB.</span><span class="sxs-lookup"><span data-stu-id="294c4-119">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], on the **Data Flow** tab, add an OLE DB source.</span></span>  
  
2.  <span data-ttu-id="294c4-120">No **Editor de Origem de OLE DB**, na página **Gerenciador de Conexões** , selecione as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="294c4-120">In the **OLE DB Source Editor**, on the **Connection Manager** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="294c4-121">Configure uma conexão válida com o banco de dados fonte.</span><span class="sxs-lookup"><span data-stu-id="294c4-121">Configure a valid connection to the source database.</span></span>  
  
    2.  <span data-ttu-id="294c4-122">Para **Modo de acesso a dados**, selecione o **Comando SQL a partir da variável**.</span><span class="sxs-lookup"><span data-stu-id="294c4-122">For **Data access mode**, select **SQL command from variable**.</span></span>  
  
    3.  <span data-ttu-id="294c4-123">Para **Nome da variável**, selecione **User::SqlDataQuery**.</span><span class="sxs-lookup"><span data-stu-id="294c4-123">For **Variable name**, select **User::SqlDataQuery**.</span></span>  
  
3.  <span data-ttu-id="294c4-124">No **Editor de Origem de OLE DB**, na página **Colunas** , verifique se todas as colunas estão mapeadas para as colunas de saída.</span><span class="sxs-lookup"><span data-stu-id="294c4-124">In the **OLE DB Source Editor**, on the **Columns** page, make sure that all the columns that you want are mapped to output columns.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="294c4-125">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="294c4-125">Next Step</span></span>  
 <span data-ttu-id="294c4-126">Depois de configurar uma fonte de OLE DB para recuperar os dados de alteração, a próxima etapa será iniciar a criação do fluxo de dados no pacote.</span><span class="sxs-lookup"><span data-stu-id="294c4-126">After you have configured an OLE DB source to retrieve the change data, the next step is to start designing the data flow in the package.</span></span>  
  
 <span data-ttu-id="294c4-127">**Próximo tópico:** [Processar inserções, atualizações e exclusões](process-inserts-updates-and-deletes.md)</span><span class="sxs-lookup"><span data-stu-id="294c4-127">**Next topic:** [Process Inserts, Updates, and Deletes](process-inserts-updates-and-deletes.md)</span></span>  
  
  
