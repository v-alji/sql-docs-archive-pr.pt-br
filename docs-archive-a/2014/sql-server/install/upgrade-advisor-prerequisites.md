---
title: Pré-requisitos do supervisor de atualização | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- requirements [Upgrade Advisor]
- software [Upgrade Advisor]
- system requirements [Upgrade Advisor]
- Setup [Upgrade Advisor]
- SQL Server Upgrade Advisor, prerequisites
- prerequisites [Upgrade Advisor]
- Upgrade Advisor [SQL Server], prerequisites
ms.assetid: d21a39e5-5f81-4096-a7dd-f244e4779992
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 41c97cf585d1768c7aebeec2613ee8744cb220da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573417"
---
# <a name="upgrade-advisor-prerequisites"></a><span data-ttu-id="c345e-102">Pré-requisitos do Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="c345e-102">Upgrade Advisor Prerequisites</span></span>
  <span data-ttu-id="c345e-103">Este tópico descreve os requisitos de software do Supervisor de Atualização.</span><span class="sxs-lookup"><span data-stu-id="c345e-103">This topic describes the software requirements for Upgrade Advisor.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c345e-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="c345e-104">Prerequisites</span></span>  
 <span data-ttu-id="c345e-105">Os pré-requisitos para instalar e executar o Supervisor de Atualização são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="c345e-105">The prerequisites for installing and running Upgrade Advisor are as follows:</span></span>  
  
-   [!INCLUDE[wiprlhext](../../includes/wiprlhext-md.md)] <span data-ttu-id="c345e-106">SP1, [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] a partir do SP2, Windows 7 ou [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] R2.</span><span class="sxs-lookup"><span data-stu-id="c345e-106">SP1, [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] beginning with SP2, Windows 7, or [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] R2.</span></span>  
  
-   <span data-ttu-id="c345e-107">Windows Installer 4.5.</span><span class="sxs-lookup"><span data-stu-id="c345e-107">Windows Installer 4.5.</span></span> <span data-ttu-id="c345e-108">Você pode instalar o Windows Installer do [site do Windows Installer](https://www.microsoft.com/download/details.aspx?id=8483).</span><span class="sxs-lookup"><span data-stu-id="c345e-108">You can install Windows Installer from the [Windows Installer Web site](https://www.microsoft.com/download/details.aspx?id=8483).</span></span>  
  
-   <span data-ttu-id="c345e-109">O [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], a partir do .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="c345e-109">The [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], beginning with .NET Framework 4.</span></span> <span data-ttu-id="c345e-110">O [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] está disponível na [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mídia do produto e do [SDK, redistribuível e Service Pack site de download da Web](https://go.microsoft.com/fwlink/?LinkId=48882).</span><span class="sxs-lookup"><span data-stu-id="c345e-110">The [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] is available on the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] product media, and from the [SDK, redistributable, and service pack download Web site](https://go.microsoft.com/fwlink/?LinkId=48882).</span></span>  
  
    -   <span data-ttu-id="c345e-111">Para instalar o .NET Framework 4 a partir da mídia do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], localize a raiz da unidade de disco.</span><span class="sxs-lookup"><span data-stu-id="c345e-111">To install the .NET Framework 4 from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] media, locate the root of the disk drive.</span></span> <span data-ttu-id="c345e-112">Clique duas vezes nas pastas \redist e DotNetFrameworks, e execute o dotNetFx40_Full_x86_x64.exe (para sistemas operacionais de 32 e 64 bits).</span><span class="sxs-lookup"><span data-stu-id="c345e-112">Then double-click the \redist folder, double-click the DotNetFrameworks folder, and run dotNetFx40_Full_x86_x64.exe (for both 32-bit and 64-bit operating systems).</span></span>  
  
-   <span data-ttu-id="c345e-113">O [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom é um pré-requisito para instalar o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] supervisor de atualização e não é instalado pela instalação do supervisor de atualização.</span><span class="sxs-lookup"><span data-stu-id="c345e-113">The [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom is a prerequisite for installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor, and is not installed by Upgrade Advisor Setup.</span></span> <span data-ttu-id="c345e-114">A instalação exige que você baixe e instale o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Feature Pack.</span><span class="sxs-lookup"><span data-stu-id="c345e-114">The Setup requires you to download and install the [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Feature Pack.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c345e-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c345e-115">See Also</span></span>  
 [<span data-ttu-id="c345e-116">Como fazer: Para instalar o Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="c345e-116">How to: Install Upgrade Advisor</span></span>](../../../2014/sql-server/install/how-to-install-upgrade-advisor.md)  
  
  
