---
title: Usar o designer de consulta e exibição com dados internacionais (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Visual Database Tools [SQL Server], international data
- queries [SQL Server], international data
- languages [SQL Server], Query and View Designer
- international considerations [SQL Server], Query and View Designer
- Criteria pane
- View Designer, international data
- Query Designer [SQL Server], international data
- localized information in Query and View Designer [SQL Server]
- global considerations [SQL Server], Query and View Designer
- SQL pane [Visual Database Tools]
- multiple language support [SQL Server], Query and View Designer
ms.assetid: 4b51c56f-f902-4e72-b919-e36127369b63
author: stevestein
ms.author: sstein
ms.openlocfilehash: 905e4c6909c792b019c11ef95662a7ec1a113bb4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682034"
---
# <a name="use-the-query-and-view-designer-with-international-data-visual-database-tools"></a><span data-ttu-id="2adf3-102">Usar o Designer de Consulta e Exibição com dados internacionais (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="2adf3-102">Use the Query and View Designer with International Data (Visual Database Tools)</span></span>
  <span data-ttu-id="2adf3-103">Você pode usar o [Designer de Consulta e Exibição](visual-database-tools.md) com dados de qualquer idioma e em qualquer versão do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="2adf3-103">You can use the [Query and View Designer](visual-database-tools.md) with data in any language and in any version of the Windows operating system.</span></span> <span data-ttu-id="2adf3-104">As diretrizes a seguir mostram as diferenças existentes e fornecem informações sobre como gerenciar dados em aplicativos internacionais.</span><span class="sxs-lookup"><span data-stu-id="2adf3-104">The following guidelines outline the differences you will notice and provide information about managing data in international applications.</span></span>  
  
## <a name="localized-information-in-the-criteria-and-sql-panes"></a><span data-ttu-id="2adf3-105">Informações localizadas nos painéis Critérios e SQL</span><span class="sxs-lookup"><span data-stu-id="2adf3-105">Localized Information in the Criteria and SQL Panes</span></span>  
 <span data-ttu-id="2adf3-106">Ao usar o painel Critérios para criar uma consulta, você poderá inserir informações no formato que corresponda às Configurações regionais do Windows do seu computador.</span><span class="sxs-lookup"><span data-stu-id="2adf3-106">If you are using the Criteria pane to create your query, you can enter information in the format that corresponds to the Windows Regional Settings for you computer.</span></span> <span data-ttu-id="2adf3-107">Por exemplo, ao pesquisar dados, você poderá inserir os dados nas colunas de critérios, usando qualquer formato que esteja acostumado a usar, com as seguintes exceções:</span><span class="sxs-lookup"><span data-stu-id="2adf3-107">For example, if you are searching for data, you can enter the data in the Criteria columns using whatever format you are accustomed to using, with these exceptions:</span></span>  
  
-   <span data-ttu-id="2adf3-108">Não há suporte para formatos de dados longos.</span><span class="sxs-lookup"><span data-stu-id="2adf3-108">Long data formats are not supported.</span></span>  
  
-   <span data-ttu-id="2adf3-109">Símbolos de moeda não devem ser inseridos no painel Critérios.</span><span class="sxs-lookup"><span data-stu-id="2adf3-109">Currency symbols should not be entered in the Criteria pane.</span></span>  
  
-   <span data-ttu-id="2adf3-110">Símbolos de moeda não são exibidos no painel Resultados.</span><span class="sxs-lookup"><span data-stu-id="2adf3-110">Currency symbols will not display in the Results pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2adf3-111">No painel Resultados, de fato é possível inserir o símbolo de moeda correspondente às Configurações regionais do Windows do seu computador, mas o símbolo é removido e não é exibido no painel Resultados.</span><span class="sxs-lookup"><span data-stu-id="2adf3-111">In the Results pane, you can actually enter the currency symbol that corresponds to the Windows Regional Settings for your computer, but the symbol will be removed and will not display in the Results pane.</span></span>  
  
-   <span data-ttu-id="2adf3-112">O unário de subtração aparece sempre do lado esquerdo (por exemplo, -1) independentemente das opções de configurações regionais.</span><span class="sxs-lookup"><span data-stu-id="2adf3-112">Unary minus always appears on the left side (for example, -1) regardless of the Regional Settings options.</span></span>  
  
 <span data-ttu-id="2adf3-113">Por outro lado, dados e palavras-chave do painel SQL devem estar sempre em formato ANSI (EUA).</span><span class="sxs-lookup"><span data-stu-id="2adf3-113">In contrast, data and keywords in the SQL pane must always be in ANSI (U.S.) format.</span></span> <span data-ttu-id="2adf3-114">Por exemplo, à medida que o Designer de Consulta e Exibição cria uma consulta, ele insere o formulário ANSI de todas as palavras-chave SQL como SELECT e FROM.</span><span class="sxs-lookup"><span data-stu-id="2adf3-114">For example, as the Query and View Designer builds a query, it inserts the ANSI form of all SQL keywords such as SELECT and FROM.</span></span> <span data-ttu-id="2adf3-115">Para adicionar elementos à instrução no painel SQL, certifique-se de usar o formulário padrão ANSI para os elementos.</span><span class="sxs-lookup"><span data-stu-id="2adf3-115">If you add elements to the statement in the SQL pane, be sure to use the ANSI standard form for the elements.</span></span>  
  
 <span data-ttu-id="2adf3-116">Quando dados são inseridos usando formato específico de local no painel Critérios, o Designer de Consulta e Exibição traduz  automaticamente esses dados para o formato ANSI no painel SQL.</span><span class="sxs-lookup"><span data-stu-id="2adf3-116">When you enter data using local-specific format in the Criteria pane, the Query and View Designer automatically translates it to ANSI format in the SQL pane.</span></span> <span data-ttu-id="2adf3-117">Por exemplo, se as Configurações regionais estiverem definidas como padrão alemão, você poderá inserir dados no painel Critérios em formato "31.12.96".</span><span class="sxs-lookup"><span data-stu-id="2adf3-117">For example, if your Regional Settings are set to Standard German, you can enter data in the Criteria pane in a format such as "31.12.96."</span></span> <span data-ttu-id="2adf3-118">Porém, a data aparecerá no painel SQL em formato ANSI de data e hora como `{ ts '1996-12-31 00:00:00' }.` . Se você inserir dados diretamente no painel SQL, será necessário inseri-los em formato ANSI.</span><span class="sxs-lookup"><span data-stu-id="2adf3-118">However, the date will appear in the SQL pane in ANSI datetime format as `{ ts '1996-12-31 00:00:00' }.` If you enter data directly in the SQL pane, you must enter it in ANSI format.</span></span>  
  
## <a name="sort-order"></a><span data-ttu-id="2adf3-119">Ordem de classificação</span><span class="sxs-lookup"><span data-stu-id="2adf3-119">Sort Order</span></span>  
 <span data-ttu-id="2adf3-120">A ordem de classificação dos dados de uma consulta é determinada pelo banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2adf3-120">The sort order of data in your query is determined by the database.</span></span> <span data-ttu-id="2adf3-121">As opções definidas na caixa de diálogo Configurações regionais do Windows não afetam a ordem de classificação das consultas.</span><span class="sxs-lookup"><span data-stu-id="2adf3-121">Options that you set in the Windows Regional Settings dialog box do not affect sort order for queries.</span></span> <span data-ttu-id="2adf3-122">Em qualquer consulta particular, porém, você pode solicitar que as linhas sejam retornadas em determinada ordem.</span><span class="sxs-lookup"><span data-stu-id="2adf3-122">Within any particular query, however, you can request that rows be returned in a particular order.</span></span>  
  
## <a name="using-double-byte-characters"></a><span data-ttu-id="2adf3-123">Usando caracteres de dois bytes</span><span class="sxs-lookup"><span data-stu-id="2adf3-123">Using Double-Byte Characters</span></span>  
 <span data-ttu-id="2adf3-124">É possível inserir caracteres DBCS de literais e de nomes de objeto de banco de dados, como nomes de tabelas e de exibições, ou aliases.</span><span class="sxs-lookup"><span data-stu-id="2adf3-124">You can enter DBCS characters for literals and for database object names such as table and view names or aliases.</span></span> <span data-ttu-id="2adf3-125">Você também poderá usar caracteres DBCS para nomes de parâmetro e caracteres de marcador de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="2adf3-125">You can also use DBCS characters for parameter names and parameter marker characters.</span></span> <span data-ttu-id="2adf3-126">Porém, não será possível usar caracteres DBCS em elementos de linguagem SQL, como nomes de função ou palavras-chave de SQL.</span><span class="sxs-lookup"><span data-stu-id="2adf3-126">However, you cannot use DBCS characters in SQL language elements such as function names or SQL keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2adf3-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2adf3-127">See Also</span></span>  
 [<span data-ttu-id="2adf3-128">Tópicos de instruções de como criar consultas e exibições &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="2adf3-128">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
