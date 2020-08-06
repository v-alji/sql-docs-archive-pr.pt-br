---
title: Armazenamento do gerenciamento baseado em políticas | Microsoft Docs
ms.custom: ''
ms.date: 08/10/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, storage
ms.assetid: d0cbf214-fc2e-4917-8d31-1d71c9ffa61d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0e775d038c5bb4f7a467f2691e374296f1389d84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680372"
---
# <a name="policy-based-management-storage"></a><span data-ttu-id="204a0-102">Armazenamento do Gerenciamento Baseado em Políticas</span><span class="sxs-lookup"><span data-stu-id="204a0-102">Policy-Based Management Storage</span></span>
  <span data-ttu-id="204a0-103">As políticas são armazenadas no banco de dados msdb.</span><span class="sxs-lookup"><span data-stu-id="204a0-103">Policies are stored in the msdb database.</span></span> <span data-ttu-id="204a0-104">Após a alteração de uma política ou condição, deve ser feito backup do msdb.</span><span class="sxs-lookup"><span data-stu-id="204a0-104">After a policy or condition is changed, msdb should be backed up.</span></span> <span data-ttu-id="204a0-105">Para obter mais informações, consulte [Fazer backup e restaurar bancos de dados do sistema &#40;SQL Server&#41;](../backup-restore/back-up-and-restore-of-system-databases-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="204a0-105">For more information, see [Back Up and Restore of System Databases &#40;SQL Server&#41;](../backup-restore/back-up-and-restore-of-system-databases-sql-server.md).</span></span>  
  
## <a name="storing-policies"></a><span data-ttu-id="204a0-106">Armazenando políticas</span><span class="sxs-lookup"><span data-stu-id="204a0-106">Storing Policies</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="204a0-107">inclui políticas que podem ser usadas para monitorar uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="204a0-107">includes policies that can be used to monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="204a0-108">Por padrão, essas políticas não são instaladas no [!INCLUDE[ssDE](../../includes/ssde-md.md)] ; no entanto, elas podem ser importadas do local de instalação padrão de C:\Program Files (x86) \Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033.</span><span class="sxs-lookup"><span data-stu-id="204a0-108">By default, these policies are not installed on the [!INCLUDE[ssDE](../../includes/ssde-md.md)]; however, they can be imported from the default installation location of C:\Program Files (x86)\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033.</span></span>  
  
 <span data-ttu-id="204a0-109">Você pode criar políticas diretamente usando o menu **Arquivo/Novo** e salvá-las em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="204a0-109">You can directly create policies by using the **File/New** menu, and then saving them to a file.</span></span> <span data-ttu-id="204a0-110">Isso permite criar políticas quando você não estiver conectado a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="204a0-110">This enables you to create policies when you are not connected to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="204a0-111">O histórico de políticas avaliadas na instância atual do [!INCLUDE[ssDE](../../includes/ssde-md.md)] é mantido em tabelas do sistema de msdb.</span><span class="sxs-lookup"><span data-stu-id="204a0-111">Policy history for policies evaluated in the current instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is maintained in msdb system tables.</span></span> <span data-ttu-id="204a0-112">O histórico de políticas aplicadas a outras instâncias do [!INCLUDE[ssDE](../../includes/ssde-md.md)] ou aplicadas ao [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] ou ao [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] não é retido.</span><span class="sxs-lookup"><span data-stu-id="204a0-112">Policy history for policies applied to other instances of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] or applied to [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] or [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] is not retained.</span></span>  
  
  
