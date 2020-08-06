---
title: Definir a opção de banco de dados AUTO_CLOSE como OFF | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: e6b03364-263a-4ec4-9794-de9869d396ce
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: db6cf5a3f82c3493a8732958594743104fccc968
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685069"
---
# <a name="set-the-auto_close-database-option-to-off"></a><span data-ttu-id="b7a87-102">Definir a opção do banco de dados AUTO_CLOSE como OFF</span><span class="sxs-lookup"><span data-stu-id="b7a87-102">Set the AUTO_CLOSE Database Option to OFF</span></span>
  <span data-ttu-id="b7a87-103">Esta regra verifica se a opção AUTO_ CLOSE é definida como OFF.</span><span class="sxs-lookup"><span data-stu-id="b7a87-103">This rule checks whether the AUTO_ CLOSE option is set OFF.</span></span> <span data-ttu-id="b7a87-104">Quando a opção AUTO_CLOSE está definido como ON, pode causar degradação do desempenho em bancos de dados acessados com frequência, por causa do aumento da sobrecarga ao abrir e fechar o banco de dados após cada conexão.</span><span class="sxs-lookup"><span data-stu-id="b7a87-104">When AUTO_CLOSE is set ON, this option can cause performance degradation on frequently accessed databases because of the increased overhead of opening and closing the database after each connection.</span></span> <span data-ttu-id="b7a87-105">AUTO_CLOSE também libera o cache de procedimento depois de cada conexão.</span><span class="sxs-lookup"><span data-stu-id="b7a87-105">AUTO_CLOSE also flushes the procedure cache after each connection.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="b7a87-106">Práticas Recomendadas</span><span class="sxs-lookup"><span data-stu-id="b7a87-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="b7a87-107">Se um banco de dados for acessado frequentemente, defina sua opção de AUTO_CLOSE como OFF.</span><span class="sxs-lookup"><span data-stu-id="b7a87-107">If a database is accessed frequently, set the AUTO_CLOSE option to OFF for the database.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="b7a87-108">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="b7a87-108">For More Information</span></span>  
 [<span data-ttu-id="b7a87-109">Opções ALTER DATABASE SET &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b7a87-109">ALTER DATABASE SET Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-set-options)  
  
## <a name="see-also"></a><span data-ttu-id="b7a87-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b7a87-110">See Also</span></span>  
 [<span data-ttu-id="b7a87-111">Monitorar e impor melhores práticas usando o gerenciamento baseado em políticas</span><span class="sxs-lookup"><span data-stu-id="b7a87-111">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
