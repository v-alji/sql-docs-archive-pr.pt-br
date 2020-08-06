---
title: Caixa de diálogo Colunas de Índice de Texto Completo (Ferramentas de Banco de Dados Visual) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.fulltextcolumn
ms.assetid: a6f41c5c-d950-4d64-9e42-d062925917b6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7f1cd2c94739a13e1820d8c05b338abd91d8a908
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685411"
---
# <a name="full-text-index-columns-dialog-box-visual-database-tools"></a><span data-ttu-id="4e3f0-102">Caixa de diálogo colunas de índice de texto completo (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="4e3f0-102">Full-Text Index Columns Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="4e3f0-103">Esta caixa de diálogo lista as colunas que participam do índice de texto completo para a tabela aberta no Designer de Tabela.</span><span class="sxs-lookup"><span data-stu-id="4e3f0-103">This dialog box lists the columns participating in the full-text index for the table open in Table Designer.</span></span> <span data-ttu-id="4e3f0-104">Para acessar essa caixa de diálogo, clique com o botão direito do mouse na tabela no Designer de Tabela, escolha **Índice de Texto Completo** e, na caixa de diálogo **Índice de Texto Completo**, clique no índice com as colunas que você deseja exibir ou editar, clique no campo **Colunas** na grade à direita e clique nas reticências ( **…** ).</span><span class="sxs-lookup"><span data-stu-id="4e3f0-104">To access this dialog box, right-click the table in Table Designer, choose **Full-Text Index**, and in the **Full-Text Index** dialog box, click the index with columns you want to view or edit, click the **Columns** field in the grid to the right, and click the ellipses (**...**).</span></span>  
  
## <a name="options"></a><span data-ttu-id="4e3f0-105">Opções</span><span class="sxs-lookup"><span data-stu-id="4e3f0-105">Options</span></span>  
 <span data-ttu-id="4e3f0-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="4e3f0-106">**Column**</span></span>  
 <span data-ttu-id="4e3f0-107">Mostra os nomes das colunas que fazem parte do índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="4e3f0-107">Shows the names of columns participating in the full-text index.</span></span> <span data-ttu-id="4e3f0-108">Para adicionar uma coluna, clique na primeira célula vazia e escolha uma coluna da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="4e3f0-108">To add a column, click in the first empty cell and choose a column from the drop-down list.</span></span> <span data-ttu-id="4e3f0-109">Só estarão acessíveis as colunas com tipos de dados baseados em texto ou em imagens.</span><span class="sxs-lookup"><span data-stu-id="4e3f0-109">Only columns with either text-based or image data types will be accessible.</span></span>  
  
 <span data-ttu-id="4e3f0-110">**Tipo de Dados**</span><span class="sxs-lookup"><span data-stu-id="4e3f0-110">**Data Type**</span></span>  
 <span data-ttu-id="4e3f0-111">Mostra o tipo de dados para cada coluna.</span><span class="sxs-lookup"><span data-stu-id="4e3f0-111">Shows the data type for each column.</span></span> <span data-ttu-id="4e3f0-112">Trata-se de uma propriedade somente leitura.</span><span class="sxs-lookup"><span data-stu-id="4e3f0-112">This is a read-only property.</span></span> <span data-ttu-id="4e3f0-113">Para alterar um tipo de dados, abra a tabela no Designer de Tabela, clique na coluna e edite o tipo de dados na guia **Propriedades da Coluna** .</span><span class="sxs-lookup"><span data-stu-id="4e3f0-113">To change a data type, open the table in Table Designer, click the column, and edit the data type in the **Column Properties** tab.</span></span>  
  
 <span data-ttu-id="4e3f0-114">**Digitado por Coluna**</span><span class="sxs-lookup"><span data-stu-id="4e3f0-114">**Typed by Column**</span></span>  
 <span data-ttu-id="4e3f0-115">Aplica-se somente a colunas com o tipo de dados `image`.</span><span class="sxs-lookup"><span data-stu-id="4e3f0-115">Applies only to columns with the data type `image`.</span></span> <span data-ttu-id="4e3f0-116">Fornece uma lista suspensa na qual você pode escolher quais das outras colunas representam o tipo de dados dessa coluna.</span><span class="sxs-lookup"><span data-stu-id="4e3f0-116">Provides a drop-down list from which you can choose which of the other columns represent the data type of this column.</span></span> <span data-ttu-id="4e3f0-117">Se esta coluna não for do tipo de dados `image`, o valor será Nenhum.</span><span class="sxs-lookup"><span data-stu-id="4e3f0-117">If this column is not of the `image` data type the value will be None.</span></span>  
  
 <span data-ttu-id="4e3f0-118">Colunas com o tipo de dados `image` podem conter arquivos do Microsoft Office (arquivos .doc, .xls, e .ppt), arquivo de texto (arquivos .txt) e arquivos HTML (arquivos .htm); definir o tipo de dados dessa coluna para imagem permite que a procura de texto completo busque os conteúdos dos arquivos.</span><span class="sxs-lookup"><span data-stu-id="4e3f0-118">Columns with the data type `image` can contain Microsoft Office files (.doc, .xls, and .ppt files), text files (.txt files), and HTML files (.htm files), and setting the data type of that column to image allows the full-text search to search the contents of the files.</span></span>  
  
 <span data-ttu-id="4e3f0-119">**Idioma**</span><span class="sxs-lookup"><span data-stu-id="4e3f0-119">**Language**</span></span>  
 <span data-ttu-id="4e3f0-120">Lista os idiomas disponíveis.</span><span class="sxs-lookup"><span data-stu-id="4e3f0-120">Lists available languages.</span></span> <span data-ttu-id="4e3f0-121">Escolha o idioma da lista suspensa de idiomas que é apropriado para seus dados de coluna.</span><span class="sxs-lookup"><span data-stu-id="4e3f0-121">Choose the language from the drop-down list appropriate for your column data.</span></span> <span data-ttu-id="4e3f0-122">Por exemplo, se você estiver usando um sistema operacional em inglês, mas quiser indexar uma coluna que contenha texto em alemão, escolha alemão na lista suspensa para melhorar o desempenho do índice.</span><span class="sxs-lookup"><span data-stu-id="4e3f0-122">For example, if you are using an English operating system, but you want to index a column that contains German text, choose German from the drop-down list to improve the index's performance.</span></span>  
  
 <span data-ttu-id="4e3f0-123">**Semântica Estatística**</span><span class="sxs-lookup"><span data-stu-id="4e3f0-123">**Statistical Semantics**</span></span>  
 <span data-ttu-id="4e3f0-124">Especifique se habilitará a indexação semântica da coluna selecionada.</span><span class="sxs-lookup"><span data-stu-id="4e3f0-124">Select whether to enable semantic indexing for the selected column.</span></span> <span data-ttu-id="4e3f0-125">Para obter mais informações, veja [Pesquisa semântica &#40;SQL Server&#41;](../../relational-databases/search/semantic-search-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4e3f0-125">For more information, see [Semantic Search &#40;SQL Server&#41;](../../relational-databases/search/semantic-search-sql-server.md).</span></span>  
  
 <span data-ttu-id="4e3f0-126">Se você selecionar um **Idioma** antes de selecionar **Semântica Estatística**, e o idioma selecionado não tiver um Modelo de Idioma Semântico associado, a caixa de seleção **Semântica Estatística** será desabilitada.</span><span class="sxs-lookup"><span data-stu-id="4e3f0-126">If you select a **Language** prior to selecting **Statistical Semantics**, and the selected language does not have an associated Semantic Language Model, then the **Statistical Semantics** checkbox is disabled.</span></span> <span data-ttu-id="4e3f0-127">Se você selecionar **Semântica Estatística** antes de selecionar um **Idioma**, os idiomas disponíveis na caixa de combinação suspensa serão restringidos a esses para os quais o Modelo de Idioma Semântico dá suporte.</span><span class="sxs-lookup"><span data-stu-id="4e3f0-127">If you select **Statistical Semantics** prior to selecting a **Language**, the languages available in the drop-down combo box will be restricted to those for which there is Semantic Language Model support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e3f0-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4e3f0-128">See Also</span></span>  
 [<span data-ttu-id="4e3f0-129">Caixa de diálogo Índice de Texto Completo &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="4e3f0-129">Full-Text Index Dialog Box &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
