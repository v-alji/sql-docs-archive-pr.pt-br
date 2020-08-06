---
title: Recursos desativados por padrão (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a9529edf-337e-4fdd-9a13-99cfe96b4fa1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 87752b8760ffc80e80c87ac1132cae36f2f151b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680148"
---
# <a name="features-off-by-default-analysis-services"></a><span data-ttu-id="b7465-102">Recursos desativados por padrão (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="b7465-102">Features off by default (Analysis Services)</span></span>
  <span data-ttu-id="b7465-103">Uma instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] é considerada segura por padrão.</span><span class="sxs-lookup"><span data-stu-id="b7465-103">An instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] is designed to be secure by default.</span></span> <span data-ttu-id="b7465-104">Assim, os recursos que podem comprometer a segurança são desabilitados por padrão.</span><span class="sxs-lookup"><span data-stu-id="b7465-104">Therefore, features that might compromise security are disabled by default.</span></span> <span data-ttu-id="b7465-105">Os recursos a seguir são instalados em um estado desabilitado e deverão ser habilitados especificamente se você quiser usá-los.</span><span class="sxs-lookup"><span data-stu-id="b7465-105">The following features are installed in a disabled state and must specifically be enabled if you want to use them.</span></span>  
  
## <a name="feature-list"></a><span data-ttu-id="b7465-106">Lista de recursos</span><span class="sxs-lookup"><span data-stu-id="b7465-106">Feature List</span></span>  
 <span data-ttu-id="b7465-107">Para habilitar os recursos a seguir, conecte-se ao [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7465-107">To enable the following features, connect to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="b7465-108">Clique com o botão direito do mouse no nome da instância e selecione **Facetas**.</span><span class="sxs-lookup"><span data-stu-id="b7465-108">Right-click the instance name and choose **Facets**.</span></span> <span data-ttu-id="b7465-109">Como alternativa, você pode habilitar esses recursos por meio das propriedades do servidor, conforme descrito na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="b7465-109">Alternatively, you can enable these features through server properties, as described in the next section.</span></span>  
  
-   <span data-ttu-id="b7465-110">Consultas de mineração de dados ad hoc (OpenRowset)</span><span class="sxs-lookup"><span data-stu-id="b7465-110">Ad Hoc Data Mining (OpenRowset) Queries</span></span>  
  
-   <span data-ttu-id="b7465-111">Objetos vinculados (para)</span><span class="sxs-lookup"><span data-stu-id="b7465-111">Linked Objects (To)</span></span>  
  
-   <span data-ttu-id="b7465-112">Objetos vinculados (de)</span><span class="sxs-lookup"><span data-stu-id="b7465-112">Linked Objects (From)</span></span>  
  
-   <span data-ttu-id="b7465-113">Escutar apenas em conexões locais</span><span class="sxs-lookup"><span data-stu-id="b7465-113">Listen Only On Local Connections</span></span>  
  
-   <span data-ttu-id="b7465-114">Funções definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="b7465-114">User Defined Functions</span></span>  
  
## <a name="server-properties"></a><span data-ttu-id="b7465-115">Propriedades do servidor</span><span class="sxs-lookup"><span data-stu-id="b7465-115">Server properties</span></span>  
 <span data-ttu-id="b7465-116">Recursos adicionais que são desativados por padrão podem ser habilitados por meio das propriedades do servidor.</span><span class="sxs-lookup"><span data-stu-id="b7465-116">Additional features that are off by default can be enabled through server properties.</span></span> <span data-ttu-id="b7465-117">Conectar-se a [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7465-117">Connect to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="b7465-118">Clique com o botão direito do mouse no nome da instância e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="b7465-118">Right-click the instance name and choose **Properties**.</span></span> <span data-ttu-id="b7465-119">Clique em **Geral**e, em seguida, clique em **Mostrar avançado** para exibir uma lista de propriedades maior.</span><span class="sxs-lookup"><span data-stu-id="b7465-119">Click **General**, and then click **Show Advanced** to display a larger property list.</span></span>  
  
-   <span data-ttu-id="b7465-120">Consultas de mineração de dados ad hoc (OpenRowset)</span><span class="sxs-lookup"><span data-stu-id="b7465-120">Ad Hoc Data Mining (OpenRowset) Queries</span></span>  
  
-   <span data-ttu-id="b7465-121">Permitir modelos de mineração de sessão (Mineração de dados)</span><span class="sxs-lookup"><span data-stu-id="b7465-121">Allow Session Mining Models (Data Mining)</span></span>  
  
-   <span data-ttu-id="b7465-122">Objetos vinculados (para)</span><span class="sxs-lookup"><span data-stu-id="b7465-122">Linked Objects (To)</span></span>  
  
-   <span data-ttu-id="b7465-123">Objetos vinculados (de)</span><span class="sxs-lookup"><span data-stu-id="b7465-123">Linked Objects (From)</span></span>  
  
-   <span data-ttu-id="b7465-124">Funções COM definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="b7465-124">COM based user-defined functions</span></span>  
  
-   <span data-ttu-id="b7465-125">Definição de Rastreamento do Registrador de Voo (modelos).</span><span class="sxs-lookup"><span data-stu-id="b7465-125">Flight Recorder Trace Definitions (templates).</span></span>  
  
-   <span data-ttu-id="b7465-126">Gravação de log de consulta</span><span class="sxs-lookup"><span data-stu-id="b7465-126">Query logging</span></span>  
  
-   <span data-ttu-id="b7465-127">Escutar apenas em conexões locais</span><span class="sxs-lookup"><span data-stu-id="b7465-127">Listen Only On Local Connections</span></span>  
  
-   <span data-ttu-id="b7465-128">XML binário</span><span class="sxs-lookup"><span data-stu-id="b7465-128">Binary XML</span></span>  
  
-   <span data-ttu-id="b7465-129">Compactação</span><span class="sxs-lookup"><span data-stu-id="b7465-129">Compression</span></span>  
  
-   <span data-ttu-id="b7465-130">Afinidade do grupo.</span><span class="sxs-lookup"><span data-stu-id="b7465-130">Group affinity.</span></span> <span data-ttu-id="b7465-131">Para obter detalhes, consulte [Thread Pool Properties](../server-properties/thread-pool-properties.md) .</span><span class="sxs-lookup"><span data-stu-id="b7465-131">See [Thread Pool Properties](../server-properties/thread-pool-properties.md) for details.</span></span>  
  
  
