---
title: Exibindo e parando os pacotes em execução no servidor de Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- packages [Integration Services], managing
- managing running packages [Integration Services]
- packages [Integration Services], running
- running package [Integration Services], managing
ms.assetid: 11bf44e6-f6b0-475f-b816-40e914dbac80
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6e63839d4ab5d8d50f7d86eea05c8d58107d6799
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582514"
---
# <a name="viewing-and-stopping-packages-running-on-the-integration-services-server"></a><span data-ttu-id="42bf7-102">Exibindo e parando pacotes que são executados no servidor do Integration Services</span><span class="sxs-lookup"><span data-stu-id="42bf7-102">Viewing and Stopping Packages Running on the Integration Services Server</span></span>
  <span data-ttu-id="42bf7-103">O banco de dados do `SSISDB` armazena o histórico da execução em tabelas internas que não são visíveis aos usuários.</span><span class="sxs-lookup"><span data-stu-id="42bf7-103">The `SSISDB` database stores execution history in internal tables that are not visible to users.</span></span> <span data-ttu-id="42bf7-104">Porém, ele expõe as informações necessárias por meio de exibições públicas que você pode consultar.</span><span class="sxs-lookup"><span data-stu-id="42bf7-104">However it exposes the information that you need through public views that you can query.</span></span> <span data-ttu-id="42bf7-105">Ele também fornece procedimentos armazenados que você pode chamar para executar tarefas comuns relacionadas a pacotes.</span><span class="sxs-lookup"><span data-stu-id="42bf7-105">It also provides stored procedures that you can call to perform common tasks related to packages.</span></span>  
  
 <span data-ttu-id="42bf7-106">Normalmente você gerencia objetos do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no servidor no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42bf7-106">Typically you manage [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] objects on the server in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="42bf7-107">No entanto, você também pode consultar as exibições de banco de dados e chamar os procedimentos armazenados diretamente, ou escrever código personalizado que chame a API gerenciada.</span><span class="sxs-lookup"><span data-stu-id="42bf7-107">However you can also query the database views and call the stored procedures directly, or write custom code that calls the managed API.</span></span> [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="42bf7-108">e a API gerenciada consultam as exibições e chamam os procedimentos armazenados para executar muitas de suas tarefas.</span><span class="sxs-lookup"><span data-stu-id="42bf7-108">and the managed API query the views and call the stored procedures to perform many of their tasks.</span></span> <span data-ttu-id="42bf7-109">Por exemplo, você pode exibir a lista de pacotes do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que estão em execução atualmente no servidor e solicitar a interrupção de pacotes, se necessário.</span><span class="sxs-lookup"><span data-stu-id="42bf7-109">For example, you can view the list of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages that are currently running on the server, and request packages to stop if you have to.</span></span>  
  
## <a name="viewing-the-list-of-running-packages"></a><span data-ttu-id="42bf7-110">Exibindo a lista de pacotes em execução</span><span class="sxs-lookup"><span data-stu-id="42bf7-110">Viewing the List of Running Packages</span></span>  
 <span data-ttu-id="42bf7-111">É possível exibir a lista de pacotes que estão sendo executados no momento no servidor na caixa de diálogo **Operações Ativas** .</span><span class="sxs-lookup"><span data-stu-id="42bf7-111">You can view the list of packages that are currently running on the server in the **Active Operations** dialog box.</span></span> <span data-ttu-id="42bf7-112">Para obter mais informações, consulte [Active Operations Dialog Box](../../2014/integration-services/active-operations-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="42bf7-112">For more information, see [Active Operations Dialog Box](../../2014/integration-services/active-operations-dialog-box.md).</span></span>  
  
 <span data-ttu-id="42bf7-113">Para obter informações sobre os outros métodos que podem ser usados para exibir a lista de pacotes em execução, consulte os tópicos a seguir.</span><span class="sxs-lookup"><span data-stu-id="42bf7-113">For information about the other methods that you can use to view the list of running packages, see the following topics.</span></span>  
  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="42bf7-114">acesso</span><span class="sxs-lookup"><span data-stu-id="42bf7-114">access</span></span>  
 <span data-ttu-id="42bf7-115">Para exibir a lista de pacotes em execução no servidor, consulte a exibição [catalog.executions &#40;Banco de Dados SSISDB&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database) para obter pacotes que têm um status 2.</span><span class="sxs-lookup"><span data-stu-id="42bf7-115">To view the list of packages that are running on the server, query the view, [catalog.executions &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database) for packages that have a status of 2.</span></span>  
  
 <span data-ttu-id="42bf7-116">Acesso programático por meio de API gerenciada</span><span class="sxs-lookup"><span data-stu-id="42bf7-116">Programmatic access through the managed API</span></span>  
 <span data-ttu-id="42bf7-117">Consulte o namespace <xref:Microsoft.SqlServer.Management.IntegrationServices> e suas classes.</span><span class="sxs-lookup"><span data-stu-id="42bf7-117">See the <xref:Microsoft.SqlServer.Management.IntegrationServices> namespace and its classes.</span></span>  
  
## <a name="stopping-a-running-package"></a><span data-ttu-id="42bf7-118">Interrompendo um pacote em execução</span><span class="sxs-lookup"><span data-stu-id="42bf7-118">Stopping a Running Package</span></span>  
 <span data-ttu-id="42bf7-119">Você pode solicitar um pacote em execução a ser interrompido na caixa de diálogo **Operações Ativas** .</span><span class="sxs-lookup"><span data-stu-id="42bf7-119">You can request a running package to stop in the **Active Operations** dialog box.</span></span> <span data-ttu-id="42bf7-120">Para obter mais informações, consulte [Active Operations Dialog Box](../../2014/integration-services/active-operations-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="42bf7-120">For more information, see [Active Operations Dialog Box](../../2014/integration-services/active-operations-dialog-box.md).</span></span>  
  
 <span data-ttu-id="42bf7-121">Para obter informações sobre os outros métodos que podem ser usados para interromper um pacote em execução, consulte os tópicos a seguir.</span><span class="sxs-lookup"><span data-stu-id="42bf7-121">For information about the other methods that you can use to stop a running package, see the following topics.</span></span>  
  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="42bf7-122">acesso</span><span class="sxs-lookup"><span data-stu-id="42bf7-122">access</span></span>  
 <span data-ttu-id="42bf7-123">Para interromper um pacote em execução no servidor, chame o procedimento armazenado, [catalog.stop_operation &#40;Banco de Dados SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-stop-operation-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="42bf7-123">To stop a package that is running on the server, call the stored procedure, [catalog.stop_operation &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-stop-operation-ssisdb-database).</span></span>  
  
 <span data-ttu-id="42bf7-124">Acesso programático por meio de API gerenciada</span><span class="sxs-lookup"><span data-stu-id="42bf7-124">Programmatic access through the managed API</span></span>  
 <span data-ttu-id="42bf7-125">Consulte o namespace <xref:Microsoft.SqlServer.Management.IntegrationServices> e suas classes.</span><span class="sxs-lookup"><span data-stu-id="42bf7-125">See the <xref:Microsoft.SqlServer.Management.IntegrationServices> namespace and its classes.</span></span>  
  
## <a name="viewing-the-history-of-packages-that-have-run"></a><span data-ttu-id="42bf7-126">Exibindo o histórico de pacotes executados</span><span class="sxs-lookup"><span data-stu-id="42bf7-126">Viewing the History of Packages That Have Run</span></span>  
 <span data-ttu-id="42bf7-127">Para exibir o histórico de pacotes executados no [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], use o relatório **Todas as Execuções** .</span><span class="sxs-lookup"><span data-stu-id="42bf7-127">To view the history of packages that have run in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], use the **All Executions** report.</span></span> <span data-ttu-id="42bf7-128">Para obter mais informações sobre o relatório **Todas as Execuções** e outros relatórios padrão, consulte [Relatórios do servidor do Integration Services](../../2014/integration-services/reports-for-the-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="42bf7-128">For more information on the **All Executions** report and other standard reports, see [Reports for the Integration Services Server](../../2014/integration-services/reports-for-the-integration-services-server.md).</span></span>  
  
 <span data-ttu-id="42bf7-129">Para obter informações sobre os outros métodos que podem ser usados para exibir o histórico de pacotes em execução, consulte os tópicos a seguir.</span><span class="sxs-lookup"><span data-stu-id="42bf7-129">For information about the other methods that you can use to view the history of running packages, see the following topics.</span></span>  
  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="42bf7-130">acesso</span><span class="sxs-lookup"><span data-stu-id="42bf7-130">access</span></span>  
 <span data-ttu-id="42bf7-131">Para exibir informações sobre os pacotes que foram executados, consulte a exibição [catalog.executions &#40;Banco de Dados SSISDB&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="42bf7-131">To view information about packages that have run, query the view, [catalog.executions &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database).</span></span>  
  
 <span data-ttu-id="42bf7-132">Acesso programático por meio de API gerenciada</span><span class="sxs-lookup"><span data-stu-id="42bf7-132">Programmatic access through the managed API</span></span>  
 <span data-ttu-id="42bf7-133">Consulte o namespace <xref:Microsoft.SqlServer.Management.IntegrationServices> e suas classes.</span><span class="sxs-lookup"><span data-stu-id="42bf7-133">See the <xref:Microsoft.SqlServer.Management.IntegrationServices> namespace and its classes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42bf7-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="42bf7-134">See Also</span></span>  
 <span data-ttu-id="42bf7-135">[Execução de projetos e pacotes](packages/run-integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="42bf7-135">[Execution of Projects and Packages](packages/run-integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="42bf7-136">Relatórios para solução de problemas de execução de pacote</span><span class="sxs-lookup"><span data-stu-id="42bf7-136">Troubleshooting Reports for Package Execution</span></span>](troubleshooting/troubleshooting-reports-for-package-execution.md)  
  
  
