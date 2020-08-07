---
title: Excluir linhas duplicadas (Ferramentas de Banco de Dados Visual) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], excluding rows
- row duplicates [SQL Server]
- duplicate rows
- row excluded in search [SQL Server]
- result sets [SQL Server], duplicate values
- excluding rows
ms.assetid: ab35a363-421d-4665-946b-ae3f6397af50
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3b396f2738f6895684d828884d4822ea9165e0a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582745"
---
# <a name="exclude-duplicate-rows-visual-database-tools"></a><span data-ttu-id="05513-102">Excluir linhas duplicadas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="05513-102">Exclude Duplicate Rows (Visual Database Tools)</span></span>
  <span data-ttu-id="05513-103">Para exibir apenas os valores exclusivos de um conjunto de resultados, você poderá especificar que deseja excluir duplicatas do conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="05513-103">If you want to see only unique values in a result set, you can specify that you want to exclude duplicates from the result set.</span></span>  
  
### <a name="to-exclude-duplicate-rows-from-the-result-set"></a><span data-ttu-id="05513-104">Para excluir linhas duplicadas do conjunto de resultados</span><span class="sxs-lookup"><span data-stu-id="05513-104">To exclude duplicate rows from the result set</span></span>  
  
1.  <span data-ttu-id="05513-105">Clique com o botão direito do mouse na tela de fundo do Painel de Diagrama e escolha **Propriedades** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="05513-105">Right-click the background of the Diagram pane, then choose **Properties** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="05513-106">Na janela Propriedades, clique em **Valores Distintos** e defina o valor como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="05513-106">In the Property window, click **Distinct values** and set the value to **Yes**.</span></span>  
  
     <span data-ttu-id="05513-107">O Designer de Consulta e Exibição insere a palavra-chave DISTINCT diante da lista de colunas exibidas da instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="05513-107">The Query and View Designer inserts the keyword DISTINCT in front of the list of display columns in the SQL statement.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="05513-108">Usar a palavra-chave DISTINCT talvez o impeça de modificar o conjunto de resultados no painel de resultados.</span><span class="sxs-lookup"><span data-stu-id="05513-108">If you use the DISTINCT keyword you may not be able to modify the result set in the results pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05513-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="05513-109">See Also</span></span>  
 <span data-ttu-id="05513-110">[Especificar critérios de pesquisa &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="05513-110">[Specify Search Criteria &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="05513-111">Classificar e agrupar resultados da consulta &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="05513-111">Sort and Group Query Results &#40;Visual Database Tools&#41;</span></span>](sort-and-group-query-results-visual-database-tools.md)  
  
  
