---
title: Gerenciador de Conexões WMI | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], WMI
- connection managers [Integration Services], WMI
- WMI connection manager [Integration Services]
ms.assetid: fbfa4ba7-3d0d-4d6b-94ad-50741a88d03d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f15aefb0ed112f1d5b7bb05421750b6689a11339
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574866"
---
# <a name="wmi-connection-manager"></a><span data-ttu-id="92e4e-102">Gerenciador de conexões WMI</span><span class="sxs-lookup"><span data-stu-id="92e4e-102">WMI Connection Manager</span></span>
  <span data-ttu-id="92e4e-103">Um gerenciador de conexões WMI permite que um pacote use o WMI (Instrumentação de Gerenciamento do Windows, Windows Management Instrumentation) para gerenciar informações em um ambiente corporativo.</span><span class="sxs-lookup"><span data-stu-id="92e4e-103">A WMI connection manager enables a package to use Windows Management Instrumentation (WMI) to manage information in an enterprise environment.</span></span> <span data-ttu-id="92e4e-104">A tarefa Serviço Web que o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] inclui usa um gerenciador de conexões WMI.</span><span class="sxs-lookup"><span data-stu-id="92e4e-104">The Web Service task that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses a WMI connection manager.</span></span>  
  
 <span data-ttu-id="92e4e-105">Quando você adiciona um Gerenciador de conexões WMI a um pacote, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] o cria um Gerenciador de conexões que será resolvido para uma conexão WMI em tempo de execução, define as propriedades do Gerenciador de conexões e adiciona o Gerenciador de conexões à `Connections` coleção no pacote.</span><span class="sxs-lookup"><span data-stu-id="92e4e-105">When you add a WMI connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to a WMI connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="92e4e-106">A propriedade `ConnectionManagerType` do gerenciador de conexões é definida como `WMI`.</span><span class="sxs-lookup"><span data-stu-id="92e4e-106">The `ConnectionManagerType` property of the connection manager is set to `WMI`.</span></span>  
  
## <a name="configuration-of-the-wmi-connection-manager"></a><span data-ttu-id="92e4e-107">Configuração do gerenciador de conexões WMI</span><span class="sxs-lookup"><span data-stu-id="92e4e-107">Configuration of the WMI Connection Manager</span></span>  
 <span data-ttu-id="92e4e-108">Você pode configurar um gerenciador de conexões WMI das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="92e4e-108">You can configure a WMI connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="92e4e-109">Especifique o nome de um servidor.</span><span class="sxs-lookup"><span data-stu-id="92e4e-109">Specify the name of a server.</span></span>  
  
-   <span data-ttu-id="92e4e-110">Especifique um namespace no servidor.</span><span class="sxs-lookup"><span data-stu-id="92e4e-110">Specify a namespace on the server.</span></span>  
  
-   <span data-ttu-id="92e4e-111">Selecione o modo de autenticação para a conexão com o servidor.</span><span class="sxs-lookup"><span data-stu-id="92e4e-111">Select the authentication mode for connecting to the server.</span></span>  
  
 <span data-ttu-id="92e4e-112">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="92e4e-112">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="92e4e-113">Para obter mais informações sobre as propriedades que podem ser definidas no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, consulte [Editor do Gerenciador de Conexões WMI](../wmi-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="92e4e-113">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [WMI Connection Manager Editor](../wmi-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="92e4e-114">Para obter informações sobre como configurar um gerenciador de conexões programaticamente, consulte <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> e [Adicionando conexões programaticamente](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="92e4e-114">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92e4e-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="92e4e-115">See Also</span></span>  
 <span data-ttu-id="92e4e-116">[Tarefa serviço Web](../control-flow/web-service-task.md) </span><span class="sxs-lookup"><span data-stu-id="92e4e-116">[Web Service Task](../control-flow/web-service-task.md) </span></span>  
 [<span data-ttu-id="92e4e-117">Conexões do SSIS &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="92e4e-117">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
