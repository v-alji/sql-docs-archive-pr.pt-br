---
title: Permissões de convidado em bancos de dados de usuários | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 540f1c6d-df51-497e-958a-3a0f429d2920
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 344c5fd0639876998f1585c32fac5f7599f664e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569988"
---
# <a name="guest-permissions-on-user-databases"></a><span data-ttu-id="b40f5-102">Permissões de convidado em bancos de dados de usuários</span><span class="sxs-lookup"><span data-stu-id="b40f5-102">Guest Permissions on User Databases</span></span>
  <span data-ttu-id="b40f5-103">Esta regra determina se o usuário convidado tem permissão para acessar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b40f5-103">This rule determines whether the guest user has permission to access the database.</span></span> <span data-ttu-id="b40f5-104">Esta regra só se aplica a bancos de dados de usuários.</span><span class="sxs-lookup"><span data-stu-id="b40f5-104">This rule applies to user databases only.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="b40f5-105">Práticas Recomendadas</span><span class="sxs-lookup"><span data-stu-id="b40f5-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="b40f5-106">Revogue a permissão de usuário convidado para acessar o banco de dados se não for necessária.</span><span class="sxs-lookup"><span data-stu-id="b40f5-106">Revoke the guest user permission to access the database if it is not required.</span></span>  
  
 <span data-ttu-id="b40f5-107">O usuário convidado não pode ser descartado, mas pode ser desabilitado revogando sua permissão CONNECT com a execução de REVOKE CONNECT FROM GUEST em qualquer banco de dados que não seja mestre, tempdb ou msdb.</span><span class="sxs-lookup"><span data-stu-id="b40f5-107">The guest user cannot be dropped, but guest user can be disabled by revoking its CONNECT permission by executing REVOKE CONNECT FROM GUEST within any database other than master, tempdb, or msdb.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="b40f5-108">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="b40f5-108">For More Information</span></span>  
 [<span data-ttu-id="b40f5-109">Protegendo o SQL Server</span><span class="sxs-lookup"><span data-stu-id="b40f5-109">Securing SQL Server</span></span>](../security/securing-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="b40f5-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b40f5-110">See Also</span></span>  
 [<span data-ttu-id="b40f5-111">Monitorar e impor melhores práticas usando o gerenciamento baseado em políticas</span><span class="sxs-lookup"><span data-stu-id="b40f5-111">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
