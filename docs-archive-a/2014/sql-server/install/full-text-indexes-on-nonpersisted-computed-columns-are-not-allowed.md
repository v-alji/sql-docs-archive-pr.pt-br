---
title: Índices de texto completo em colunas computadas não persistentes não são permitidas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- full-text indexes
ms.assetid: cba737f7-b187-47d0-8458-23dc18d18aca
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: de153d45e2f652bfea6e9dce68428af84be68b6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583989"
---
# <a name="full-text-indexes-on-nonpersisted-computed-columns-are-not-allowed"></a><span data-ttu-id="95e43-102">Índices de texto completo em colunas computadas não persistentes não são permitidos</span><span class="sxs-lookup"><span data-stu-id="95e43-102">Full-text indexes on nonpersisted, computed columns are not allowed</span></span>
  <span data-ttu-id="95e43-103">Não é possível criar índices de texto completo em colunas computadas imprecisas e não determinísticas.</span><span class="sxs-lookup"><span data-stu-id="95e43-103">You cannot create full-text indexes on nondeterministic and imprecise computed columns.</span></span> <span data-ttu-id="95e43-104">Essas colunas não podem ser usadas como colunas de tipo ou colunas de chave de texto completo.</span><span class="sxs-lookup"><span data-stu-id="95e43-104">Such columns cannot be used as type columns or as full-text key columns.</span></span>  
  
## <a name="description"></a><span data-ttu-id="95e43-105">Descrição</span><span class="sxs-lookup"><span data-stu-id="95e43-105">Description</span></span>  
 <span data-ttu-id="95e43-106">No [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], um índice de texto completo pode ser criado usando-se uma coluna computada imprecisa e não determinística como coluna de tipo ou coluna de chave de texto completo.</span><span class="sxs-lookup"><span data-stu-id="95e43-106">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], a full-text index can be created by using a nondeterministic and imprecise computed column as the type column or the full-text key column.</span></span> <span data-ttu-id="95e43-107">Não há mais suporte para essa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="95e43-107">This functionality is not supported.</span></span> <span data-ttu-id="95e43-108">Quando você atualiza, índices de texto completo antigos, incompatíveis e sem-suporte são desabilitados.</span><span class="sxs-lookup"><span data-stu-id="95e43-108">When you upgrade, older, incompatible, and unsupported full-text indexes are disabled.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="95e43-109">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="95e43-109">Corrective Action</span></span>  
 <span data-ttu-id="95e43-110">Para habilitar índices de texto completo, modifique as definições das colunas para que elas sejam determinísticas e precisas.</span><span class="sxs-lookup"><span data-stu-id="95e43-110">To enable these full-text indexes, modify the column definitions so that the columns are deterministic and precise.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95e43-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="95e43-111">See Also</span></span>  
 [<span data-ttu-id="95e43-112">Trabalhando com o Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="95e43-112">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
