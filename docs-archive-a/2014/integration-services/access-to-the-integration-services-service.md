---
title: Acesso ao serviço de Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SSIS packages, security
- viewing packages while running
- displaying packacges while running
- security [Integration Services], running packages
- packages [Integration Services], security
- current packages running
- Integration Services packages, security
- SQL Server Integration Services packages, security
ms.assetid: 1088aafc-14c5-4e7d-9930-606a24c3049b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7dd6fbed4bedc285069306ab4c400f0f67f9f293
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570827"
---
# <a name="access-to-the-integration-services-service"></a><span data-ttu-id="dd44e-102">Acesso ao serviço Integration Services</span><span class="sxs-lookup"><span data-stu-id="dd44e-102">Access to the Integration Services Service</span></span>
  <span data-ttu-id="dd44e-103">Os níveis de proteção do pacote podem limitar quem tem permissão para editar e executar um pacote.</span><span class="sxs-lookup"><span data-stu-id="dd44e-103">Package protection levels can limit who is allowed to edit and execute a package.</span></span> <span data-ttu-id="dd44e-104">É necessário ter proteção adicional para limitar quem pode exibir a lista de pacotes que estão sendo executados em um servidor e quem pode interromper a execução de pacotes no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd44e-104">Additional protection is needed to limit who can view the list of packages currently running on a server and who can stop currently executing packages in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="dd44e-105">usa o serviço [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para listar os pacotes em execução.</span><span class="sxs-lookup"><span data-stu-id="dd44e-105">uses the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] service to list running packages.</span></span> <span data-ttu-id="dd44e-106">Os membros do grupo Administradores do Windows podem visualizar e parar todos os pacotes em execução.</span><span class="sxs-lookup"><span data-stu-id="dd44e-106">Members of the Windows Administrators group can view and stop all currently running packages.</span></span> <span data-ttu-id="dd44e-107">Os usuários que não são membros do grupo Administradores podem visualizar e parar apenas os pacotes iniciados por eles.</span><span class="sxs-lookup"><span data-stu-id="dd44e-107">Users who are not members of the Administrators group can view and stop only packages that they started.</span></span>  
  
 <span data-ttu-id="dd44e-108">É importante restringir o acesso a computadores que executam um serviço [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , especialmente um serviço [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que pode enumerar pastas remotas.</span><span class="sxs-lookup"><span data-stu-id="dd44e-108">It is important to restrict access to computers that run an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] service, especially an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] service that can enumerate remote folders.</span></span> <span data-ttu-id="dd44e-109">Qualquer usuário autenticado pode solicitar a enumeração dos pacotes.</span><span class="sxs-lookup"><span data-stu-id="dd44e-109">Any authenticated user can request the enumeration of packages.</span></span> <span data-ttu-id="dd44e-110">Mesmo que o serviço não encontre o serviço, o serviço enumera as pastas.</span><span class="sxs-lookup"><span data-stu-id="dd44e-110">Even if the service doesn not find the service, the service enumerates folders.</span></span> <span data-ttu-id="dd44e-111">Esses nomes de pastas podem ser úteis a um usuário mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="dd44e-111">These folder names may be useful to a malicious user.</span></span> <span data-ttu-id="dd44e-112">Se um administrador tiver configurado o serviço para enumerar pastas em uma máquina remota, os usuários também poderão ver os nomes de pastas que eles normalmente não conseguiriam consultar.</span><span class="sxs-lookup"><span data-stu-id="dd44e-112">If an administrator has configured the service to enumerate folders on a remote machine, users may also be able to see folder names that they would normally not be able to see.</span></span>  
  
  
