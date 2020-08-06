---
title: Extrair dados usando a origem ODBC | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 10f25703-49a2-4d45-abab-6b4da2a57ba5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c05efe2b0479047280fc093ee555e037c77d82e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685862"
---
# <a name="extract-data-by-using-the-odbc-source"></a><span data-ttu-id="ab025-102">Extrair dados por meio da origem ODBC</span><span class="sxs-lookup"><span data-stu-id="ab025-102">Extract Data by Using the ODBC Source</span></span>
  <span data-ttu-id="ab025-103">Este procedimento descreve como extrair dados usando uma fonte ODBC.</span><span class="sxs-lookup"><span data-stu-id="ab025-103">This procedure describes how to extract data by using an ODBC source.</span></span> <span data-ttu-id="ab025-104">Para adicionar e configurar uma origem ODBC, o pacote já deve incluir pelo menos uma tarefa de Fluxo de Dados.</span><span class="sxs-lookup"><span data-stu-id="ab025-104">To add and configure an ODBC source, the package must already include at least one Data Flow task.</span></span>  
  
### <a name="to-extract-data-using-an-odbc-source"></a><span data-ttu-id="ab025-105">Para extrair dados usando uma origem ODBC</span><span class="sxs-lookup"><span data-stu-id="ab025-105">To extract data using an ODBC source</span></span>  
  
1.  <span data-ttu-id="ab025-106">No [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], abra o pacote do [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] desejado.</span><span class="sxs-lookup"><span data-stu-id="ab025-106">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] package you want.</span></span>  
  
2.  <span data-ttu-id="ab025-107">Clique na guia **Fluxo de Dados** e, na **Caixa de Ferramentas**, arraste a origem ODBC para a superfície de design.</span><span class="sxs-lookup"><span data-stu-id="ab025-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the ODBC source to the design surface.</span></span>  
  
3.  <span data-ttu-id="ab025-108">Clique duas vezes na origem ODBC.</span><span class="sxs-lookup"><span data-stu-id="ab025-108">Double-click the ODBC source.</span></span>  
  
4.  <span data-ttu-id="ab025-109">Na caixa de diálogo **Editor de Origem de ODBC** , na página **Gerenciador de Conexões** , selecione um gerenciador de conexões ODBC existente ou clique em **Novo** para criar um gerenciador de conexões novo.</span><span class="sxs-lookup"><span data-stu-id="ab025-109">In the **ODBC Source Editor** dialog box, on the **Connection Manager** page, select an existing ODBC connection manager or click **New** to create a new connection manager.</span></span>  
  
5.  <span data-ttu-id="ab025-110">Selecione o método de acesso de dados.</span><span class="sxs-lookup"><span data-stu-id="ab025-110">Select the data access method.</span></span>  
  
    -   <span data-ttu-id="ab025-111">**Nome da Tabela**: selecione uma tabela ou exibição no banco de dados ou digite uma expressão regular para identificar a tabela à qual o gerenciador de conexão ODBC se conecta.</span><span class="sxs-lookup"><span data-stu-id="ab025-111">**Table Name**: Select a table or view in the database or type a regular expression to identify the table to which the ODBC connection manager connects.</span></span>  
  
         <span data-ttu-id="ab025-112">Essa lista contém apenas as primeiras 1.000 tabelas.</span><span class="sxs-lookup"><span data-stu-id="ab025-112">This list contains the first 1000 tables only.</span></span> <span data-ttu-id="ab025-113">Se o banco de dados contiver mais de 1.000 tabelas, você poderá digitar o início do nome de uma tabela ou usar o curinga (\*) para inserir qualquer parte do nome para exibir a tabela ou tabelas desejadas.</span><span class="sxs-lookup"><span data-stu-id="ab025-113">If your database contains more than 1000 tables, you can type the beginning of a table name or use the (\*) wild card to enter any part of the name to display the table or tables you want to use.</span></span>  
  
    -   <span data-ttu-id="ab025-114">**Comando SQL**: digite um Comando SQL ou clique em **Procurar** para carregar a consulta SQL de um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="ab025-114">**SQL Command**: Type an SQL Command or click **Browse** to load the SQL query from a text file.</span></span>  
  
6.  <span data-ttu-id="ab025-115">É possível clicar em **Visualizar** para exibir até 200 linhas dos dados extraídos pela origem ODBC.</span><span class="sxs-lookup"><span data-stu-id="ab025-115">You can click **Preview** to view up to 200 rows of the data extracted by the ODBC source.</span></span>  
  
7.  <span data-ttu-id="ab025-116">Para atualizar o mapeamento entre colunas externas e de saída, clique em **Colunas** e selecione colunas diferentes na lista **Coluna Externa** .</span><span class="sxs-lookup"><span data-stu-id="ab025-116">To update the mapping between external and output columns, click **Columns** and select different columns in the **External Column** list.</span></span>  
  
8.  <span data-ttu-id="ab025-117">Se necessário, atualize os nomes de colunas de saída editando valores na lista **Coluna de Saída** .</span><span class="sxs-lookup"><span data-stu-id="ab025-117">If necessary, update the names of output columns by editing values in the **Output Column** list.</span></span>  
  
9. <span data-ttu-id="ab025-118">Para configurar a saída de erro, clique em **Saída de Erro**.</span><span class="sxs-lookup"><span data-stu-id="ab025-118">To configure the error output, click **Error Output**.</span></span>  
  
10. <span data-ttu-id="ab025-119">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab025-119">Click **OK**.</span></span>  
  
11. <span data-ttu-id="ab025-120">Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="ab025-120">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab025-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ab025-121">See Also</span></span>  
 <span data-ttu-id="ab025-122">[Editor de Fonte ODBC &#40;Página Gerenciador de Conexões&#41;](../odbc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="ab025-122">[ODBC Source Editor &#40;Connection Manager Page&#41;](../odbc-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="ab025-123">[Editor de Origem ODBC &#40;Página Colunas&#41;](../odbc-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="ab025-123">[ODBC Source Editor &#40;Columns Page&#41;](../odbc-source-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="ab025-124">Editor de Fonte ODBC &#40;Página Saída de Erro&#41;</span><span class="sxs-lookup"><span data-stu-id="ab025-124">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../odbc-source-editor-error-output-page.md)  
  
  
