---
title: Configuração de rede de cluster | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- cluster network selection, Setup
- cluster network selection
ms.assetid: 579482ef-a023-45b2-9176-b4a4188adf9d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 17ab563817a3b9b476dfd566f4a7f2beda98ca26
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573503"
---
# <a name="cluster-network-configuration"></a><span data-ttu-id="5a938-102">Configuração de rede do cluster</span><span class="sxs-lookup"><span data-stu-id="5a938-102">Cluster Network Configuration</span></span>
  <span data-ttu-id="5a938-103">Use a página **Seleção de Rede de Cluster** para especificar os recursos de rede para sua instância de cluster de failover.</span><span class="sxs-lookup"><span data-stu-id="5a938-103">Use the **Cluster Network Selection** page to specify the network resources for your failover cluster instance.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5a938-104">Opções</span><span class="sxs-lookup"><span data-stu-id="5a938-104">Options</span></span>  
 <span data-ttu-id="5a938-105">\*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Nome de rede do cluster de failover\*\* -esse é o nome usado para identificar a instância de cluster de failover na rede.</span><span class="sxs-lookup"><span data-stu-id="5a938-105">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Failover Cluster Network Name** - This is the name used to identify your failover cluster instance on the network.</span></span>  
  
 <span data-ttu-id="5a938-106">**Configurações de Rede** — Especifique o tipo e o endereço IP da instância de cluster de failover.</span><span class="sxs-lookup"><span data-stu-id="5a938-106">**Network Settings** - Specify the IP type and IP address for your failover cluster instance.</span></span>  
  
 <span data-ttu-id="5a938-107">Durante as operações Adicionar Nó e Remover Nó, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] exibe uma lista somente leitura dos endereços IP existentes para o cluster de failover do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5a938-107">During the Add Node and Remove Node operations, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] displays a read-only list of the existing IP addresses for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster.</span></span>  
  
-   <span data-ttu-id="5a938-108">Instalação Integrada:</span><span class="sxs-lookup"><span data-stu-id="5a938-108">Integrated Install:</span></span>  
  
    -   <span data-ttu-id="5a938-109">Se você estiver adicionando um nó que tenha suporte para um conjunto idêntico de sub-redes de rede com suporte dos nós existentes do cluster de failover do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , nenhum outro endereço IP poderá ser adicionado.</span><span class="sxs-lookup"><span data-stu-id="5a938-109">If you are adding a node that supports an identical set of network subnets supported by the existing nodes of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, no additional IP addresses can be added.</span></span> <span data-ttu-id="5a938-110">A configuração de dependência permanece inalterada.</span><span class="sxs-lookup"><span data-stu-id="5a938-110">The dependency setting remains unchanged.</span></span>  
  
    -   <span data-ttu-id="5a938-111">Se você estiver adicionando um nó que tenha um subconjunto das sub-redes com suporte dos nós existentes no cluster de failover do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , nenhum outro recurso de endereço IP poderá ser adicionado.</span><span class="sxs-lookup"><span data-stu-id="5a938-111">If you are adding a node that supports a subset of the subnets supported by the existing nodes on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, no additional IP address resources can be added.</span></span> <span data-ttu-id="5a938-112">A dependência de recurso de endereço IP é definida como OR para refletir que todos os endereços IP especificados não sejam válidos em todos os nós de cluster.</span><span class="sxs-lookup"><span data-stu-id="5a938-112">The IP address resource dependency is set to OR to reflect that all the specified IP addresses are not valid on all the cluster nodes.</span></span>  
  
    -   <span data-ttu-id="5a938-113">Se você estiver adicionando um nó que tenha suporte para sub-redes, além das sub-redes já com suporte dos nós existentes no cluster de failover do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , terá a opção de adicionar novos endereços IP válidos.</span><span class="sxs-lookup"><span data-stu-id="5a938-113">If you are adding a node that supports subnets in addition to the subnets already supported by the existing nodes on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, you have the option of adding new valid IP addresses.</span></span> <span data-ttu-id="5a938-114">Se novos endereços IP forem especificados, a dependência de recurso de endereço IP será definida como OR para refletir que todos os endereços IP especificados não sejam válidos em todos os nós de cluster.</span><span class="sxs-lookup"><span data-stu-id="5a938-114">If new IP addresses are specified, the IP address resource dependency is set to OR to reflect that all the specified IP addresses are not valid on all the cluster nodes.</span></span>  
  
    -   <span data-ttu-id="5a938-115">Se você estiver adicionando um nó que tenha suporte para mais sub-redes de rede, mas que não tenha suporte para nenhuma das sub-redes aceitas pelos nós existentes no cluster de failover do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , será necessário adicionar mais endereços IP.</span><span class="sxs-lookup"><span data-stu-id="5a938-115">If you are adding a node that supports additional network subnets, but supports none of the subnets supported by the existing nodes on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, you are required to add additional IP addresses.</span></span> <span data-ttu-id="5a938-116">A dependência de recurso de endereço IP é definida como OR para refletir que todos os endereços IP especificados não sejam válidos em todos os nós de cluster.</span><span class="sxs-lookup"><span data-stu-id="5a938-116">The IP address resource dependency is set to OR to reflect that all the specified IP addresses are not valid on all the cluster nodes.</span></span>  
  
-   <span data-ttu-id="5a938-117">Instalação Avançada: Durante a etapa Concluir da instalação, especifique o endereço IP de todos os nós e sub-redes da instância de cluster de failover.</span><span class="sxs-lookup"><span data-stu-id="5a938-117">Advanced Install: During the Complete step of the installation, specify the IP address for all the nodes and subnets for your failover cluster instance.</span></span> <span data-ttu-id="5a938-118">Você pode especificar vários endereços IP para um cluster de failover de várias sub-redes, mas há suporte para apenas um endereço IP por sub-rede.</span><span class="sxs-lookup"><span data-stu-id="5a938-118">You can specify multiple IP addresses for a multi-subnet failover cluster, but only one IP address per subnet is supported.</span></span> <span data-ttu-id="5a938-119">Cada nó preparado deve ser um possível proprietário de pelo menos um endereço IP.</span><span class="sxs-lookup"><span data-stu-id="5a938-119">Every prepared node should be an owner of at least one IP address.</span></span> <span data-ttu-id="5a938-120">Se você tiver várias sub-redes em seu cluster de failover do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , será solicitado que defina a dependência de recurso de endereço IP como OR.Remove Node:</span><span class="sxs-lookup"><span data-stu-id="5a938-120">If you have multiple subnets in your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, you are prompted to set the IP address resource dependency to OR.Remove Node:</span></span>  
  
    -   <span data-ttu-id="5a938-121">Se houver suporte para os endereços IP restantes em todos os outros nós, você deverá definir a dependência de recurso de endereço IP como AND.</span><span class="sxs-lookup"><span data-stu-id="5a938-121">If the remaining IP addresses are supported on all the remaining nodes, you are prompted to set the IP address resource dependencyto AND.</span></span>  
  
    -   <span data-ttu-id="5a938-122">Se não houver suporte para os endereços IP restantes em todos os outros nós, a dependência de recurso de endereço IP será deixada como OR.</span><span class="sxs-lookup"><span data-stu-id="5a938-122">If the remaining IP addresses are not supported on all the remaining nodes, the IP address resource dependency is left as OR.</span></span>  
  
  
