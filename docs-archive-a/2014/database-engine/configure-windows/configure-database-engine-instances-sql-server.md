---
title: Configurar instâncias do Mecanismo de Banco de Dados (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 84e36fcb-2c78-48e8-8e4b-bf784a3ee557
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: af7408ff66d1f0e41369ba095ce51ea590d316e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583841"
---
# <a name="configure-database-engine-instances-sql-server"></a><span data-ttu-id="e298d-102">Configurar instâncias do mecanismo de banco de dados (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e298d-102">Configure Database Engine Instances (SQL Server)</span></span>
  <span data-ttu-id="e298d-103">Cada instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] deve ser configurada para satisfazer os requisitos de desempenho e disponibilidade definidos para os bancos de dados hospedados pela instância.</span><span class="sxs-lookup"><span data-stu-id="e298d-103">Each instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] must be configured to meet the performance and availability requirements defined for the databases hosted by the instance.</span></span> <span data-ttu-id="e298d-104">O [!INCLUDE[ssDE](../../includes/ssde-md.md)] inclui opções de configuração que controlam comportamentos como uso de recurso e a disponibilidade de recursos como auditoria ou recursão de gatilho.</span><span class="sxs-lookup"><span data-stu-id="e298d-104">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] includes configuration options that control behaviors such as resource usage and the availability of features such as auditing or trigger recursion.</span></span>  
  
## <a name="instance-configuration"></a><span data-ttu-id="e298d-105">Configuração de Instância</span><span class="sxs-lookup"><span data-stu-id="e298d-105">Instance Configuration</span></span>  
 <span data-ttu-id="e298d-106">Quando um banco de dados é implantado na produção, em geral há um SLA (acordo em nível de serviço) que define áreas como os níveis de desempenho necessários do banco de dados e o nível de disponibilidade exigido pelo banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e298d-106">When a database is deployed into production there is often a service level agreement (SLA) defining areas such as the levels of performance required from the database and the required availability level of the database.</span></span> <span data-ttu-id="e298d-107">As condições do SLA normalmente orientam requisitos de configuração da instância.</span><span class="sxs-lookup"><span data-stu-id="e298d-107">The terms of the SLA typically drive configuration requirements for the instance.</span></span>  
  
 <span data-ttu-id="e298d-108">Uma instância costuma ser configurada logo após ser instalada.</span><span class="sxs-lookup"><span data-stu-id="e298d-108">An instance is usually configured immediately after it has been installed.</span></span> <span data-ttu-id="e298d-109">A configuração inicial normalmente é determinada pelos requisitos de SLA dos tipos de bancos de dados planejados para serem implantados na instância.</span><span class="sxs-lookup"><span data-stu-id="e298d-109">The initial configuration is usually determined by the SLA requirements of the types of databases planned to be deployed to the instance.</span></span> <span data-ttu-id="e298d-110">Depois que os bancos de dados forem implantados, os administradores de banco de dados monitorarão o desempenho da instância e ajustarão os parâmetros de configuração, quando necessário, se a métrica de desempenho mostrar que a instância não está satisfazendo os requisitos de SLA.</span><span class="sxs-lookup"><span data-stu-id="e298d-110">After the databases have been deployed, the database administrators monitor the performance of the instance and adjust the configuration settings as needed if the performance metrics show the instance is not meeting the SLA requirements.</span></span>  
  
## <a name="configuration-tasks"></a><span data-ttu-id="e298d-111">Tarefas de configuração</span><span class="sxs-lookup"><span data-stu-id="e298d-111">Configuration Tasks</span></span>  
  
|<span data-ttu-id="e298d-112">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="e298d-112">Task Description</span></span>|<span data-ttu-id="e298d-113">Tópico</span><span class="sxs-lookup"><span data-stu-id="e298d-113">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="e298d-114">Descreve as várias opções de configuração de instância e como exibir ou alterar essas opções.</span><span class="sxs-lookup"><span data-stu-id="e298d-114">Describes the various instance configuration options and how to view or change these options.</span></span>|[<span data-ttu-id="e298d-115">Opções de configuração do servidor &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e298d-115">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)|  
|<span data-ttu-id="e298d-116">Descreve como exibir e configurar os locais padrão de novos arquivos de log e de dados na instância.</span><span class="sxs-lookup"><span data-stu-id="e298d-116">Describes how to view and configure the default locations of new data and log files in the instance.</span></span>|[<span data-ttu-id="e298d-117">Exibir ou alterar os locais padrão de arquivos de log e de dados &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="e298d-117">View or Change the Default Locations for Data and Log Files &#40;SQL Server Management Studio&#41;</span></span>](view-or-change-the-default-locations-for-data-and-log-files.md)|  
|<span data-ttu-id="e298d-118">Descreve como configurar o SQL Server para usar o soft-NUMA.</span><span class="sxs-lookup"><span data-stu-id="e298d-118">Describes how to configure SQL Server to use soft-NUMA.</span></span>|[<span data-ttu-id="e298d-119">Configurar SQL Server para usar &#40;de soft-NUMA SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e298d-119">Configure SQL Server to Use Soft-NUMA &#40;SQL Server&#41;</span></span>](soft-numa-sql-server.md)|  
|<span data-ttu-id="e298d-120">Descreve como mapear uma porta TCP/IP para afinidade de nó NUMA (acesso não uniforme a memória).</span><span class="sxs-lookup"><span data-stu-id="e298d-120">Describes how to map a TCP/IP port to non-uniform memory access (NUMA) node affinity.</span></span>|[<span data-ttu-id="e298d-121">Mapear portas TCP/IP para nós NUMA &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e298d-121">Map TCP IP Ports to NUMA Nodes &#40;SQL Server&#41;</span></span>](map-tcp-ip-ports-to-numa-nodes-sql-server.md)|  
|<span data-ttu-id="e298d-122">Descreve como habilitar a política Bloquear Páginas na Memória do Windows</span><span class="sxs-lookup"><span data-stu-id="e298d-122">Describes how to enable the Windows Lock Pages In Memory policy.</span></span> <span data-ttu-id="e298d-123">Essa política determina quais contas podem usar um processo para manter dados na memória física, impedindo que o sistema faça a paginação dos dados para a memória virtual em disco.</span><span class="sxs-lookup"><span data-stu-id="e298d-123">This policy determines which accounts can use a process to keep data in physical memory, preventing the system from paging the data to virtual memory on disk.</span></span>|[<span data-ttu-id="e298d-124">Habilitar a opção Bloquear Páginas na Memória &#40;Windows&#41;</span><span class="sxs-lookup"><span data-stu-id="e298d-124">Enable the Lock Pages in Memory Option &#40;Windows&#41;</span></span>](enable-the-lock-pages-in-memory-option-windows.md)|  
  
## <a name="see-also"></a><span data-ttu-id="e298d-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e298d-125">See Also</span></span>  
 [<span data-ttu-id="e298d-126">Instâncias do mecanismo de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e298d-126">Database Engine Instances &#40;SQL Server&#41;</span></span>](database-engine-instances-sql-server.md)  
  
  