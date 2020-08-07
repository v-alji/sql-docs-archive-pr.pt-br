---
title: Restrição de endereço IP detectada (Supervisor de atualização) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], upgrade issues
ms.assetid: 9a154455-c68f-4403-a3a7-b90f4d35eecb
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 2028e59e91d42bfdced2d18fa6ce129dfb108302
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680763"
---
# <a name="ip-address-restriction-detected-upgrade-advisor"></a><span data-ttu-id="f7a7d-102">Restrição de endereço IP detectada (Supervisor de Atualização)</span><span class="sxs-lookup"><span data-stu-id="f7a7d-102">IP address restriction detected (Upgrade Advisor)</span></span>
  <span data-ttu-id="f7a7d-103">O Supervisor de Atualização detectou uma ou mais restrições de endereço IP no site do IIS que hospeda o servidor de relatório ou os diretórios virtuais do Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="f7a7d-103">Upgrade Advisor detected one or more IP address restrictions on the IIS Web site that hosts the report server or Report Manager virtual directories.</span></span> <span data-ttu-id="f7a7d-104">O [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] não fornece suporte nativo para restrições de endereço IP.</span><span class="sxs-lookup"><span data-stu-id="f7a7d-104">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] does not provide native support for IP address restrictions.</span></span>  
  
||  
|-|  
|<span data-ttu-id="f7a7d-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Forma.</span><span class="sxs-lookup"><span data-stu-id="f7a7d-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="f7a7d-106">Componente</span><span class="sxs-lookup"><span data-stu-id="f7a7d-106">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="f7a7d-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="f7a7d-107">Description</span></span>  
 <span data-ttu-id="f7a7d-108">A Instalação não pode definir restrições de endereço IP em URLs criadas para um servidor de relatório atualizado.</span><span class="sxs-lookup"><span data-stu-id="f7a7d-108">Setup cannot define IP address restrictions on URLs created for an upgraded report server.</span></span> <span data-ttu-id="f7a7d-109">A atualização pode continuar, mas as restrições de endereço IP não serão definidas nas URLs do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f7a7d-109">Upgrade can continue, but IP address restrictions will not be defined on the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] URLs.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="f7a7d-110">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="f7a7d-110">Corrective Action</span></span>  
 <span data-ttu-id="f7a7d-111">Depois da atualização, use o ISA Server, o seu software de firewall ou outra solução para permitir ou excluir solicitações de endereços IP específicos para o servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="f7a7d-111">After upgrade, use ISA Server, your firewall software, or another solution to allow or exclude requests from specific IP addresses to the report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7a7d-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f7a7d-112">See Also</span></span>  
 [<span data-ttu-id="f7a7d-113">Problemas de atualização do Reporting Services &#40;o supervisor de atualização&#41;</span><span class="sxs-lookup"><span data-stu-id="f7a7d-113">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
