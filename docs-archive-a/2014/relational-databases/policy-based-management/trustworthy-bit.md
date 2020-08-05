---
title: Bit confiável | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 3198188a-2b59-4865-9560-10f760934b8e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 062a63dd52f4641a0ddfcbc20cb9bad3cce6dc61
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572001"
---
# <a name="trustworthy-bit"></a><span data-ttu-id="85362-102">Bit confiável</span><span class="sxs-lookup"><span data-stu-id="85362-102">Trustworthy Bit</span></span>
  <span data-ttu-id="85362-103">Esta regra determina se a função dbo para um banco de dados é atribuída à função de servidor fixa sysadmin e se o banco de dados tem o bit confiável definido como ON.</span><span class="sxs-lookup"><span data-stu-id="85362-103">This rule determines whether the dbo role for a database is assigned to the sysadmin fixed server role and the database has its trustworthy bit set to ON.</span></span>  
  
 <span data-ttu-id="85362-104">Se essas condições forem atendidas, um usuário de banco de dados privilegiado poderá elevar privilégios para a função sysadmin.</span><span class="sxs-lookup"><span data-stu-id="85362-104">If these conditions are met, a privileged database user can elevate privileges to the sysadmin role.</span></span> <span data-ttu-id="85362-105">Nessa função, o usuário pode criar e executar assemblies não seguros que comprometem o sistema.</span><span class="sxs-lookup"><span data-stu-id="85362-105">In this role, the user can create and run unsafe assemblies that compromise the system.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="85362-106">Práticas Recomendadas</span><span class="sxs-lookup"><span data-stu-id="85362-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="85362-107">Desativar o bit confiável ou revogar permissões sysadmin da função de banco de dados dbo.</span><span class="sxs-lookup"><span data-stu-id="85362-107">Turn off the trustworthy bit or revoke sysadmin permissions from the dbo database role.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="85362-108">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="85362-108">For More Information</span></span>  
 [<span data-ttu-id="85362-109">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="85362-109">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="85362-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="85362-110">See Also</span></span>  
 [<span data-ttu-id="85362-111">Monitorar e impor melhores práticas usando o gerenciamento baseado em políticas</span><span class="sxs-lookup"><span data-stu-id="85362-111">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
