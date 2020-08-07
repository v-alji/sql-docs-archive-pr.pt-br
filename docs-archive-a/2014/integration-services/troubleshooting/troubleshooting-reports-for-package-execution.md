---
title: Relatórios de solução de problemas para execução de pacotes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 8fc476ac-bd69-434e-9636-70776e0b3b6c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b20d9c9c02af3f3df96e2ef46a7b25251793fa55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575905"
---
# <a name="troubleshooting-reports-for-package-execution"></a><span data-ttu-id="53875-102">Solucionando problemas de relatórios para execução de pacotes</span><span class="sxs-lookup"><span data-stu-id="53875-102">Troubleshooting Reports for Package Execution</span></span>
  <span data-ttu-id="53875-103">Na versão atual do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], os relatórios padrão estão disponíveis no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para ajudar você a monitorar e solucionar problemas de pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , que foram implantados no catálogo do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="53875-103">In the current release of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], standard reports are available in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to help you monitor and troubleshoot [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages that have been deployed to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] catalog.</span></span> <span data-ttu-id="53875-104">Dois desses relatórios de pacotes em especial ajudam você a exibir o status de execução do pacote e a identificar a causa de falhas de execução.</span><span class="sxs-lookup"><span data-stu-id="53875-104">Two of these package reports in particular help you to view package execution status and identify the cause of execution failures.</span></span>  
  
-   <span data-ttu-id="53875-105">**Painel do Integration Services** – este relatório fornece uma visão geral de todas as execuções de pacote na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nas últimas 24 horas.</span><span class="sxs-lookup"><span data-stu-id="53875-105">**Integration Services Dashboard** - This report provides an overview of all the package executions on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance in the past 24 hours.</span></span> <span data-ttu-id="53875-106">O relatório exibe informações, como Status, Tipo de Operação, Nome do Pacote, etc., para cada pacote.</span><span class="sxs-lookup"><span data-stu-id="53875-106">The report displays information such as Status, Operation Type, Package Name, etc., for each package.</span></span>  
  
     <span data-ttu-id="53875-107">A Hora de Início, a Hora de Término e a Duração podem ser interpretadas desta forma:</span><span class="sxs-lookup"><span data-stu-id="53875-107">The Start Time, End Time, and Duration can be interpreted as follows:</span></span>  
  
    -   <span data-ttu-id="53875-108">Se o pacote ainda estiver em execução, Duração = hora atual – Hora de Início</span><span class="sxs-lookup"><span data-stu-id="53875-108">If the package is still running, then Duration = current time - Start Time</span></span>  
  
    -   <span data-ttu-id="53875-109">Se o pacote tiver sido concluído, Duração = Hora de Término – Hora de Início</span><span class="sxs-lookup"><span data-stu-id="53875-109">If the package has completed, then Duration = End Time - Start Time</span></span>  
  
     <span data-ttu-id="53875-110">Para cada pacote executado no servidor, o painel permite "ampliar" para localizar detalhes específicos sobre erros de execução de pacote que possam ter ocorrido.</span><span class="sxs-lookup"><span data-stu-id="53875-110">For each package that has run on the server, the dashboard allows you to "zoom in" to find specific details on package execution errors that may have occurred.</span></span> <span data-ttu-id="53875-111">Por exemplo, clique em **Visão Geral** para exibir uma visão geral de alto nível do status das tarefas na execução, ou em **Todas as Mensagens** para exibir as mensagens detalhadas que foram capturadas como parte da execução do pacote.</span><span class="sxs-lookup"><span data-stu-id="53875-111">For example, click **Overview** to display a high-level overview of the status of the tasks in the execution, or **All Messages** to display the detailed messages that were captured as part of the package execution.</span></span>  
  
     <span data-ttu-id="53875-112">Você pode filtrar a tabela exibida em qualquer página clicando em **Filtrar** e, em seguida, selecionando os critérios na caixa de diálogo **Configurações de Filtro** .</span><span class="sxs-lookup"><span data-stu-id="53875-112">You can filter the table displayed on any page by clicking **Filter** and then selecting criteria in the **Filter Settings** dialog.</span></span> <span data-ttu-id="53875-113">Os critérios de filtro disponíveis dependem dos dados sendo exibidos.</span><span class="sxs-lookup"><span data-stu-id="53875-113">The filter criteria available depends on the data being displayed.</span></span> <span data-ttu-id="53875-114">É possível alterar a ordem de classificação do relatório clicando no ícone de classificação na caixa de diálogo **Configurações de Filtro** .</span><span class="sxs-lookup"><span data-stu-id="53875-114">You can change the sort order of the report by clicking the sort icon in the **Filter Settings** dialog.</span></span>  
  
-   <span data-ttu-id="53875-115">**Relatório de Atividade – Todas as Execuções** – este relatório exibe um resumo de todas as execuções do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que foram efetuadas no servidor.</span><span class="sxs-lookup"><span data-stu-id="53875-115">**Activity - All Executions Report** - This report displays a summary of all [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] executions that have been performed on the server.</span></span> <span data-ttu-id="53875-116">O resumo exibe informações para cada execução, como status, hora de início e hora de término.</span><span class="sxs-lookup"><span data-stu-id="53875-116">The summary displays information for each execution such as status, start time, and end time.</span></span> <span data-ttu-id="53875-117">Cada entrada resumida inclui links para mais informações sobre a execução, inclusive mensagens geradas durante a execução e dados de desempenho.</span><span class="sxs-lookup"><span data-stu-id="53875-117">Each summary entry includes links to more information about the execution including messages generated during execution and performance data.</span></span> <span data-ttu-id="53875-118">Como no Painel do Integration Services, você pode aplicar um filtro à tabela para reduzir as informações exibidas.</span><span class="sxs-lookup"><span data-stu-id="53875-118">As with the Integration Services Dashboard, you can apply a filter to the table to narrow down the information displayed.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="53875-119">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="53875-119">Related Tasks</span></span>  
 [<span data-ttu-id="53875-120">Exibir relatórios do servidor do Integration Services</span><span class="sxs-lookup"><span data-stu-id="53875-120">View Reports for the Integration Services Server</span></span>](../view-reports-for-the-integration-services-server.md)  
  
## <a name="related-content"></a><span data-ttu-id="53875-121">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="53875-121">Related Content</span></span>  
 [<span data-ttu-id="53875-122">Relatórios para o servidor de Integration Services</span><span class="sxs-lookup"><span data-stu-id="53875-122">Reports for the Integration Services Server</span></span>](../reports-for-the-integration-services-server.md)  
  
 [<span data-ttu-id="53875-123">Ferramentas de solução de problemas de execução de pacote</span><span class="sxs-lookup"><span data-stu-id="53875-123">Troubleshooting Tools for Package Execution</span></span>](troubleshooting-tools-for-package-execution.md)  
  
  
