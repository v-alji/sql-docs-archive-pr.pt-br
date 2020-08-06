---
title: Monitoramento de execuções de pacote e outras operações | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: cbbcd79f-ab9b-46ec-84cb-4821c1d16b99
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 628b62d9c8e01d0dc0bf641551de67c3838a4504
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583722"
---
# <a name="monitoring-for-package-executions-and-other-operations"></a><span data-ttu-id="caaaf-102">Monitorando execuções de pacotes e outras operações</span><span class="sxs-lookup"><span data-stu-id="caaaf-102">Monitoring for Package Executions and Other Operations</span></span>
  <span data-ttu-id="caaaf-103">Você pode monitorar execuções de pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , validações de projeto e outras operações usando uma ou mais das ferramentas a seguir.</span><span class="sxs-lookup"><span data-stu-id="caaaf-103">You can monitor [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package executions, project validations, and other operations by using one of more of the following tools.</span></span> <span data-ttu-id="caaaf-104">Algumas ferramentas, como toques de dados, estão disponíveis somente para os projetos que são implantados no servidor do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="caaaf-104">Certain tools such as data taps are available only for projects that are deployed to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
-   <span data-ttu-id="caaaf-105">Logs</span><span class="sxs-lookup"><span data-stu-id="caaaf-105">Logs</span></span>  
  
     <span data-ttu-id="caaaf-106">Para obter mais informações, consulte [Log do SSIS &#40;Integration Services&#41;](integration-services-ssis-logging.md).</span><span class="sxs-lookup"><span data-stu-id="caaaf-106">For more information, see [Integration Services &#40;SSIS&#41; Logging](integration-services-ssis-logging.md).</span></span>  
  
-   <span data-ttu-id="caaaf-107">Relatórios</span><span class="sxs-lookup"><span data-stu-id="caaaf-107">Reports</span></span>  
  
     <span data-ttu-id="caaaf-108">Para saber mais, confira [Reports for the Integration Services Server](../reports-for-the-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="caaaf-108">For more information, see [Reports for the Integration Services Server](../reports-for-the-integration-services-server.md).</span></span>  
  
-   <span data-ttu-id="caaaf-109">Exibições</span><span class="sxs-lookup"><span data-stu-id="caaaf-109">Views</span></span>  
  
     <span data-ttu-id="caaaf-110">Para obter mais informações, consulte [Exibições &#40;Catálogo do Integration Services&#41;](/sql/integration-services/system-views/views-integration-services-catalog).</span><span class="sxs-lookup"><span data-stu-id="caaaf-110">For more information, see [Views &#40;Integration Services Catalog&#41;](/sql/integration-services/system-views/views-integration-services-catalog).</span></span>  
  
-   <span data-ttu-id="caaaf-111">Contadores de desempenho</span><span class="sxs-lookup"><span data-stu-id="caaaf-111">Performance counters</span></span>  
  
     <span data-ttu-id="caaaf-112">Para obter mais informações, consulte [Performance Counters](performance-counters.md).</span><span class="sxs-lookup"><span data-stu-id="caaaf-112">For more information, see [Performance Counters](performance-counters.md).</span></span>  
  
-   <span data-ttu-id="caaaf-113">Toques de dados</span><span class="sxs-lookup"><span data-stu-id="caaaf-113">Data taps</span></span>  
  
## <a name="operation-types"></a><span data-ttu-id="caaaf-114">Tipos de operação</span><span class="sxs-lookup"><span data-stu-id="caaaf-114">Operation Types</span></span>  
 <span data-ttu-id="caaaf-115">São monitorados vários tipos diferentes de operações no catálogo `SSISDB`, no servidor do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="caaaf-115">Several different types of operations are monitored in the `SSISDB` catalog, on the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="caaaf-116">Cada operação pode ter várias mensagens associadas a ela.</span><span class="sxs-lookup"><span data-stu-id="caaaf-116">Each operation can have multiple messages associated with it.</span></span> <span data-ttu-id="caaaf-117">Cada mensagem pode ser classificada em um de vários tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="caaaf-117">Each message can be classified into one of several different types.</span></span> <span data-ttu-id="caaaf-118">Por exemplo, uma mensagem pode ser de tipo Informações, Aviso ou Erro.</span><span class="sxs-lookup"><span data-stu-id="caaaf-118">For example, a message can be of type Information, Warning, or Error.</span></span> <span data-ttu-id="caaaf-119">Para obter a lista completa dos tipos de mensagem, consulte a documentação da exibição [catalog.operation_messages &#40;Banco de Dados do SSISDB&#41;](/sql/integration-services/system-views/catalog-operation-messages-ssisdb-database) do Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="caaaf-119">For the full list of message types, see the documentation for the Transact-SQL [catalog.operation_messages &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-operation-messages-ssisdb-database) view.</span></span> <span data-ttu-id="caaaf-120">Para ver uma lista completa dos tipos de operação, consulte [catalog.operations &#40;Banco de Dados do SSISDB&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="caaaf-120">For a full list of the operations types, see [catalog.operations &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database).</span></span>  
  
 <span data-ttu-id="caaaf-121">São usados nove tipos de status diferentes para indicar o status de uma operação.</span><span class="sxs-lookup"><span data-stu-id="caaaf-121">Nine different status types are used to indicate the status of an operation.</span></span> <span data-ttu-id="caaaf-122">Para ver uma lista completa dos tipos de status, consulte a exibição [catalog.operations &#40;Banco de Dados do SSISDB&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="caaaf-122">For a full list of the status types, see the [catalog.operations &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database) view.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="caaaf-123">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="caaaf-123">Related Content</span></span>  
 <span data-ttu-id="caaaf-124">Entrada de blog, [Visão geral da API do T-SQL SSIS](https://go.microsoft.com/fwlink/?LinkId=249051), em blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="caaaf-124">Blog entry, [SSIS T-SQL API Overview](https://go.microsoft.com/fwlink/?LinkId=249051), on blogs.msdn.com.</span></span>  
  
  
