---
title: Executar um pacote no servidor SSIS usando SQL Server Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 56dc1bf8-99d4-41dc-bdc4-f64f1ccfd688
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d17009988dea54621d4fd7ef542cf452bfe95c6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679395"
---
# <a name="run-a-package-on-the-ssis-server-using-sql-server-management-studio"></a><span data-ttu-id="10d81-102">Executar um pacote no servidor SSIS usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="10d81-102">Run a Package on the SSIS Server Using SQL Server Management Studio</span></span>
  <span data-ttu-id="10d81-103">Depois de implantar o projeto no servidor do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , você pode executar o pacote no servidor.</span><span class="sxs-lookup"><span data-stu-id="10d81-103">After you deploy your project to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server, you can run the package on the server.</span></span>  
  
 <span data-ttu-id="10d81-104">Você pode usar relatórios de operações para exibir informações sobre pacotes que foram executados, ou que estão em execução no momento, no servidor.</span><span class="sxs-lookup"><span data-stu-id="10d81-104">You can use operations reports to view information about packages that have run, or are currently running, on the server.</span></span> <span data-ttu-id="10d81-105">Para saber mais, confira [Reports for the Integration Services Server](../../2014/integration-services/reports-for-the-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="10d81-105">For more information, see [Reports for the Integration Services Server](../../2014/integration-services/reports-for-the-integration-services-server.md).</span></span>  
  
### <a name="to-run-a-package-on-the-server-using-sql-server-management-studio"></a><span data-ttu-id="10d81-106">Para executar um pacote no servidor usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="10d81-106">To run a package on the server using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="10d81-107">Abra o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] e conecte-se com a instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que contém o catálogo do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="10d81-107">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that contains the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] catalog.</span></span>  
  
2.  <span data-ttu-id="10d81-108">No Explorador de Objetos, expanda o nó **Catálogo do Integration Services** , expanda o nó **SSISDB** e navegue até o pacote contido no projeto que você implantou.</span><span class="sxs-lookup"><span data-stu-id="10d81-108">In Object Explorer, expand the **Integration Services Catalogs** node, expand the **SSISDB** node, and navigate to the package contained in the project you deployed.</span></span>  
  
3.  <span data-ttu-id="10d81-109">Clique com o botão direito do mouse no nome do pacote e selecione **Executar**.</span><span class="sxs-lookup"><span data-stu-id="10d81-109">Right-click the package name and select **Execute**.</span></span>  
  
4.  <span data-ttu-id="10d81-110">Configure a execução de pacote usando as configurações nas guias **Parâmetros**, **Gerenciadores de Conexões**e **Avançado** na caixa de diálogo **Executar Pacote** .</span><span class="sxs-lookup"><span data-stu-id="10d81-110">Configure the package execution by using the settings on the **Parameters**, **Connection Managers**, and **Advanced** tabs in the **Execute Package** dialog box.</span></span>  
  
5.  <span data-ttu-id="10d81-111">Clique em **OK** para executar o pacote.</span><span class="sxs-lookup"><span data-stu-id="10d81-111">Click **OK** to run the package.</span></span>  
  
     <span data-ttu-id="10d81-112">-ou-</span><span class="sxs-lookup"><span data-stu-id="10d81-112">-or-</span></span>  
  
     <span data-ttu-id="10d81-113">Use procedimentos armazenados para executar o pacote.</span><span class="sxs-lookup"><span data-stu-id="10d81-113">Use stored procedures to run the package.</span></span> <span data-ttu-id="10d81-114">Clique em **Script** para gerar a instrução Transact-SQL que cria uma instância da execução e inicia uma instância da execução.</span><span class="sxs-lookup"><span data-stu-id="10d81-114">Click **Script** to generate the Transact-SQL statement that creates an instance of the execution and starts an instance of the execution.</span></span> <span data-ttu-id="10d81-115">A instrução inclu uma chamada para os procedimentos armazenados catalog.create_execution, catalog.set_execution_parameter_value e catalog.start_execution.</span><span class="sxs-lookup"><span data-stu-id="10d81-115">The statement includes a call to the catalog.create_execution, catalog.set_execution_parameter_value, and catalog.start_execution stored procedures.</span></span> <span data-ttu-id="10d81-116">Para obter mais informações sobre esses procedimentos armazenados, consulte [catalog.create_execution &#40;Banco de dados SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database), [catalog.set_execution_parameter_value &#40;Banco de dados SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database) e [catalog.start_execution &#40;Banco de dados SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="10d81-116">For more information about these stored procedures, see [catalog.create_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database), [catalog.set_execution_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database), and [catalog.start_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database).</span></span>  
  
  
