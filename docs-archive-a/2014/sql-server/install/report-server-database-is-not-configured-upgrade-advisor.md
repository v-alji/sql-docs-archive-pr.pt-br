---
title: O banco de dados do servidor de relatório não está configurado (Supervisor de atualização) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], upgrade issues
ms.assetid: b964300c-b220-4244-9fa6-c0c6a57760f6
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 072e689da3f43222396f071e607214a2ec494749
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569045"
---
# <a name="report-server-database-is-not-configured-upgrade-advisor"></a><span data-ttu-id="1945e-102">O banco de dados do servidor de relatório não está configurado (Supervisor de Atualização)</span><span class="sxs-lookup"><span data-stu-id="1945e-102">Report server database is not configured (Upgrade Advisor)</span></span>
  <span data-ttu-id="1945e-103">A atualização está bloqueada devido a uma configuração incompleta do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="1945e-103">Upgrade is blocked due to an incomplete report server configuration.</span></span> <span data-ttu-id="1945e-104">O banco de dados do servidor de relatório não está configurado.</span><span class="sxs-lookup"><span data-stu-id="1945e-104">The report server database is not configured.</span></span>  
  
||  
|-|  
|<span data-ttu-id="1945e-105">**[!INCLUDE[applies](../../includes/applies-md.md)]** Modo nativo do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] &#124; [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] modo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1945e-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode &#124; [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="1945e-106">Componente</span><span class="sxs-lookup"><span data-stu-id="1945e-106">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="1945e-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="1945e-107">Description</span></span>  
 <span data-ttu-id="1945e-108">A Instalação só pode atualizar uma instância do servidor de relatório completamente configurada.</span><span class="sxs-lookup"><span data-stu-id="1945e-108">Setup can only upgrade a fully configured report server instance.</span></span> <span data-ttu-id="1945e-109">Para continuar, você deve configurar o banco de dados do servidor de relatório ou usar o **painel de controle** do Microsoft Windows para remover o recurso do servidor de relatório da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instalação.</span><span class="sxs-lookup"><span data-stu-id="1945e-109">To continue, you must either configure the report server database, or use Microsoft Windows **Control Panel** to remove the report server feature from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span></span> <span data-ttu-id="1945e-110">Depois de remover o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], é possível atualizar outros componentes do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1945e-110">After you remove [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can upgrade other [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="1945e-111">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="1945e-111">Corrective Action</span></span>  
 <span data-ttu-id="1945e-112">Caso não tenha configurado o banco de dados do servidor de relatório, o servidor de relatório não estará operacional e deverá ser removido antes da atualização.</span><span class="sxs-lookup"><span data-stu-id="1945e-112">If you did not configure the report server database, the report server is not operational and should be removed prior to upgrade.</span></span>  
  
 <span data-ttu-id="1945e-113">Para obter informações adicionais sobre a desinstalação [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , consulte [desinstalar o Reporting Services 2012](https://technet.microsoft.com/library/hh479745.aspx\(v=sql.11\)).</span><span class="sxs-lookup"><span data-stu-id="1945e-113">For additional information on uninstalling [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , see [Uninstall Reporting Services 2012](https://technet.microsoft.com/library/hh479745.aspx\(v=sql.11\)).</span></span> <span data-ttu-id="1945e-114">o tópico descreve como desinstalar uma versão específica e os procedimentos são semelhantes para versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="1945e-114">the topic describes how to uninstall a specific version and the procedures are similar for previous versions as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1945e-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1945e-115">See Also</span></span>  
 [<span data-ttu-id="1945e-116">Problemas de atualização do Reporting Services &#40;o supervisor de atualização&#41;</span><span class="sxs-lookup"><span data-stu-id="1945e-116">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
