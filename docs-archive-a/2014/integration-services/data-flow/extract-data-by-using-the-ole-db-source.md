---
title: Extrair dados por meio da origem OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- extracting data [Integration Services]
- sources [Integration Services], OLE DB
- OLE DB source [Integration Services]
ms.assetid: 4ca6eeb5-b60e-4b81-86dd-0674be8ae8d8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 352d62cc66e3f17fb10839086e7ee9c5307f1a17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685861"
---
# <a name="extract-data-by-using-the-ole-db-source"></a><span data-ttu-id="cdd62-102">Extrair dados por meio da origem OLE DB</span><span class="sxs-lookup"><span data-stu-id="cdd62-102">Extract Data by Using the OLE DB Source</span></span>
  <span data-ttu-id="cdd62-103">Para adicionar e configurar uma origem OLE DB, o pacote já deve incluir pelo menos uma tarefa de Fluxo de Dados.</span><span class="sxs-lookup"><span data-stu-id="cdd62-103">To add and configure an OLE DB source, the package must already include at least one Data Flow task.</span></span>  
  
### <a name="to-extract-data-using-an-ole-db-source"></a><span data-ttu-id="cdd62-104">Para extrair dados usando uma Origem OLE DB</span><span class="sxs-lookup"><span data-stu-id="cdd62-104">To extract data using an OLE DB Source</span></span>  
  
1.  <span data-ttu-id="cdd62-105">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="cdd62-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="cdd62-106">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="cdd62-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="cdd62-107">Clique na guia **Fluxo de Dados** e, na **Caixa de Ferramentas**, arraste a fonte OLE DB para a superfície de design.</span><span class="sxs-lookup"><span data-stu-id="cdd62-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the OLE DB source to the design surface.</span></span>  
  
4.  <span data-ttu-id="cdd62-108">Clique duas vezes na origem OLE DB.</span><span class="sxs-lookup"><span data-stu-id="cdd62-108">Double-click the OLE DB source.</span></span>  
  
5.  <span data-ttu-id="cdd62-109">Na caixa de diálogo **Editor de Origem OLE DB** , na página **Gerenciador de Conexões** , selecione um gerenciador de conexões OLE DB existente ou clique em **Novo** para criar um gerenciador de conexões novo.</span><span class="sxs-lookup"><span data-stu-id="cdd62-109">In the **OLE DB Source Editor** dialog box, on the **Connection Manager** page, select an existing OLE DB connection manager or click **New** to create a new connection manager.</span></span> <span data-ttu-id="cdd62-110">Para obter mais informações, consulte [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="cdd62-110">For more information, see [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span></span>  
  
6.  <span data-ttu-id="cdd62-111">Selecione o método de acesso de dados:</span><span class="sxs-lookup"><span data-stu-id="cdd62-111">Select the data access method:</span></span>  
  
    -   <span data-ttu-id="cdd62-112">**Tabela ou exibição** Selecione uma tabela ou uma exibição no banco de dados com a qual o gerenciador de conexões OLE DB se conecta.</span><span class="sxs-lookup"><span data-stu-id="cdd62-112">**Table or view** Select a table or view in the database to which the OLE DB connection manager connects.</span></span>  
  
    -   <span data-ttu-id="cdd62-113">**Variável de nome da tabela ou exibição** Selecione a variável definida pelo usuário que contém o nome da tabela ou da exibição no banco de dados com a qual o gerenciador de conexões OLE DB se conecta.</span><span class="sxs-lookup"><span data-stu-id="cdd62-113">**Table name or view name variable** Select the user-defined variable that contains the name of a table or view in the database to which the OLE DB connection manager connects.</span></span>  
  
    -   <span data-ttu-id="cdd62-114">**Comando SQL** Digite um comando SQL ou clique em **Construir Consulta** para escrever um comando SQL usando o **Construtor de Consultas**.</span><span class="sxs-lookup"><span data-stu-id="cdd62-114">**SQL command** Type an SQL command or click **Build Query** to write an SQL command using the **Query Builder**.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="cdd62-115">O comando pode incluir parâmetros.</span><span class="sxs-lookup"><span data-stu-id="cdd62-115">The command can include parameters.</span></span> <span data-ttu-id="cdd62-116">Para obter mais informações, consulte [Mapear parâmetros de consulta para variáveis em um componente de fluxo de dados](map-query-parameters-to-variables-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="cdd62-116">For more information, see [Map Query Parameters to Variables in a Data Flow Component](map-query-parameters-to-variables-in-a-data-flow-component.md).</span></span>  
  
    -   <span data-ttu-id="cdd62-117">**Comando SQL da variável** Selecione a variável definida pelo usuário que contém o comando SQL.</span><span class="sxs-lookup"><span data-stu-id="cdd62-117">**SQL command from variable** Select the user-defined variable that contains the SQL command.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="cdd62-118">As variáveis devem ser definidas no escopo da mesma tarefa Fluxo de Dados que contém a origem OLE DB ou no escopo do mesmo pacote, além disso, a variável deve ter um tipo de dados de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="cdd62-118">The variables must be defined in the scope of the same Data Flow task that contains the OLE DB source, or in the scope of the same package; additionally, the variable must have a string data type.</span></span>  
  
7.  <span data-ttu-id="cdd62-119">Para atualizar o mapeamento entre colunas externas e de saída, clique em **Colunas** e selecione colunas diferentes na lista **Coluna Externa** .</span><span class="sxs-lookup"><span data-stu-id="cdd62-119">To update the mapping between external and output columns, click **Columns** and select different columns in the **External Column** list.</span></span>  
  
8.  <span data-ttu-id="cdd62-120">Como opção, atualize os nomes de colunas de saída editando valores na lista **Coluna de Saída** .</span><span class="sxs-lookup"><span data-stu-id="cdd62-120">Optionally, update the names of output columns by editing values in the **Output Column** list.</span></span>  
  
9. <span data-ttu-id="cdd62-121">Para configurar a saída de erro, clique em **Saída de Erro**.</span><span class="sxs-lookup"><span data-stu-id="cdd62-121">To configure the error output, click **Error Output**.</span></span> <span data-ttu-id="cdd62-122">Para obter mais informações, consulte [Configurar uma saída de erro em um componente de fluxo de dados](../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="cdd62-122">For more information, see [Configure an Error Output in a Data Flow Component](../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
10. <span data-ttu-id="cdd62-123">É possível clicar em **Visualizar** para exibir até 200 linhas dos dados extraídos pela origem OLE DB.</span><span class="sxs-lookup"><span data-stu-id="cdd62-123">You can click **Preview** to view up to 200 rows of the data extracted by the OLE DB source.</span></span>  
  
11. <span data-ttu-id="cdd62-124">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="cdd62-124">Click **OK**.</span></span>  
  
12. <span data-ttu-id="cdd62-125">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="cdd62-125">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdd62-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="cdd62-126">See Also</span></span>  
 <span data-ttu-id="cdd62-127">[Origem de OLE DB](ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="cdd62-127">[OLE DB Source](ole-db-source.md) </span></span>  
 <span data-ttu-id="cdd62-128">[Transformações do Integration Services](transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="cdd62-128">[Integration Services Transformations](transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="cdd62-129">[Caminhos do Integration Services](integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="cdd62-129">[Integration Services Paths](integration-services-paths.md) </span></span>  
 [<span data-ttu-id="cdd62-130">Tarefa de Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="cdd62-130">Data Flow Task</span></span>](../control-flow/data-flow-task.md)  
  
  
