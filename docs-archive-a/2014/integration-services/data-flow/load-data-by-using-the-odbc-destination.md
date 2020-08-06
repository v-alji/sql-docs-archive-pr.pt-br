---
title: Carregar dados por meio do destino ODBC | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 339ec0a8-922e-48c0-97b3-fc5ee34f95e3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e8bf0b30619c2886df6ddb28858cf98bad858421
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680585"
---
# <a name="load-data-by-using-the-odbc-destination"></a><span data-ttu-id="2eeba-102">Carregar dados por meio do destino ODBC</span><span class="sxs-lookup"><span data-stu-id="2eeba-102">Load Data by Using the ODBC Destination</span></span>
  <span data-ttu-id="2eeba-103">Este procedimento mostra como carregar dados usando o destino ODBC.</span><span class="sxs-lookup"><span data-stu-id="2eeba-103">This procedure shows how to load data by using the ODBC destination.</span></span> <span data-ttu-id="2eeba-104">Para adicionar e configurar um destino ODBC, o pacote já deve incluir pelo menos uma tarefa de Fluxo de Dados e uma fonte.</span><span class="sxs-lookup"><span data-stu-id="2eeba-104">To add and configure an ODBC destination, the package must already include at least one Data Flow task and source.</span></span>  
  
### <a name="to-load-data-using-an-odbc-destination"></a><span data-ttu-id="2eeba-105">Para carregar dados usando um destino ODBC</span><span class="sxs-lookup"><span data-stu-id="2eeba-105">To load data using an ODBC destination</span></span>  
  
1.  <span data-ttu-id="2eeba-106">No [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], abra o pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] desejado.</span><span class="sxs-lookup"><span data-stu-id="2eeba-106">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package you want.</span></span>  
  
2.  <span data-ttu-id="2eeba-107">Clique na guia **Fluxo de Dados** , e então, na **Caixa de Ferramentas**, arraste o destino ODBC para a superfície de design.</span><span class="sxs-lookup"><span data-stu-id="2eeba-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the ODBC destination to the design surface.</span></span>  
  
3.  <span data-ttu-id="2eeba-108">Arraste uma saída disponível para um componente de fluxo de dados para a entrada do destino ODBC.</span><span class="sxs-lookup"><span data-stu-id="2eeba-108">Drag an available output of a data flow component to the input of the ODBC destination.</span></span>  
  
4.  <span data-ttu-id="2eeba-109">Clique duas vezes no destino ODBC.</span><span class="sxs-lookup"><span data-stu-id="2eeba-109">Double-click the ODBC destination.</span></span>  
  
5.  <span data-ttu-id="2eeba-110">Na caixa de diálogo **Editor de Destino ODBC** , na página **Gerenciador de Conexões** , selecione um gerenciador de conexões ODBC existente ou clique em **Novo** para criar um gerenciador de conexões novo.</span><span class="sxs-lookup"><span data-stu-id="2eeba-110">In the **ODBC Destination Editor** dialog box, on the **Connection Manager** page, select an existing ODBC connection manager or click **New** to create a new connection manager.</span></span>  
  
6.  <span data-ttu-id="2eeba-111">Selecione o método de acesso de dados.</span><span class="sxs-lookup"><span data-stu-id="2eeba-111">Select the data access method.</span></span>  
  
    -   <span data-ttu-id="2eeba-112">**Nome da Tabela – Lote**: selecione esta opção para configurar o destino ODBC para funcionar no modo em lote.</span><span class="sxs-lookup"><span data-stu-id="2eeba-112">**Table Name - Batch**: Select this option to configure the ODBC destination to work in batch mode.</span></span> <span data-ttu-id="2eeba-113">Quando você selecionar essa opção, poderá definir o **Tamanho do lote**.</span><span class="sxs-lookup"><span data-stu-id="2eeba-113">When you select this option, you can set the **Batch size**.</span></span>  
  
    -   <span data-ttu-id="2eeba-114">**Nome da Tabela – Linha a Linha**: selecione esta opção para configurar o destino ODBC para inserir cada uma das linhas na tabela de destino, uma de cada vez.</span><span class="sxs-lookup"><span data-stu-id="2eeba-114">**Table Name - Row by Row**: Select this option to configure the ODBC destination to insert each of the rows into the destination table one at a time.</span></span> <span data-ttu-id="2eeba-115">Quando você selecionar essa opção, os dados serão carregados na tabela uma linha de cada vez.</span><span class="sxs-lookup"><span data-stu-id="2eeba-115">When you select this option, the data is loaded into the table one row at a time.</span></span>  
  
7.  <span data-ttu-id="2eeba-116">No campo **Nome da tabela ou exibição** , selecione uma tabela ou exibição disponível do banco de dados na lista ou digite uma expressão regular para identificar a tabela. Essa lista contém apenas as primeiras 1.000 tabelas.</span><span class="sxs-lookup"><span data-stu-id="2eeba-116">In the **Name of the table or the view** field, select an available table or view from the database from the list or type in a regular expression to identify the table.This list contains the first 1000 tables only.</span></span> <span data-ttu-id="2eeba-117">Se o banco de dados contiver mais de 1.000 tabelas, você poderá digitar o início do nome de uma tabela ou usar o curinga (\*) para inserir qualquer parte do nome para exibir a tabela ou tabelas desejadas.</span><span class="sxs-lookup"><span data-stu-id="2eeba-117">If your database contains more than 1000 tables, you can type the beginning of a table name or use the (\*) wild card to enter any part of the name to display the table or tables you want to use.</span></span>  
  
8.  <span data-ttu-id="2eeba-118">Você pode clicar em **Visualizar** para exibir até 200 linhas dos dados da tabela selecionada no destino ODBC.</span><span class="sxs-lookup"><span data-stu-id="2eeba-118">You can click **Preview** to view up to 200 rows of the data from the table selected in the ODBC destination.</span></span>  
  
9. <span data-ttu-id="2eeba-119">Clique em **Mapeamentos** e mapeie as colunas da lista **Colunas de Entrada Disponíveis** para as colunas da lista **Colunas de Destino Disponíveis** arrastando as colunas de uma lista para outra.</span><span class="sxs-lookup"><span data-stu-id="2eeba-119">Click **Mappings** and then map columns from the **Available Input Columns** list to columns in the **Available Destination Columns** list by dragging columns from one list to another.</span></span>  
  
10. <span data-ttu-id="2eeba-120">Para configurar a saída de erro, clique em **Saída de Erro**.</span><span class="sxs-lookup"><span data-stu-id="2eeba-120">To configure the error output, click **Error Output**.</span></span>  
  
11. <span data-ttu-id="2eeba-121">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2eeba-121">Click **OK**.</span></span>  
  
12. <span data-ttu-id="2eeba-122">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="2eeba-122">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2eeba-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2eeba-123">See Also</span></span>  
 <span data-ttu-id="2eeba-124">[Editor do Destino ODBC &#40;Página Gerenciador de Conexões&#41;](../odbc-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="2eeba-124">[ODBC Destination Editor &#40;Connection Manager Page&#41;](../odbc-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="2eeba-125">[Editor de Destinos ODBC &#40;Página Mapeamentos&#41;](../odbc-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="2eeba-125">[ODBC Destination Editor &#40;Mappings Page&#41;](../odbc-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="2eeba-126">Editor de Fonte ODBC &#40;Página Saída de Erro&#41;</span><span class="sxs-lookup"><span data-stu-id="2eeba-126">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../odbc-source-editor-error-output-page.md)  
  
  
