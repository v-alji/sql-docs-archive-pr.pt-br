---
title: Renomear uma instância do cluster de failover do SQL Server (Configuração) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- clusters [SQL Server], removing failover clustered instance
- failover clustering [SQL Server], removing failover clustered instance
- uninstalling failover clustered instances
- removing failover clustered instances
ms.assetid: bf63353b-69cf-4c5c-98ea-7b151e36537f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a4d0ae492481b0677be2d2692fbda0fbc8eb604b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573595"
---
# <a name="remove-a-sql-server-failover-cluster-instance-setup"></a><span data-ttu-id="033e4-102">Remover uma instância de cluster de failover do SQL Server (instalação)</span><span class="sxs-lookup"><span data-stu-id="033e4-102">Remove a SQL Server Failover Cluster Instance (Setup)</span></span>
  <span data-ttu-id="033e4-103">Use esse procedimento para desinstalar uma instância clusterizada de failover do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="033e4-103">Use this procedure to uninstall a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover clustered instance.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="033e4-104">Para atualizar ou remover um cluster de failover do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , você deve ter privilégios de administrador local com permissão para efetuar logon como um serviço em todos os nós do cluster de failover.</span><span class="sxs-lookup"><span data-stu-id="033e4-104">To update or remove a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover cluster, you must be a local administrator with permission to login as a service on all nodes of the failover cluster.</span></span>  
  
 <span data-ttu-id="033e4-105">**Antes de começar**</span><span class="sxs-lookup"><span data-stu-id="033e4-105">**Before you begin**</span></span>  
  
 <span data-ttu-id="033e4-106">Considere os seguintes pontos importantes antes de desinstalar um cluster de failover do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="033e4-106">Consider the following important points before you uninstall a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover cluster:</span></span>  
  
-   <span data-ttu-id="033e4-107">Se o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client for desinstalado por acidente, os recursos do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] não poderão ser iniciados.</span><span class="sxs-lookup"><span data-stu-id="033e4-107">If [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client is uninstalled by accident, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resources will fail to start.</span></span> <span data-ttu-id="033e4-108">Para reinstalar o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, execute o programa de instalação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para instalar os pré-requisitos do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="033e4-108">To reinstall [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, run the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Setup program to install [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] prerequisites.</span></span>  
  
-   <span data-ttu-id="033e4-109">Se você optar por desinstalar um cluster de failover que tenha mais de um recurso de cluster IP do SQL, deverá remover os recursos IP adicionais do SQL usando o administrador de cluster.</span><span class="sxs-lookup"><span data-stu-id="033e4-109">If you uninstall a failover cluster that has more than one SQL IP cluster resource, you must remove the additional SQL IP resources using cluster administrator.</span></span>  
  
 <span data-ttu-id="033e4-110">Para obter informações sobre a sintaxe do prompt de comando, consulte [instalar SQL Server 2014 no prompt de comando](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="033e4-110">For information about command prompt syntax, see [Install SQL Server 2014 from the Command Prompt](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span></span>  
  
### <a name="to-uninstall-a-ssnoversion-failover-cluster"></a><span data-ttu-id="033e4-111">Para desinstalar um cluster de failover do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="033e4-111">To uninstall a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover cluster</span></span>  
  
1.  <span data-ttu-id="033e4-112">Para desinstalar um cluster de failover do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , use a função Remover Nó fornecida na instalação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para remover cada nó individualmente.</span><span class="sxs-lookup"><span data-stu-id="033e4-112">To uninstall a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover cluster, use the Remove Node functionality provided by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Setup to remove each node individually.</span></span> <span data-ttu-id="033e4-113">Para obter mais informações, consulte [Adicionar ou remover nós em um cluster de failover do SQL Server &#40;Instalação&#41;](add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).</span><span class="sxs-lookup"><span data-stu-id="033e4-113">For more information, see [Add or Remove Nodes in a SQL Server Failover Cluster &#40;Setup&#41;](add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="033e4-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="033e4-114">See Also</span></span>  
 [<span data-ttu-id="033e4-115">Exibir e ler arquivos de log da Instalação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="033e4-115">View and Read SQL Server Setup Log Files</span></span>](../../../database-engine/install-windows/view-and-read-sql-server-setup-log-files.md)  
  
  
