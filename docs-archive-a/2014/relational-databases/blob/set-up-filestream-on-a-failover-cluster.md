---
title: Configurar FILESTREAM em um cluster de failover | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.technology: filestream
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], setting up on a failover cluster
ms.assetid: 6721f780-20b7-4109-8ddb-ac327310699e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 29541bbcfd323a85a3fa751f60904fd1a26e1199
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678797"
---
# <a name="set-up-filestream-on-a-failover-cluster"></a><span data-ttu-id="7ab62-102">Configurar FILESTREAM em um cluster de failover</span><span class="sxs-lookup"><span data-stu-id="7ab62-102">Set Up FILESTREAM on a Failover Cluster</span></span>
  <span data-ttu-id="7ab62-103">Este tópico descreve como habilitar FILESTREAM em um cluster de failover.</span><span class="sxs-lookup"><span data-stu-id="7ab62-103">This topic describes how to enable FILESTREAM on a failover cluster.</span></span> <span data-ttu-id="7ab62-104">Antes de tentar este procedimento, você deve entender [clustering de failover](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md) e ter o FILESTREAM habilitado.</span><span class="sxs-lookup"><span data-stu-id="7ab62-104">Before you try this procedure, you should understand [failover clustering](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md) and have FILESTREAM enabled.</span></span> <span data-ttu-id="7ab62-105">Para obter informações sobre como habilitar o FILESTREAM, veja [Habilitar e configurar o FILESTREAM](enable-and-configure-filestream.md).</span><span class="sxs-lookup"><span data-stu-id="7ab62-105">For information about how to enable FILESTREAM, see [Enable and Configure FILESTREAM](enable-and-configure-filestream.md).</span></span>  
  
### <a name="to-set-up-filestream-on-a-failover-cluster"></a><span data-ttu-id="7ab62-106">Para configurar FILESTREAM em um cluster de failover</span><span class="sxs-lookup"><span data-stu-id="7ab62-106">To set up FILESTREAM on a failover cluster</span></span>  
  
1.  <span data-ttu-id="7ab62-107">Configure o nó primário para o cluster de failover.</span><span class="sxs-lookup"><span data-stu-id="7ab62-107">Set up the primary node for the failover cluster.</span></span>  
  
     <span data-ttu-id="7ab62-108">Depois de concluir a configuração, habilite o FILESTREAM no nó primário usando o **SQL Server Configuration Manager**.</span><span class="sxs-lookup"><span data-stu-id="7ab62-108">After the setup finishes, enable FILESTREAM on the primary node by using **SQL Server Configuration Manager**.</span></span> <span data-ttu-id="7ab62-109">Isto habilita as configurações que requerem privilégios Admin do Windows.</span><span class="sxs-lookup"><span data-stu-id="7ab62-109">This enables the settings that require Windows Admin privileges.</span></span> <span data-ttu-id="7ab62-110">Se acesso remoto for necessário, selecione **Permitir que clientes remotos tenham acesso contínuo aos dados FILESTREAM**.</span><span class="sxs-lookup"><span data-stu-id="7ab62-110">If remote access is required, select **Allow remote clients to have streaming access to FILESTREAM data**.</span></span> <span data-ttu-id="7ab62-111">Isso criará um recurso de cluster de compartilhamento de arquivo.</span><span class="sxs-lookup"><span data-stu-id="7ab62-111">This will create a file-share cluster resource.</span></span>  
  
2.  <span data-ttu-id="7ab62-112">Configure um nó passivo.</span><span class="sxs-lookup"><span data-stu-id="7ab62-112">Set up a passive node.</span></span>  
  
     <span data-ttu-id="7ab62-113">Depois de concluir a configuração, habilite o FILESTREAM no nó passivo usando o **SQL Server Configuration Manager**.</span><span class="sxs-lookup"><span data-stu-id="7ab62-113">After the setup finishes, enable FILESTREAM on the passive node by using **SQL Server Configuration Manager**.</span></span> <span data-ttu-id="7ab62-114">O nome especificado para **Nome de Compartilhamento do Windows** deve ser o mesmo em todos os nós no cluster.</span><span class="sxs-lookup"><span data-stu-id="7ab62-114">The name that you specify for **Windows Share Name** must be the same across all nodes in the cluster.</span></span>  
  
3.  <span data-ttu-id="7ab62-115">Para adicionar mais nós passivos, repita a etapa 2.</span><span class="sxs-lookup"><span data-stu-id="7ab62-115">To add more passive nodes, repeat step 2.</span></span>  
  
4.  <span data-ttu-id="7ab62-116">Depois que todos os nós forem adicionados, conclua o processo executando o procedimento armazenado sp_configure em cada instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7ab62-116">After all the nodes are added, complete the process by executing the sp_configure stored procedure on each instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
5.  <span data-ttu-id="7ab62-117">Para adicionar e habilitar nós adicionais ao cluster, em qualquer momento, repita as etapas 2, 3 e 4.</span><span class="sxs-lookup"><span data-stu-id="7ab62-117">To add and enable additional nodes to the cluster at any time, you can repeat steps 2, 3, and 4.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ab62-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7ab62-118">See Also</span></span>  
 <span data-ttu-id="7ab62-119">[Opções de configuração do servidor &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7ab62-119">[Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="7ab62-120">[Criar um novo cluster de failover do SQL Server &#40;Instalação&#41;](../../sql-server/failover-clusters/install/create-a-new-sql-server-failover-cluster-setup.md) </span><span class="sxs-lookup"><span data-stu-id="7ab62-120">[Create a New SQL Server Failover Cluster &#40;Setup&#41;](../../sql-server/failover-clusters/install/create-a-new-sql-server-failover-cluster-setup.md) </span></span>  
 <span data-ttu-id="7ab62-121">[Remover uma Instância de Cluster de Failover do SQL Server &#40;Instalação&#41;](../../sql-server/failover-clusters/install/remove-a-sql-server-failover-cluster-instance-setup.md) </span><span class="sxs-lookup"><span data-stu-id="7ab62-121">[Remove a SQL Server Failover Cluster Instance &#40;Setup&#41;](../../sql-server/failover-clusters/install/remove-a-sql-server-failover-cluster-instance-setup.md) </span></span>  
 [<span data-ttu-id="7ab62-122">Adicionar ou remover nós em um cluster de failover do SQL Server &#40;Instalação&#41;</span><span class="sxs-lookup"><span data-stu-id="7ab62-122">Add or Remove Nodes in a SQL Server Failover Cluster &#40;Setup&#41;</span></span>](../../sql-server/failover-clusters/install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md)  
  
  
