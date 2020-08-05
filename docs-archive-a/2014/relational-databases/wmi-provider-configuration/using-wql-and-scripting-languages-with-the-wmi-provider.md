---
title: Usando WQL e linguagens de script com o provedor WMI para gerenciamento de configuração | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- queries [WMI]
- scripts [WMI]
- query language [WMI]
- WMI Query Language [WMI]
- WQL [WMI]
- WMI Provider for Configuration Management, WQL
- WMI Provider for Configuration Management, scripts
ms.assetid: c1e64905-3c2b-4974-88f4-abf17cf7e289
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d8c903cd0e993728865bce3371c349a2d0ba7485
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573844"
---
# <a name="using-wql-and-scripting-languages-with-the-wmi-provider-for-configuration-management"></a><span data-ttu-id="3cfa9-102">Usando as linguagens WQL e de scripts com o provedor WMI para gerenciamento de configuração</span><span class="sxs-lookup"><span data-stu-id="3cfa9-102">Using WQL and Scripting Languages with the WMI Provider for Configuration Management</span></span>
  <span data-ttu-id="3cfa9-103">Os aplicativos de gerenciamento acessam os serviços e configurações de rede do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando o Provedor WMI (Instrumentação de Gerenciamento do Windows) para objetos de Gerenciamento de Configuração de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="3cfa9-103">Management applications access [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services and network settings using the Windows Management Instrumentation (WMI) Provider for Configuration Management objects in two ways:</span></span>  
  
-   <span data-ttu-id="3cfa9-104">Usando um editor de WQL ou ferramenta de consulta, como o WBEMTest.exe para consultar o objeto definido com WQL (Linguagem de Instrumentação de Gerenciamento do Windows).</span><span class="sxs-lookup"><span data-stu-id="3cfa9-104">Using a WQL editor or query tool, such as WBEMTest.exe to query the object set with the Windows Management Instrumentation Language (WQL).</span></span>  
  
-   <span data-ttu-id="3cfa9-105">Usando uma linguagem de scripts, como o VBScript.</span><span class="sxs-lookup"><span data-stu-id="3cfa9-105">Using a scripting language, such as VBScript.</span></span>  
  
 <span data-ttu-id="3cfa9-106">Como alternativa, os serviços e configurações de rede do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] podem ser gerenciados via programação usando objetos gerenciados WMI no SMO.</span><span class="sxs-lookup"><span data-stu-id="3cfa9-106">Alternatively, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services and network settings can be managed programmatically using the WMI managed objects in SMO.</span></span> <span data-ttu-id="3cfa9-107">Para obter mais informações sobre como programar objetos gerenciados por WMI, consulte [Gerenciando serviços e configurações de rede usando o provedor WMI](../server-management-objects-smo/tasks/managing-services-and-network-settings-by-using-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="3cfa9-107">For more information about programming WMI managed objects, see [Managing Services and Network Settings by Using WMI Provider](../server-management-objects-smo/tasks/managing-services-and-network-settings-by-using-wmi-provider.md).</span></span>  
  
 <span data-ttu-id="3cfa9-108">O Provedor WMI para Gerenciamento de Configuração pode ser acessado usando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager e o Console de Gerenciamento [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cfa9-108">The WMI provider for Configuration Management can be accessed by using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager and [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console.</span></span> <span data-ttu-id="3cfa9-109">Para obter mais informações sobre como acessar o provedor WMI de uma interface do usuário, consulte [Tópicos de instruções sobre como gerenciar serviços &#40;SQL Server Configuration Manager&#41;](../../database-engine/managing-services-how-to-topics-sql-server-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="3cfa9-109">For more information about accessing the WMI provider from a user interface, see [Managing Services How-to Topics &#40;SQL Server Configuration Manager&#41;](../../database-engine/managing-services-how-to-topics-sql-server-configuration-manager.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cfa9-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3cfa9-110">See Also</span></span>  
 <span data-ttu-id="3cfa9-111">[Acessar o provedor WMI para gerenciamento de configuração usando WQL](access-wmi-provider-for-configuration-management-using-wql.md) </span><span class="sxs-lookup"><span data-stu-id="3cfa9-111">[Access WMI Provider for Configuration Management using WQL](access-wmi-provider-for-configuration-management-using-wql.md) </span></span>  
 [<span data-ttu-id="3cfa9-112">Modificar as propriedades avançadas do serviço do SQL Server usando o VBScript</span><span class="sxs-lookup"><span data-stu-id="3cfa9-112">Modify SQL Server Service Advanced Properties using VBScript</span></span>](access-wmi-provider-for-configuration-management-using-vbscript.md)  
  
  
