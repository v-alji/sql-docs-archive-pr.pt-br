---
title: Reciclar logs de erros do SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.errorlog.recyclesqlagenterrorlogs.f1
ms.assetid: 10bc2dd1-0505-4527-8ec7-d3b4e5d6352b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2b30f0a2ba9a2d861d4a36a86489757cde512fea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583307"
---
# <a name="recycle-sql-server-agent-error-logs"></a><span data-ttu-id="e9295-102">Reciclar logs de erros do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="e9295-102">Recycle SQL Server Agent Error Logs</span></span>
  <span data-ttu-id="e9295-103">Use esta página para reciclar os [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logs de erros do Agent.</span><span class="sxs-lookup"><span data-stu-id="e9295-103">Use this page to recycle the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Error Logs.</span></span> <span data-ttu-id="e9295-104">A reciclagem do log encerra o log de erros atual do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e inicia um novo log de erros sem reiniciar o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="e9295-104">Recycling the log closes the current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log and starts a new error log without restarting the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span> <span data-ttu-id="e9295-105">Observe que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent mantém os nove logs de erros mais recentes.</span><span class="sxs-lookup"><span data-stu-id="e9295-105">Notice that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent maintains the nine most recent error logs.</span></span> <span data-ttu-id="e9295-106">Se já houver nove logs de erros presentes, a reciclagem do log de erros faz com que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent remova o log de erros mais antigo.</span><span class="sxs-lookup"><span data-stu-id="e9295-106">If there are already nine error logs present, recycling the error log causes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to remove the oldest error log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9295-107">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e9295-107">See Also</span></span>  
 [<span data-ttu-id="e9295-108">Log de erros do SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="e9295-108">SQL Server Agent Error Log</span></span>](sql-server-agent-error-log.md)  
  
  
