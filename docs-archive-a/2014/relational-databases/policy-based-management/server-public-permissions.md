---
title: Permissões públicas de servidor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 9a276caa-ea38-473d-92bc-26302bfcf660
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7913c4715f47b8105b72b1c817dbe77e52d40539
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685074"
---
# <a name="server-public-permissions"></a><span data-ttu-id="acf4d-102">Permissões públicas de servidor</span><span class="sxs-lookup"><span data-stu-id="acf4d-102">Server public Permissions</span></span>
  <span data-ttu-id="acf4d-103">Esta regra determina se a função de servidor público tem permissões de servidor.</span><span class="sxs-lookup"><span data-stu-id="acf4d-103">This rule determines whether the public server role has server permissions.</span></span> <span data-ttu-id="acf4d-104">Todo logon criado no servidor é um membro da função de servidor público.</span><span class="sxs-lookup"><span data-stu-id="acf4d-104">Every login that is created on the server is a member of the public server role.</span></span> <span data-ttu-id="acf4d-105">Se esta condição for atendida, todo logon no servidor terá permissões de servidor.</span><span class="sxs-lookup"><span data-stu-id="acf4d-105">If this condition is met, every login on the server will have server permissions.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="acf4d-106">Práticas Recomendadas</span><span class="sxs-lookup"><span data-stu-id="acf4d-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="acf4d-107">Não conceda permissões de servidor à função de servidor público.</span><span class="sxs-lookup"><span data-stu-id="acf4d-107">Do not grant server permissions to the server public role.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="acf4d-108">Após a conclusão da instalação, a função **pública** tem `CONNECT` permissão em todos os pontos de extremidade, exceto na **conexão de administrador dedicada**.</span><span class="sxs-lookup"><span data-stu-id="acf4d-108">After setup completes the **PUBLIC** role has `CONNECT` permission on all the endpoints except the **Dedicated Admin Connection**.</span></span> <span data-ttu-id="acf4d-109">Isso é normal e não deve ser alterado.</span><span class="sxs-lookup"><span data-stu-id="acf4d-109">This is normal and should not be normally changed.</span></span> <span data-ttu-id="acf4d-110">(O acesso é controlado pela permissão `CONNECT SQL`, que é concedida automaticamente quando novos logons são criados.)</span><span class="sxs-lookup"><span data-stu-id="acf4d-110">(Access is controlled by using the `CONNECT SQL` permission which is automatically granted when new logins are created.)</span></span>  
  
### <a name="for-more-information"></a><span data-ttu-id="acf4d-111">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="acf4d-111">For more information</span></span>  
 [<span data-ttu-id="acf4d-112">Protegendo o SQL Server</span><span class="sxs-lookup"><span data-stu-id="acf4d-112">Securing SQL Server</span></span>](../security/securing-sql-server.md)  
  
  
