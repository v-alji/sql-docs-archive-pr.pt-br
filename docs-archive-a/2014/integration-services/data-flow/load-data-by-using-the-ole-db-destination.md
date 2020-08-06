---
title: Carregar dados por meio do destino OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- loading data
- OLE DB destination [Integration Services]
- destinations [Integration Services], OLE DB
ms.assetid: 78899498-725e-4300-a7af-f983f4ea384b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 43e8d1123ae91d9e68c00fbe3e05c490383afe0c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680583"
---
# <a name="load-data-by-using-the-ole-db-destination"></a><span data-ttu-id="91787-102">Carregar dados por meio do destino OLE DB</span><span class="sxs-lookup"><span data-stu-id="91787-102">Load Data by Using the OLE DB Destination</span></span>
  <span data-ttu-id="91787-103">Para adicionar e configurar um destino OLE DB, o pacote já deve incluir pelo menos uma tarefa de Fluxo de Dados e uma fonte.</span><span class="sxs-lookup"><span data-stu-id="91787-103">To add and configure an OLE DB destination, the package must already include at least one Data Flow task and a source.</span></span>  
  
### <a name="to-load-data-using-an-ole-db-destination"></a><span data-ttu-id="91787-104">Para carregar dados usando um destino OLE DB</span><span class="sxs-lookup"><span data-stu-id="91787-104">To load data using an OLE DB destination</span></span>  
  
1.  <span data-ttu-id="91787-105">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="91787-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="91787-106">No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="91787-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="91787-107">Clique na guia **Fluxo de Dados** e em seguida, da **Caixa de Ferramentas**arraste o destino OLE DB para a superfície de design.</span><span class="sxs-lookup"><span data-stu-id="91787-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the OLE DB destination to the design surface.</span></span>  
  
4.  <span data-ttu-id="91787-108">Conecte o destino OLE DB a um fluxo de dados arrastando um conector de uma fonte de dados, ou de uma transformação anterior, para o destino.</span><span class="sxs-lookup"><span data-stu-id="91787-108">Connect the OLE DB destination to the data flow by dragging a connector from a data source or a previous transformation to the destination.</span></span>  
  
5.  <span data-ttu-id="91787-109">Clique duas vezes sobre o destino OLE DB.</span><span class="sxs-lookup"><span data-stu-id="91787-109">Double-click the OLE DB destination.</span></span>  
  
6.  <span data-ttu-id="91787-110">Na caixa de diálogo **Editor de Destino OLE DB** , na página **Gerenciador de Conexões** , selecione um gerenciador de conexões OLE DB existente ou clique em **Novo** para criar um gerenciador de conexões novo.</span><span class="sxs-lookup"><span data-stu-id="91787-110">In the **OLE DB Destination Editor** dialog box, on the **Connection Manager** page, select an existing OLE DB connection manager or click **New** to create a new connection manager.</span></span> <span data-ttu-id="91787-111">Para obter mais informações, consulte [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="91787-111">For more information, see [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span></span>  
  
7.  <span data-ttu-id="91787-112">Selecione o método de acesso de dados:</span><span class="sxs-lookup"><span data-stu-id="91787-112">Select the data access method:</span></span>  
  
    -   <span data-ttu-id="91787-113">**Tabela ou exibição** Selecione uma tabela ou exibição no banco de dados que contém os dados.</span><span class="sxs-lookup"><span data-stu-id="91787-113">**Table or view** Select a table or view in the database that contains the data.</span></span>  
  
    -   <span data-ttu-id="91787-114">**Tabela ou exibição – carregamento rápido** Selecione uma tabela ou exibição no banco de dados que contém os dados, e defina as opções de carregamento rápido: **Manter identidade**, **Manter nulos**, **Bloqueio da tabela**, **Restrição de Verificação**, **Linhas por lote**ou **Tamanho máximo de confirmação de inserção**.</span><span class="sxs-lookup"><span data-stu-id="91787-114">**Table or view - fast load** Select a table or view in the database that contains the data, and then set the fast-load options: **Keep identity**, **Keep null**, **Table lock**, **Check constraint**, **Rows per batch**, or **Maximum insert commit size**.</span></span>  
  
    -   <span data-ttu-id="91787-115">**Variável de nome da tabela ou exibição** Selecione a variável definida pelo usuário que contém o nome da tabela ou da exibição no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="91787-115">**Table name or view name variable** Select the user-defined variable that contains the name of a table or view in the database.</span></span>  
  
    -   <span data-ttu-id="91787-116">**Variável de nome da tabela ou exibição – carregamento rápido** Selecione a variável definida pelo usuário que contém o nome de uma tabela ou exibição no banco de dados que contém os dados e em seguida defina as opções de carregamento rápido.</span><span class="sxs-lookup"><span data-stu-id="91787-116">**Table name or view name variable fast load** Select the user-defined variable that contains the name of a table or view in the database that contains the data, and then set the fast-load options.</span></span>  
  
    -   <span data-ttu-id="91787-117">**Comando SQL** Digite um comando SQL ou clique em **Construir Consulta** para escrever um comando SQL usando o **Construtor de Consultas**.</span><span class="sxs-lookup"><span data-stu-id="91787-117">**SQL command** Type an SQL command or click **Build Query** to write an SQL command by using the **Query Builder**.</span></span>  
  
8.  <span data-ttu-id="91787-118">Clique em **Mapeamentos** e mapeie as colunas da lista **Colunas de Entrada Disponíveis** para as colunas da lista **Colunas de Destino Disponíveis** arrastando as colunas de uma lista para outra.</span><span class="sxs-lookup"><span data-stu-id="91787-118">Click **Mappings** and then map columns from the **Available Input Columns** list to columns in the **Available Destination Columns** list by dragging columns from one list to another.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="91787-119">O destino OLE DB mapeia automaticamente as colunas de mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="91787-119">The OLE DB destination automatically maps same-named columns.</span></span>  
  
9. <span data-ttu-id="91787-120">Para configurar a saída de erro, clique em **Saída de Erro**.</span><span class="sxs-lookup"><span data-stu-id="91787-120">To configure the error output, click **Error Output**.</span></span> <span data-ttu-id="91787-121">Para obter mais informações, consulte [Configurar uma saída de erro em um componente de fluxo de dados](../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="91787-121">For more information, see [Configure an Error Output in a Data Flow Component](../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
10. <span data-ttu-id="91787-122">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="91787-122">Click **OK**.</span></span>  
  
11. <span data-ttu-id="91787-123">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="91787-123">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91787-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="91787-124">See Also</span></span>  
 <span data-ttu-id="91787-125">[Destino OLE DB](ole-db-destination.md) </span><span class="sxs-lookup"><span data-stu-id="91787-125">[OLE DB Destination](ole-db-destination.md) </span></span>  
 <span data-ttu-id="91787-126">[Transformações do Integration Services](transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="91787-126">[Integration Services Transformations](transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="91787-127">[Caminhos do Integration Services](integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="91787-127">[Integration Services Paths](integration-services-paths.md) </span></span>  
 [<span data-ttu-id="91787-128">Tarefa de Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="91787-128">Data Flow Task</span></span>](../control-flow/data-flow-task.md)  
  
  
