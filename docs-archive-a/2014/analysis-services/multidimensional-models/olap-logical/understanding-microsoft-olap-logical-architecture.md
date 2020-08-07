---
title: Arquitetura lógica (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- Analysis Services, architecture
- logical architecture [Analysis Services Multidimensional Data]
ms.assetid: 1b9cae0a-8990-4194-af5f-a1ea5f2aff06
author: minewiskan
ms.author: owend
ms.openlocfilehash: d93361fb14bc6544ffa7376439c2da0c8e06c3fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581546"
---
# <a name="logical-architecture-analysis-services---multidimensional-data"></a><span data-ttu-id="90e70-102">Arquitetura lógica (Analysis Services – Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="90e70-102">Logical Architecture (Analysis Services - Multidimensional Data)</span></span>
  [!INCLUDE[msCoName](../../../includes/msconame-md.md)]<span data-ttu-id="90e70-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] o usa componentes de cliente e servidor para fornecer OLAP (processamento analítico online) e Data Mining funcionalidade para aplicativos Business Intelligence:</span><span class="sxs-lookup"><span data-stu-id="90e70-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] uses both server and client components to supply online analytical processing (OLAP) and data mining functionality for business intelligence applications:</span></span>  
  
-   <span data-ttu-id="90e70-104">O componente de servidor do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] é implementado como um serviço do Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="90e70-104">The server component of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] is implemented as a Microsoft Windows service.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="90e70-105">[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]dá suporte a várias instâncias no mesmo computador, com cada instância do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] implementada como uma instância separada do serviço do Windows.</span><span class="sxs-lookup"><span data-stu-id="90e70-105">[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] supports multiple instances on the same computer, with each instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] implemented as a separate instance of the Windows service.</span></span>  
  
-   <span data-ttu-id="90e70-106">Os clientes comunicam-se com o [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] usando o XMLA padrão público, um protocolo baseado em SOAP para emissão de comandos e recebimento de respostas, expostos como um serviço Web.</span><span class="sxs-lookup"><span data-stu-id="90e70-106">Clients communicate with [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] using the public standard XML for Analysis (XMLA), a SOAP-based protocol for issuing commands and receiving responses, exposed as a Web service.</span></span> <span data-ttu-id="90e70-107">Os modelos de objeto de cliente são também fornecidos por XMLA e podem ser acessados pelo uso de um provedor gerenciado, como ADOMD.NET ou um provedor OLE DB.</span><span class="sxs-lookup"><span data-stu-id="90e70-107">Client object models are also provided over XMLA, and can be accessed either by using a managed provider, such as ADOMD.NET, or a native OLE DB provider.</span></span>  
  
-   <span data-ttu-id="90e70-108">Os comandos de consulta podem ser emitidos usando as seguintes linguagens: SQL, Multidimensional Expressions (MDX), uma linguagem de consulta padrão do setor para análise ou DMX (Data Mining Extensions) uma linguagem de consulta padrão do setor orientada para mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="90e70-108">Query commands can be issued using the following languages: SQL; Multidimensional Expressions (MDX), an industry standard query language for analysis; or Data Mining Extensions (DMX), an industry standard query language oriented toward data mining.</span></span> <span data-ttu-id="90e70-109">O ASSL (Analysis Services Scripting Language) também pode ser usado para gerenciar objetos de banco de dados do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="90e70-109">Analysis Services Scripting Language (ASSL) can also be used to manage [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] database objects.</span></span>  
  
 <span data-ttu-id="90e70-110">O [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] também oferece suporte a um mecanismo de cubo local, permitindo que aplicativos em clientes desconectados naveguem em dados multidimensionais armazenados localmente.</span><span class="sxs-lookup"><span data-stu-id="90e70-110">[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] also supports a local cube engine that enables applications on disconnected clients to browse locally stored multidimensional data.</span></span> <span data-ttu-id="90e70-111">Para obter mais informações, consulte [requisitos de arquitetura de cliente para o desenvolvimento de Analysis Services](../olap-physical/client-architecture-requirements-for-analysis-services-development.md)</span><span class="sxs-lookup"><span data-stu-id="90e70-111">For more information, see [Client Architecture Requirements for Analysis Services Development](../olap-physical/client-architecture-requirements-for-analysis-services-development.md)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="90e70-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="90e70-112">In This Section</span></span>  
 <span data-ttu-id="90e70-113">**Visão geral da arquitetura lógica**</span><span class="sxs-lookup"><span data-stu-id="90e70-113">**Logical Architecture Overview**</span></span>  
 [<span data-ttu-id="90e70-114">Visão geral da arquitetura lógica &#40;Analysis Services de dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="90e70-114">Logical Architecture Overview &#40;Analysis Services - Multidimensional Data&#41;</span></span>](logical-architecture-overview-analysis-services-multidimensional-data.md)  
  
 <span data-ttu-id="90e70-115">**Objetos de servidor**</span><span class="sxs-lookup"><span data-stu-id="90e70-115">**Server Objects**</span></span>  
 [<span data-ttu-id="90e70-116">Objetos de servidor &#40;Analysis Services-dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="90e70-116">Server Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](server-objects-analysis-services-multidimensional-data.md)  
  
 <span data-ttu-id="90e70-117">**Objetos de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="90e70-117">**Database Objects**</span></span>  
 [<span data-ttu-id="90e70-118">Objetos de banco de dados &#40;Analysis Services – Dados Multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="90e70-118">Database Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](database-objects-analysis-services-multidimensional-data.md)  
  
 <span data-ttu-id="90e70-119">**Objetos de dimensão**</span><span class="sxs-lookup"><span data-stu-id="90e70-119">**Dimension Objects**</span></span>  
 [<span data-ttu-id="90e70-120">Objetos de dimensão &#40;Analysis Services de dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="90e70-120">Dimension Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../../multidimensional-models-olap-logical-dimension-objects/dimension-objects-analysis-services-multidimensional-data.md)  
  
 <span data-ttu-id="90e70-121">**Objetos de Cubo**</span><span class="sxs-lookup"><span data-stu-id="90e70-121">**Cube Objects**</span></span>  
 [<span data-ttu-id="90e70-122">Objetos de cubo &#40;Analysis Services de dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="90e70-122">Cube Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../../multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md)  
  
 <span data-ttu-id="90e70-123">**Segurança de acesso do usuário**</span><span class="sxs-lookup"><span data-stu-id="90e70-123">**User Access Security**</span></span>  
 [<span data-ttu-id="90e70-124">Arquitetura da segurança de acesso do usuário</span><span class="sxs-lookup"><span data-stu-id="90e70-124">User Access Security Architecture</span></span>](understanding-microsoft-olap-logical-architecture.md)  
  
## <a name="see-also"></a><span data-ttu-id="90e70-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="90e70-125">See Also</span></span>  
 <span data-ttu-id="90e70-126">[Noções básicas sobre a arquitetura Microsoft OLAP](../olap-physical/understanding-microsoft-olap-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="90e70-126">[Understanding Microsoft OLAP Architecture](../olap-physical/understanding-microsoft-olap-architecture.md) </span></span>  
 [<span data-ttu-id="90e70-127">Arquitetura física &#40;Analysis Services – Dados Multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="90e70-127">Physical Architecture &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../olap-physical/understanding-microsoft-olap-physical-architecture.md)  
  
  
