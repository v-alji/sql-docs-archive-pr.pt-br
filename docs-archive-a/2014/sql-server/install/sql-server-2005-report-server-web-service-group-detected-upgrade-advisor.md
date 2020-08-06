---
title: SQL Server grupo de serviço Web do servidor de relatório 2005 detectado (Supervisor de atualização) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- deployment [Reporting Services]
ms.assetid: 699d24eb-7756-4b41-9294-ef1a94b2f267
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 70be2b9c4e7abd55daaa752830a73cbe6e222659
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686043"
---
# <a name="sql-server-2005-report-server-web-service-group-detected-upgrade-advisor"></a><span data-ttu-id="99656-102">Grupo do serviço Web do servidor de relatório do SQL Server 2005 foi detectado (Supervisor de Atualização)</span><span class="sxs-lookup"><span data-stu-id="99656-102">SQL Server 2005 Report Server Web Service group detected (Upgrade Advisor)</span></span>
  <span data-ttu-id="99656-103">O supervisor de atualização detectou que a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instância está associada a um [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] grupo de serviço Web do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="99656-103">Upgrade Advisor detected that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance is associated with a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Report Server Web service group.</span></span>  
  
||  
|-|  
|<span data-ttu-id="99656-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modo nativo.</span><span class="sxs-lookup"><span data-stu-id="99656-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="99656-105">Componente</span><span class="sxs-lookup"><span data-stu-id="99656-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="99656-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="99656-106">Description</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]<span data-ttu-id="99656-107">Não [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] usa o [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Grupo de serviço Web servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="99656-107">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] does not use the [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Report Server Web service group.</span></span> <span data-ttu-id="99656-108">Quando você fizer a atualização do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], esse grupo de serviço será excluído e as listas de controle de acesso (ACLs) personalizadas desse grupo ou de usuários que pertencem a ele não serão mantidas durante a atualização.</span><span class="sxs-lookup"><span data-stu-id="99656-108">When you upgrade from [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], this service group is deleted and custom Access Control Lists (ACLs) for this group or users who belong to the group are not retained during the upgrade.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="99656-109">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="99656-109">Corrective Action</span></span>  
 <span data-ttu-id="99656-110">Antes da atualização, faça um backup de todas as ACLs personalizadas ou usuários pertencentes ao grupo de serviço Web do servidor de relatório do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99656-110">Before you upgrade, back up any custom ACLs or users who belong to the [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Report Server Web service group.</span></span> <span data-ttu-id="99656-111">Para fazer isso, você pode usar a ferramenta de linha de comando **Icacls.exe** no [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] SP2 e posterior ou a ferramenta de linha de comando Cacls.exe em sistemas operacionais Windows anteriores ao [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] SP2.</span><span class="sxs-lookup"><span data-stu-id="99656-111">To do this, you can use the **Icacls.exe** command-line tool in [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] SP2 and later or the Cacls.exe command-line tool in Windows operating systems prior to [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] SP2.</span></span> <span data-ttu-id="99656-112">Para obter mais informações sobre a sintaxe dessas ferramentas, consulte a documentação do Windows.</span><span class="sxs-lookup"><span data-stu-id="99656-112">For more information about the syntax for these tools, see the Windows product documentation.</span></span> <span data-ttu-id="99656-113">Concluída a instalação com êxito, aplique as ACLs personalizadas ou os usuários ao grupo do Windos do servidor de relatório do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] da instância do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="99656-113">After setup successfully completes, apply the custom ACLs or users to the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Report Server Windows group for your report server instance.</span></span> <span data-ttu-id="99656-114">O [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] grupo servidor de relatório do Windows assume a forma de SQLServerReportServerUser $ \<*computer_name*> $ \<*instance_name*> .</span><span class="sxs-lookup"><span data-stu-id="99656-114">The [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Report Server Windows group takes the form of SQLServerReportServerUser$\<*computer_name*>$\<*instance_name*>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99656-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="99656-115">See Also</span></span>  
 [<span data-ttu-id="99656-116">Problemas de atualização do Reporting Services &#40;o supervisor de atualização&#41;</span><span class="sxs-lookup"><span data-stu-id="99656-116">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
