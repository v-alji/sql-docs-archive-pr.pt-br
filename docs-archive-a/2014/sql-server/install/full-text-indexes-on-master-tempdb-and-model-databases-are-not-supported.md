---
title: Não há suporte para índices de texto completo em bancos de dados mestre, tempdb e modelo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- full-text indexes
ms.assetid: f7992965-42c1-4eb8-a7fb-afb38b67c740
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: fbd5e3133ed87fed9bdaf6d668df62c6471df766
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583990"
---
# <a name="full-text-indexes-on-master-tempdb-and-model-databases-are-not-supported"></a><span data-ttu-id="56700-102">Não há suporte para índices de texto completo em bancos de dados mestre, tempdb e modelo</span><span class="sxs-lookup"><span data-stu-id="56700-102">Full-text indexes on master, tempdb and model databases are not supported</span></span>
  <span data-ttu-id="56700-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não aceita índices de texto completo em nenhum banco de dados do sistema.</span><span class="sxs-lookup"><span data-stu-id="56700-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not allow full-text indexes on any system database.</span></span>  
  
## <a name="description"></a><span data-ttu-id="56700-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="56700-104">Description</span></span>  
 <span data-ttu-id="56700-105">No [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], havia suporte para índices de texto completo em bancos de dados mestre, tempdb e modelo.</span><span class="sxs-lookup"><span data-stu-id="56700-105">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], full-text indexes were supported on the master, tempdb, and model databases.</span></span>  
  
 <span data-ttu-id="56700-106">Todos os catálogos de texto completo nos bancos de dados mestre, tempdb e modelo são removidos durante a atualização.</span><span class="sxs-lookup"><span data-stu-id="56700-106">Any full-text catalogs in the master, tempdb, and model databases are removed during the upgrade.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56700-107">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="56700-107">See Also</span></span>  
 [<span data-ttu-id="56700-108">Trabalhando com o Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="56700-108">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
