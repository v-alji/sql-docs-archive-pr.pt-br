---
title: Os separadores de palavras de pesquisa de texto completo e os filtros melhoraram significativamente no SQL Server 2005 e SQL Server 2008 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- filters [Full-Text Search]
- word breakers [Full-Text Search]
ms.assetid: 8d06bda9-0bbf-4baa-b270-07b1c1f640eb
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d2e7d3b8da56b407d3937b05cd980c3f8a4eb0c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582798"
---
# <a name="full-text-search-word-breakers-and-filters-significantly-improved-in-sql-server-2005-and-sql-server-2008"></a><span data-ttu-id="54476-102">Significativa melhora nos separadores de palavras e filtros da Pesquisa de Texto Completo no SQL Server 2005 e SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="54476-102">Full-Text Search word breakers and filters significantly improved in SQL Server 2005 and SQL Server 2008</span></span>
  <span data-ttu-id="54476-103">Os separadores de palavras e os filtros foram alterados significativamente.</span><span class="sxs-lookup"><span data-stu-id="54476-103">The word breakers and filters were significantly changed.</span></span> <span data-ttu-id="54476-104">Foram implementadas outras melhorias nos separadores de palavras, incluindo aperfeiçoamento com relação à abrangência do idioma e à confiabilidade.</span><span class="sxs-lookup"><span data-stu-id="54476-104">Additional improvements have been made to word breakers, including enhanced language coverage and reliability.</span></span>  
  
## <a name="description"></a><span data-ttu-id="54476-105">Descrição</span><span class="sxs-lookup"><span data-stu-id="54476-105">Description</span></span>  
 <span data-ttu-id="54476-106">Separadores de palavras e filtros usados pela Pesquisa de Texto Completo do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] foram aperfeiçoados com relação à funcionalidade e à confiabilidade.</span><span class="sxs-lookup"><span data-stu-id="54476-106">Word breakers and filters used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Full-Text Search have been significantly modified to achieve improvements in functionality and reliability.</span></span> <span data-ttu-id="54476-107">Em alguns casos específicos, alterações em separadores de palavras podem impactar na geração de tokens de alguns dados.</span><span class="sxs-lookup"><span data-stu-id="54476-107">In some specific cases, changes to the word breakers can impact how some data is tokenized.</span></span> <span data-ttu-id="54476-108">Os tokens criados no [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] podem ser diferentes dos tokens criados no [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] ou [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54476-108">Tokens created in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] may be different from earlier tokens created in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] or [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="54476-109">Para obter informações sobre separadores de palavras, consulte [configurar e gerenciar separadores de palavras e lematizadores para pesquisa](../../relational-databases/search/configure-and-manage-word-breakers-and-stemmers-for-search.md).</span><span class="sxs-lookup"><span data-stu-id="54476-109">For information about word breakers, see [Configure and Manage Word Breakers and Stemmers for Search](../../relational-databases/search/configure-and-manage-word-breakers-and-stemmers-for-search.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54476-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="54476-110">See Also</span></span>  
 [<span data-ttu-id="54476-111">Trabalhando com o Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="54476-111">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
