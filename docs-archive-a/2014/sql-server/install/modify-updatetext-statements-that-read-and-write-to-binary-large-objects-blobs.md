---
title: Modificar instruções UPDATETEXT que lêem e gravam em BLOBs (objetos binários grandes) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- UPDATETEXT statement
- text [SQL Server], UPDATETEXT statements
ms.assetid: b85da6a7-42f6-4707-a25e-3ded8958b94f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 061e7bad0bae5a74d103406265ad79195f79f7db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573474"
---
# <a name="modify-updatetext-statements-that-read-and-write-to-binary-large-objects-blobs"></a><span data-ttu-id="421b2-102">Modificar instruções UPDATETEXT que leem e gravam em BLOBs (objetos grandes binários)</span><span class="sxs-lookup"><span data-stu-id="421b2-102">Modify UPDATETEXT statements that read and write to binary large objects (BLOBs)</span></span>
  <span data-ttu-id="421b2-103">O Supervisor de Atualização detectou instruções UPDATETEXT que leem e gravam no mesmo BLOB (objeto binário grande) usando o mesmo ponteiro de texto.</span><span class="sxs-lookup"><span data-stu-id="421b2-103">Upgrade Advisor detected UPDATETEXT statements that read and write to the same binary large objects (BLOB) by using the same text pointer.</span></span> <span data-ttu-id="421b2-104">O [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] não oferece suporte para o uso de ponteiros de texto dessa forma.</span><span class="sxs-lookup"><span data-stu-id="421b2-104">[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] does not support the use of text pointers in this manner.</span></span>  
  
## <a name="component"></a><span data-ttu-id="421b2-105">Componente</span><span class="sxs-lookup"><span data-stu-id="421b2-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="421b2-106">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="421b2-106">Corrective Action</span></span>  
 <span data-ttu-id="421b2-107">Copie o BLOB para uma tabela temporária ou variável de tabela e, em seguida, atribua os valores novamente às colunas originais.</span><span class="sxs-lookup"><span data-stu-id="421b2-107">Copy the BLOB to a temporary table or to a table variable, and then assign the value back to the original column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="421b2-108">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="421b2-108">See Also</span></span>  
 <span data-ttu-id="421b2-109">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="421b2-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="421b2-110">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="421b2-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
