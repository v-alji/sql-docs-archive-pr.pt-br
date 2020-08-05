---
title: Falhas inesperadas do sistema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 1679bf9e-a2ef-4f90-8907-a002f7341a7d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b791ba0e3f709288a4e2c5b6add4e74e15d56dee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571992"
---
# <a name="unexpected-system-failures"></a><span data-ttu-id="09155-102">Falhas inesperadas do sistema</span><span class="sxs-lookup"><span data-stu-id="09155-102">Unexpected System Failures</span></span>
  <span data-ttu-id="09155-103">Esta regra verifica o SYSTEM Event 6008 no log de eventos do computador.</span><span class="sxs-lookup"><span data-stu-id="09155-103">This rule checks for SYSTEM Event 6008 in the computer event log.</span></span> <span data-ttu-id="09155-104">Esse evento indica um desligamento do sistema inesperado.</span><span class="sxs-lookup"><span data-stu-id="09155-104">This event indicates an unexpected system shutdown.</span></span> <span data-ttu-id="09155-105">O sistema pode estar instável e não fornecer a estabilidade e a integridade necessárias para hospedar uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09155-105">The system might be unstable and might not provide the stability and integrity that is required to host an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="09155-106">Práticas Recomendadas</span><span class="sxs-lookup"><span data-stu-id="09155-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="09155-107">Resolva imediatamente a causa dos reinícios inesperados do servidor ou move a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para outro computador.</span><span class="sxs-lookup"><span data-stu-id="09155-107">Immediately address the cause of the unexpected server restarts, or move the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to another computer.</span></span>  
  
  
