---
title: Certificados de cliente no site do servidor de relatório (Supervisor de atualização) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], upgrade issues
ms.assetid: 5ecce26b-99df-4109-8e51-d150d369dff7
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 563a64e695ef552a712a5678f56d38fdfbff619f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573511"
---
# <a name="client-certificates-on-the-report-server-web-site-upgrade-advisor"></a><span data-ttu-id="ee525-102">Certificados cliente no site do servidor de relatório (Supervisor de Atualização)</span><span class="sxs-lookup"><span data-stu-id="ee525-102">Client certificates on the report server web site (Upgrade Advisor)</span></span>
  <span data-ttu-id="ee525-103">O Supervisor de Atualização detectou um ou mais certificados de cliente no site do IIS que hospeda o servidor de relatório ou os diretórios virtuais do Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="ee525-103">Upgrade Advisor detected one or more client certificates on the IIS Web site that hosts the report server or Report Manager virtual directories.</span></span>  
  
||  
|-|  
|<span data-ttu-id="ee525-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modo nativo.</span><span class="sxs-lookup"><span data-stu-id="ee525-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="ee525-105">Componente</span><span class="sxs-lookup"><span data-stu-id="ee525-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="ee525-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="ee525-106">Description</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]<span data-ttu-id="ee525-107">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]o não oferece suporte ao uso de certificados de cliente para autenticar usuários.</span><span class="sxs-lookup"><span data-stu-id="ee525-107">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] does not support the use of client certificates to authenticate users.</span></span> <span data-ttu-id="ee525-108">A atualização pode continuar, mas os certificados de cliente não serão usados pelo servidor de relatório atualizado.</span><span class="sxs-lookup"><span data-stu-id="ee525-108">Upgrade can continue, but client certificates will not be used by the upgraded report server.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="ee525-109">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="ee525-109">Corrective Action</span></span>  
 <span data-ttu-id="ee525-110">Será necessário usar outra solução, como o ISA Server, para garantir que quaisquer requisitos de autenticação de certificado de cliente sejam atendidos.</span><span class="sxs-lookup"><span data-stu-id="ee525-110">You will have to use a separate solution such as ISA Server to ensure any client certificate authentication requirements are addressed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee525-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ee525-111">See Also</span></span>  
 [<span data-ttu-id="ee525-112">Problemas de atualização do Reporting Services &#40;o supervisor de atualização&#41;</span><span class="sxs-lookup"><span data-stu-id="ee525-112">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
