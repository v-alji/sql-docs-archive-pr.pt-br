---
title: Arquitetura de mineração de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 105f52e1-ad3b-4cd0-b67b-06dbb451c304
author: minewiskan
ms.author: owend
ms.openlocfilehash: a372972fd7fa39f7bcfd2e10abbc4fbf8f8c10aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582217"
---
# <a name="data-mining-architecture"></a><span data-ttu-id="793b8-102">Arquitetura de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="793b8-102">Data Mining Architecture</span></span>
  <span data-ttu-id="793b8-103">Esta seção descreve a arquitetura de soluções de mineração de dados que são hospedadas em uma instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="793b8-103">This section describes the architecture of data mining solutions that are hosted in an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="793b8-104">Os tópicos desta seção descrevem a arquitetura lógica e física de uma instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que oferece suporte à mineração de dados, e também fornecem informações sobre os clientes, provedores e protocolos que podem ser usados na comunicação com servidores de mineração de dados e para trabalhar local ou remotamente com objetos de mineração de dados.</span><span class="sxs-lookup"><span data-stu-id="793b8-104">The topics in this section describe the logical and physical architecture of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance that supports data mining, and also provide information about the clients, providers, and protocols that can be used to communicate with data mining servers, and to work with data mining objects either locally or remotely.</span></span>  
  
 <span data-ttu-id="793b8-105">Em geral, a Mineração de Dados do SQL Server opera como um serviço que é fornecido como parte de uma instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] executada em modo multidimensional; portanto, é recomendável analisar as seções a seguir de Manuais Online que descrevem a operação, a manutenção e a configuração de soluções multidimensionais do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="793b8-105">In general, SQL Server Data Mining operates as a service that is provided as part of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance running in multidimensional mode; therefore, we recommend that you also review the following sections of Books Online that describe the operation, maintenance, and configuration of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] multidimensional solutions.</span></span>  
  
 [<span data-ttu-id="793b8-106">Processamento de objetos de modelo multidimensional</span><span class="sxs-lookup"><span data-stu-id="793b8-106">Multidimensional Model Object Processing</span></span>](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md)  
  
 [<span data-ttu-id="793b8-107">Conectar ao Analysis Services</span><span class="sxs-lookup"><span data-stu-id="793b8-107">Connect to Analysis Services</span></span>](../instances/connect-to-analysis-services.md)  
  
 [<span data-ttu-id="793b8-108">Local de armazenamento do banco de dados</span><span class="sxs-lookup"><span data-stu-id="793b8-108">Database Storage Location</span></span>](../multidimensional-models/database-storage-location.md)  
  
 [<span data-ttu-id="793b8-109">Alternar um banco de dados do Analysis Services entre os modos ReadOnly e ReadWrite</span><span class="sxs-lookup"><span data-stu-id="793b8-109">Switch an Analysis Services database between ReadOnly and ReadWrite modes</span></span>](../multidimensional-models/switch-an-analysis-services-database-between-readonly-and-readwrite-modes.md)  
  
 <span data-ttu-id="793b8-110">Para obter mais informações sobre como você pode implementar a mineração de dados em sua solução de business intelligence, consulte a seção Guias de Solução da Biblioteca MSDN.</span><span class="sxs-lookup"><span data-stu-id="793b8-110">For more information about how you can implement data mining in your business intelligence solution, see the Solution Guides section of the MSDN Library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="793b8-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="793b8-111">In This Section</span></span>  
 [<span data-ttu-id="793b8-112">Arquitetura lógica &#40;Analysis Services – Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="793b8-112">Logical Architecture &#40;Analysis Services - Data Mining&#41;</span></span>](logical-architecture-analysis-services-data-mining.md)  
  
 [<span data-ttu-id="793b8-113">Arquitetura física &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="793b8-113">Physical Architecture &#40;Analysis Services - Data Mining&#41;</span></span>](physical-architecture-analysis-services-data-mining.md)  
  
 [<span data-ttu-id="793b8-114">Serviços de mineração de dados e fontes de dados</span><span class="sxs-lookup"><span data-stu-id="793b8-114">Data Mining Services and Data Sources</span></span>](data-mining-services-and-data-sources.md)  
  
 [<span data-ttu-id="793b8-115">Gerenciamento de soluções de mineração de dados e objetos</span><span class="sxs-lookup"><span data-stu-id="793b8-115">Management of Data Mining Solutions and Objects</span></span>](management-of-data-mining-solutions-and-objects.md)  
  
 [<span data-ttu-id="793b8-116">Visão geral de segurança &#40;Mineração de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="793b8-116">Security Overview &#40;Data Mining&#41;</span></span>](security-overview-data-mining.md)  
  
## <a name="see-also"></a><span data-ttu-id="793b8-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="793b8-117">See Also</span></span>  
 <span data-ttu-id="793b8-118">[Programação de modelo multidimensional](../multidimensional-models/multidimensional-model-programming.md) </span><span class="sxs-lookup"><span data-stu-id="793b8-118">[Multidimensional Model Programming](../multidimensional-models/multidimensional-model-programming.md) </span></span>  
 [<span data-ttu-id="793b8-119">Programação de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="793b8-119">Data Mining Programming</span></span>](../dev-guide/data-mining-programming.md)  
  
  
