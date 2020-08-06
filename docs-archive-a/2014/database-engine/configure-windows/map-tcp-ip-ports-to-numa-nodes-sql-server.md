---
title: Mapear portas TCP/IP para nós NUMA (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- NUMA
- memory [SQL Server], NUMA
- affinity NUMA
- ports [SQL Server], working with NUMA
- CPU [SQL Server], NUMA support
- NUMA, How to map a port to a NUMA node
- NUMA affinity
- TCP/IP [SQL Server], NUMA support
- non-uniform memory access
ms.assetid: 07727642-0266-4cbc-8c55-3c367e4458ca
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cf4a1bd7e02719d3884011ad3faa20a1ccc6466a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678962"
---
# <a name="map-tcp-ip-ports-to-numa-nodes-sql-server"></a><span data-ttu-id="af599-102">Mapear portas TCP/IP para nós NUMA (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="af599-102">Map TCP IP Ports to NUMA Nodes (SQL Server)</span></span>
  <span data-ttu-id="af599-103">Este tópico descreve como mapear portas TCP/IP para nós NUMA (acesso não uniforme a memória) usando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="af599-103">This topic describes how to map TCP/IP ports to non-uniform memory access (NUMA) nodes by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="af599-104">Na inicialização, o [!INCLUDE[ssDE](../../includes/ssde-md.md)] grava as informações de nó no log de erros.</span><span class="sxs-lookup"><span data-stu-id="af599-104">On startup, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] writes the node information to the error log.</span></span>  
  
 <span data-ttu-id="af599-105">Para determinar o número de nó do nó que você quer usar, leia as informações do nó de log de erros ou da exibição **sys.dm_os_schedulers** .</span><span class="sxs-lookup"><span data-stu-id="af599-105">To determine the node number of the node you want to use, either read the node information from the error log, or from the **sys.dm_os_schedulers** view.</span></span> <span data-ttu-id="af599-106">Para definir um endereço de TCP/IP e portar para nós únicos ou múltiplos, acrescente um bitmap de identificação de nó (uma máscara de afinidade) em parênteses depois do número da porta.</span><span class="sxs-lookup"><span data-stu-id="af599-106">To set a TCP/IP address and port to single or multiple nodes, append a node identification bitmap (an affinity mask) in brackets after the port number.</span></span> <span data-ttu-id="af599-107">Podem ser especificados nós em formato decimal ou hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="af599-107">Nodes can be specified in either decimal or hexadecimal format.</span></span> <span data-ttu-id="af599-108">Para criar o bitmap, primeiro numere os nós da direita para a esquerda iniciando com zero, como em 76543210.</span><span class="sxs-lookup"><span data-stu-id="af599-108">To create the bitmap, first number the nodes from right to left starting with zero, as in 76543210.</span></span> <span data-ttu-id="af599-109">Crie uma representação binária da lista de nós, provendo 1 para os nós que você quer usar e 0 para os nós que você não quer usar.</span><span class="sxs-lookup"><span data-stu-id="af599-109">Create a binary representation of the node list, providing 1 for nodes you want to use, and 0 for nodes you do not want to use.</span></span> <span data-ttu-id="af599-110">Por exemplo, para usar nós NUMA 0, 2 e 5, especifique 00100101.</span><span class="sxs-lookup"><span data-stu-id="af599-110">For example, to use NUMA nodes 0, 2, and 5, specify 00100101.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="af599-111">Número de nó NUMA</span><span class="sxs-lookup"><span data-stu-id="af599-111">NUMA node number</span></span>|<span data-ttu-id="af599-112">76543210</span><span class="sxs-lookup"><span data-stu-id="af599-112">76543210</span></span>|  
|<span data-ttu-id="af599-113">Mascare 0, 2 e 5 contando da direita</span><span class="sxs-lookup"><span data-stu-id="af599-113">Mask for 0, 2, and 5 counting from right</span></span>|<span data-ttu-id="af599-114">00100101</span><span class="sxs-lookup"><span data-stu-id="af599-114">00100101</span></span>|  
  
 <span data-ttu-id="af599-115">Converta a representação binária (00100101) em `[37]`decimal, ou `[0x25]`hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="af599-115">Convert the binary representation (00100101), into decimal `[37]`, or hexadecimal `[0x25]`.</span></span> <span data-ttu-id="af599-116">Para escutar em todos os nós, não forneça nenhum identificador de nó.</span><span class="sxs-lookup"><span data-stu-id="af599-116">To listen on all nodes, provide no node identifier.</span></span>  
  
 <span data-ttu-id="af599-117">Se uma porta for mapeada para mais de um nó NUMA, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] atribuirá conexões para nós numa forma de rodízio sem tentar equilibrar carga pelos nós.</span><span class="sxs-lookup"><span data-stu-id="af599-117">If a port is mapped to more than one NUMA node, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] assigns connections to nodes in a round-robin fashion without attempting to balance load across the nodes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="af599-118">Para habilitar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para escutar várias portas TCP para cada endereço IP, consulte [Configurar o Mecanismo de Banco de Dados para escutar em várias portas TCP](configure-the-database-engine-to-listen-on-multiple-tcp-ports.md).</span><span class="sxs-lookup"><span data-stu-id="af599-118">To enable [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to listen on multiple TCP ports for each IP address, see [Configure the Database Engine to Listen on Multiple TCP Ports](configure-the-database-engine-to-listen-on-multiple-tcp-ports.md).</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="af599-119">Usando o SQL Server Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="af599-119">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-map-a-tcpip-port-to-a-numa-node"></a><span data-ttu-id="af599-120">Para mapear uma porta de TCP/IP para um nó NUMA</span><span class="sxs-lookup"><span data-stu-id="af599-120">To map a TCP/IP port to a NUMA node</span></span>  
  
1.  <span data-ttu-id="af599-121">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expanda **Configuração de Rede do SQL Server** e clique em **Protocolos para** *\<instance name>* .</span><span class="sxs-lookup"><span data-stu-id="af599-121">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expand **SQL Server Network Configuration**, and then click **Protocols for** *\<instance name>*.</span></span>  
  
2.  <span data-ttu-id="af599-122">No painel de detalhes, clique duas vezes no **TCP/IP**.</span><span class="sxs-lookup"><span data-stu-id="af599-122">In the details pane, double-click **TCP/IP**.</span></span>  
  
3.  <span data-ttu-id="af599-123">Na guia **IP Addresses** , na seção que corresponde ao endereço de IP para configurar, na caixa **TCP Port** , adicione o identificador do nó NUMA em parênteses depois do número da porta.</span><span class="sxs-lookup"><span data-stu-id="af599-123">On the **IP Addresses** tab, in the section corresponding to the IP address to configure, in the **TCP Port** box, add the NUMA node identifier in brackets after the port number.</span></span> <span data-ttu-id="af599-124">Por exemplo, para TCP porta 1500 e nós 0, 2 e 5, use `1500[37]` ou `1500[0x25]`.</span><span class="sxs-lookup"><span data-stu-id="af599-124">For example, for TCP port 1500 and nodes 0, 2, and 5, use `1500[37]`, or `1500[0x25]`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af599-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="af599-125">See Also</span></span>  
 [<span data-ttu-id="af599-126">Configurar SQL Server para usar &#40;de soft-NUMA SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="af599-126">Configure SQL Server to Use Soft-NUMA &#40;SQL Server&#41;</span></span>](soft-numa-sql-server.md)  
  
  
