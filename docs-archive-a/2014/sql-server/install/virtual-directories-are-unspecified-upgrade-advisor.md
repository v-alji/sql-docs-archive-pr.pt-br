---
title: Os diretórios virtuais não estão especificados (Supervisor de atualização) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- virtual directories [Reporting Services]
ms.assetid: 7d32b560-49d6-4558-b5d6-9127067f82d6
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: e20c48d0bf58d28cb2894baa26c2e11db26fab96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573412"
---
# <a name="virtual-directories-are-unspecified-upgrade-advisor"></a><span data-ttu-id="beaa6-102">Diretórios virtuais não especificados (Supervisor de Atualização)</span><span class="sxs-lookup"><span data-stu-id="beaa6-102">Virtual directories are unspecified (Upgrade Advisor)</span></span>
  <span data-ttu-id="beaa6-103">O Supervisor de Atualização não detectou configurações de diretório virtual para o serviço Web Servidor de Relatórios ou para o Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="beaa6-103">Upgrade Advisor did not detect virtual directory settings for the Report Server Web service or Report Manager.</span></span> <span data-ttu-id="beaa6-104">Concluída a atualização, configure as reservas de URL do servidor de relatório usando o Gerenciador de Configurações do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="beaa6-104">After upgrade completes, you must configure URL reservations for the report server by using the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager.</span></span>  
  
||  
|-|  
|<span data-ttu-id="beaa6-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modo nativo.</span><span class="sxs-lookup"><span data-stu-id="beaa6-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="beaa6-106">Componente</span><span class="sxs-lookup"><span data-stu-id="beaa6-106">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="beaa6-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="beaa6-107">Description</span></span>  
 <span data-ttu-id="beaa6-108">A atualização de uma instalação do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] inclui a reserva de novas URLs para o serviço Web Servidor de Relatórios e para o Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="beaa6-108">Upgrading a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation includes reserving new URLs for the Report Server Web service and Report Manager.</span></span> <span data-ttu-id="beaa6-109">O Supervisor de Atualização não detectou diretórios virtuais para o servidor de relatório ou para o Gerenciador de Relatórios da instância que será atualizada, sendo assim, o processo de atualização possui informações insuficientes para a criação de reservas de URL para o servidor de relatório atualizado.</span><span class="sxs-lookup"><span data-stu-id="beaa6-109">Upgrade Advisor did not detect virtual directories for the report server or Report Manager for the instance to be upgraded, and therefore the upgrade process has insufficient information to create URL reservations for the upgraded report server.</span></span> <span data-ttu-id="beaa6-110">A atualização pode prosseguir, mas o servidor de relatório ou o diretório virtual do Gerenciador de Relatórios ficará indefinido após a atualização da instalação.</span><span class="sxs-lookup"><span data-stu-id="beaa6-110">Upgrade can continue, but the report server or Report Manager virtual directory will be undefined after the upgraded installation.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="beaa6-111">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="beaa6-111">Corrective Action</span></span>  
 <span data-ttu-id="beaa6-112">Concluída a atualização, use o Gerenciador de Configurações do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] para definir as URLs do servidor de relatório e do Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="beaa6-112">After upgrade finishes, use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager to set the URLs for report server and Report Manager.</span></span> <span data-ttu-id="beaa6-113">Use o Gerenciador do IIS para remover todos os diretórios virtuais que não serão mais necessários.</span><span class="sxs-lookup"><span data-stu-id="beaa6-113">Use IIS Manager to remove any virtual directories you no longer need.</span></span>  
  
 <span data-ttu-id="beaa6-114">Para obter mais informações, consulte [Configurar uma URL &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) nos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] manuais online do.</span><span class="sxs-lookup"><span data-stu-id="beaa6-114">For more information, see [Configure a URL  &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beaa6-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="beaa6-115">See Also</span></span>  
 [<span data-ttu-id="beaa6-116">Problemas de atualização do Reporting Services &#40;o supervisor de atualização&#41;</span><span class="sxs-lookup"><span data-stu-id="beaa6-116">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
