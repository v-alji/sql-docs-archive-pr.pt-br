---
title: Modelagem de tabela (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 80027288-c203-4667-a3e1-40fa572b4975
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44f358f0f36e84ad903a0a4fcb0203291019e7aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571613"
---
# <a name="tabular-modeling-ssas-tabular"></a><span data-ttu-id="96482-102">Modelagem tabular (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="96482-102">Tabular Modeling (SSAS Tabular)</span></span>
  <span data-ttu-id="96482-103">Modelos tabulares são bancos de dados de memória no Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="96482-103">Tabular models are in-memory databases in Analysis Services.</span></span> <span data-ttu-id="96482-104">Usando algoritmos de compactação de última geração e processador de consulta multi-threaded, o mecanismo analítico na memória xVelocity (VertiPaq) entrega acesso rápido a objetos e dados modelo tabular relatando aplicativos clientes como o Microsoft Excel e o Microsoft [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96482-104">Using state-of-the-art compression algorithms and multi-threaded query processor, the xVelocity in-memory analytics engine (VertiPaq) delivers fast access to tabular model objects and data by reporting client applications such as Microsoft Excel and Microsoft [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span></span>  
  
 <span data-ttu-id="96482-105">Modelos tabulares dão suporte a acesso a dados por meio de dois modos: modo armazenado em cache e modo DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="96482-105">Tabular models support data access through two modes: Cached mode and DirectQuery mode.</span></span> <span data-ttu-id="96482-106">No modo armazenado em cache, você pode integrar dados de várias origens inclusive bancos de dados relacionais, feeds de dados e arquivos de texto planos.</span><span class="sxs-lookup"><span data-stu-id="96482-106">In cached mode, you can integrate data from multiple sources including relational databases, data feeds, and flat text files.</span></span> <span data-ttu-id="96482-107">No modo DirectQuery, você pode ignorar o modelo de memória, permitindo que aplicativos cliente consultem dados diretamente na origem (SQL Server relacional).</span><span class="sxs-lookup"><span data-stu-id="96482-107">In DirectQuery mode, you can bypass the in-memory model, allowing client applications to query data directly at the (SQL Server relational) source.</span></span>  
  
 <span data-ttu-id="96482-108">Os modelos tabulares são criados no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] usando novos modelos de projeto de modelo tabular.</span><span class="sxs-lookup"><span data-stu-id="96482-108">Tabular models are authored in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] using new tabular model project templates.</span></span> <span data-ttu-id="96482-109">Você pode importar dados de várias origens e enriquecer o modelo adicionando relações, colunas calculadas, medidas, KPIs e hierarquias.</span><span class="sxs-lookup"><span data-stu-id="96482-109">You can import data from multiple sources, and then enrich the model by adding relationships, calculated columns, measures, KPIs, and hierarchies.</span></span> <span data-ttu-id="96482-110">Modelos podem ser implantados a uma instância do Analysis Services onde os aplicativos de relatório de cliente podem conectar-se a eles.</span><span class="sxs-lookup"><span data-stu-id="96482-110">Models can then be deployed to an instance of Analysis Services where client reporting applications can connect to them.</span></span> <span data-ttu-id="96482-111">Os modelos implantados podem ser gerenciados n SQL Server Management Studio da mesma forma que modelos multidimensionais.</span><span class="sxs-lookup"><span data-stu-id="96482-111">Deployed models can be managed in SQL Server Management Studio just like multidimensional models.</span></span> <span data-ttu-id="96482-112">Eles também podem ser particionados para processamento otimizado e protegido no nível de linha usando segurança baseada em função.</span><span class="sxs-lookup"><span data-stu-id="96482-112">They can also be partitioned for optimized processing and secured to the row-level by using role based security.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="96482-113">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="96482-113">In This Section</span></span>  
 [<span data-ttu-id="96482-114">Soluções de modelo de tabela &#40;SSAS de tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="96482-114">Tabular Model Solutions &#40;SSAS Tabular&#41;</span></span>](../tabular-model-solutions-ssas-tabular.md)  
  
 [<span data-ttu-id="96482-115">Bancos de dados de modelo de tabela &#40;SSAS de Tabela&#41;</span><span class="sxs-lookup"><span data-stu-id="96482-115">Tabular Model Databases &#40;SSAS Tabular&#41;</span></span>](tabular-model-databases-ssas-tabular.md)  
  
 [<span data-ttu-id="96482-116">Acesso a dados de modelo de tabela</span><span class="sxs-lookup"><span data-stu-id="96482-116">Tabular Model Data Access</span></span>](tabular-model-data-access.md)  
  
  
