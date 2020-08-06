---
title: Definir filtros | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.replconflictviewer.definefilters.f1
helpviewer_keywords:
- Define Filters dialog box
ms.assetid: 1fa71d22-ce5a-4aae-ba05-4d755842aeac
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5154f002c5a35bc78e2eb6777f2cc7bb3d56b635
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569941"
---
# <a name="define-filters"></a><span data-ttu-id="771e9-102">Definir Filtros</span><span class="sxs-lookup"><span data-stu-id="771e9-102">Define Filters</span></span>
  <span data-ttu-id="771e9-103">A caixa de diálogo **Definir Filtros** permite que você defina filtros que são aplicados em conflitos de dados para consultar um subconjunto dos conflitos na grade.</span><span class="sxs-lookup"><span data-stu-id="771e9-103">The **Define Filters** dialog box allows you to define filters that you then apply to data conflicts to see a subset of the conflicts in the grid.</span></span> <span data-ttu-id="771e9-104">Para definir um filtro, escolha um operador na caixa de listagem suspensa **Operador** e então insira em um valor.</span><span class="sxs-lookup"><span data-stu-id="771e9-104">To define a filter, choose an operator from the **Operator** drop-down list box and then enter a value.</span></span> <span data-ttu-id="771e9-105">Por exemplo, para mostrar somente conflitos onde o perdedor do conflito é o servidor **ReplTest1**, selecione **Igual a** na caixa de lista suspensa **Operador** e insira **ReplTest1** na primeira coluna **Valor** .</span><span class="sxs-lookup"><span data-stu-id="771e9-105">For example, to show only those conflicts in which the conflict loser is server **ReplTest1**, select **Equal to** from the **Operator** drop-down list box and enter **ReplTest1** in the first **Value** column.</span></span>  
  
## <a name="options"></a><span data-ttu-id="771e9-106">Opções</span><span class="sxs-lookup"><span data-stu-id="771e9-106">Options</span></span>  
 <span data-ttu-id="771e9-107">**Operador**</span><span class="sxs-lookup"><span data-stu-id="771e9-107">**Operator**</span></span>  
 <span data-ttu-id="771e9-108">Selecione um operador para o filtro, como **Menor que ou Igual a**.</span><span class="sxs-lookup"><span data-stu-id="771e9-108">Select an operator for the filter, such as **Less than or Equal to**.</span></span>  
  
 <span data-ttu-id="771e9-109">**Valor**</span><span class="sxs-lookup"><span data-stu-id="771e9-109">**Value**</span></span>  
 <span data-ttu-id="771e9-110">Insira um valor para o filtro.</span><span class="sxs-lookup"><span data-stu-id="771e9-110">Enter a value for the filter.</span></span> <span data-ttu-id="771e9-111">A maioria dos operadores só exige um valor na primeira coluna **Valor** , mas os operadores **Entre** e **Não Entre** requerem um valor em ambas as coluna **Valor** .</span><span class="sxs-lookup"><span data-stu-id="771e9-111">Most operators only require a value in the first **Value** column, but the **Between** and **Not Between** operators require a value in both of the **Value** columns.</span></span>  
  
 <span data-ttu-id="771e9-112">**Limpar**</span><span class="sxs-lookup"><span data-stu-id="771e9-112">**Clear**</span></span>  
 <span data-ttu-id="771e9-113">Clique nesse botão para limpar todos os filtros anteriormente definidos.</span><span class="sxs-lookup"><span data-stu-id="771e9-113">Click this button to clear all filters that have been previously defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="771e9-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="771e9-114">See Also</span></span>  
 <span data-ttu-id="771e9-115">[Visualizador de Conflitos de Replicação da Microsoft &#40;replicação de mesclagem&#41;](microsoft-replication-conflict-viewer-merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="771e9-115">[Microsoft Replication Conflict Viewer &#40;Merge Replication&#41;](microsoft-replication-conflict-viewer-merge-replication.md) </span></span>  
 [<span data-ttu-id="771e9-116">Visualizador de Conflitos de Replicação da Microsoft &#40;replicação transacional&#41;</span><span class="sxs-lookup"><span data-stu-id="771e9-116">Microsoft Replication Conflict Viewer &#40;Transactional Replication&#41;</span></span>](microsoft-replication-conflict-viewer-transactional-replication.md)  
  
  
