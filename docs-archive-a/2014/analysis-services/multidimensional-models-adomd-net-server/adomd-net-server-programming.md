---
title: Programação de servidor ADOMD.NET | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- programming [ADOMD.NET]
- ADOMD.NET, programming
ms.assetid: 7f7ff5be-3826-43a5-b94d-ddeec5ddb2eb
author: minewiskan
ms.author: owend
ms.openlocfilehash: 522478af0b19f1745d80f167e40345d4751136b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678335"
---
# <a name="adomdnet-server-programming"></a><span data-ttu-id="786fd-102">Programando o servidor no ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="786fd-102">ADOMD.NET Server Programming</span></span>
  <span data-ttu-id="786fd-103">Os componentes de servidor do ADOMD.NET residem no namespace `Microsoft.AnalysisServices.AdomdServer` (em msmgdsrv.dll).</span><span class="sxs-lookup"><span data-stu-id="786fd-103">The ADOMD.NET server components of ADOMD.NET reside within the `Microsoft.AnalysisServices.AdomdServer` namespace (in msmgdsrv.dll).</span></span> <span data-ttu-id="786fd-104">Você usa esses componentes de servidor para criar funções MDX (expressões multidimensionais) personalizadas e procedimentos armazenados que são executados em uma instância do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="786fd-104">You use these server components to create custom Multidimensional Expressions (MDX) functions and stored procedures that are run on an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="786fd-105">Os objetos de servidor oferecem os recursos para a consulta de cubos e de modelos de mineração e para a avaliação de expressões em um determinado contexto.</span><span class="sxs-lookup"><span data-stu-id="786fd-105">The server objects provide the capabilities for querying cubes and mining models, and for evaluating expressions in a given context.</span></span> <span data-ttu-id="786fd-106">Os benefícios da criação de funções e de procedimentos armazenados personalizados incluem execução rápida, implantação centralizada e maior facilidade de manutenção.</span><span class="sxs-lookup"><span data-stu-id="786fd-106">The benefits for creating custom functions and stored procedures include fast execution, centralized deployment, and improved maintainability.</span></span>  
  
 <span data-ttu-id="786fd-107">Os tópicos da tabela a seguir ajudarão você a desenvolver aplicativos de servidor com o ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="786fd-107">The topics in the following table will help you develop ADOMD.NET server applications.</span></span>  
  
|<span data-ttu-id="786fd-108">Tópico</span><span class="sxs-lookup"><span data-stu-id="786fd-108">Topic</span></span>|<span data-ttu-id="786fd-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="786fd-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="786fd-110">Funcionalidade de servidor do ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="786fd-110">ADOMD.NET Server Functionality</span></span>](https://docs.microsoft.com/bi-reference/adomd/multidimensional-models-adomd-net-server/adomd-net-server-functionality)|<span data-ttu-id="786fd-111">Descreve os usos para objetos de servidor do ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="786fd-111">Describes the uses for ADOMD.NET server objects.</span></span>|  
|[<span data-ttu-id="786fd-112">Arquitetura de objeto de servidor do ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="786fd-112">ADOMD.NET Server Object Architecture</span></span>](https://docs.microsoft.com/bi-reference/adomd/multidimensional-models-adomd-net-server/adomd-net-server-object-architecture)|<span data-ttu-id="786fd-113">Descreve a arquitetura de objeto para objetos de servidor do ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="786fd-113">Describes the object architecture for ADOMD.NET server objects.</span></span>|  
|[<span data-ttu-id="786fd-114">Funções e procedimentos armazenados definidos pelo usuário</span><span class="sxs-lookup"><span data-stu-id="786fd-114">User Defined Functions and Stored Procedures</span></span>](https://docs.microsoft.com/analysis-services/adomd/multidimensional-models-adomd-net-server/user-defined-functions-and-stored-procedures)|<span data-ttu-id="786fd-115">Orienta você pelo processo de criação de uma função ou procedimento armazenado definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="786fd-115">Walks you through the process of creating a user defined function or stored Procedure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="786fd-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="786fd-116">See Also</span></span>  
 <span data-ttu-id="786fd-117">[Programação de cliente ADOMD.NET](https://docs.microsoft.com/analysis-services/adomd/multidimensional-models-adomd-net-client/adomd-net-client-programming) </span><span class="sxs-lookup"><span data-stu-id="786fd-117">[ADOMD.NET Client Programming](https://docs.microsoft.com/analysis-services/adomd/multidimensional-models-adomd-net-client/adomd-net-client-programming) </span></span>  
 [<span data-ttu-id="786fd-118">Desenvolvendo com ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="786fd-118">Developing with ADOMD.NET</span></span>](https://docs.microsoft.com/bi-reference/adomd/developing-with-adomd-net)  
  
  
