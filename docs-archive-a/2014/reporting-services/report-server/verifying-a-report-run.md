---
title: Verificando uma execução de relatório | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- auditing [Reporting Services]
- verifying report execution
- logs [Reporting Services], verifying report run
- report execution data [Reporting Services]
- status information [Reporting Services]
- report processing [Reporting Services], verifying execution
- checking report execution
ms.assetid: 18a98f2f-6b40-454e-9b37-568ed1a96458
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c11c57f7c5f67b2557f5637ad10658abc9f80606
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573618"
---
# <a name="verifying-a-report-run"></a><span data-ttu-id="ee3ff-102">Verificando uma execução de relatório</span><span class="sxs-lookup"><span data-stu-id="ee3ff-102">Verifying a Report Run</span></span>
  <span data-ttu-id="ee3ff-103">Para visualizar informações sobre o status de processamento do relatório, você pode usar os arquivos de log ou consultar as informações sobre status exibidas com o relatório no Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-103">To view information about the status of report processing, you can use log files or refer to status information that is displayed with the report in Report Manager.</span></span>  
  
## <a name="sources-of-report-execution-data"></a><span data-ttu-id="ee3ff-104">Fontes de dados de execução de relatórios</span><span class="sxs-lookup"><span data-stu-id="ee3ff-104">Sources of Report Execution Data</span></span>  
 <span data-ttu-id="ee3ff-105">Os logs de execução de relatório fornecem informações abrangentes sobre a execução do relatório, incluindo o nome dele, o nome do usuário que o executou, o horário da execução do relatório e a extensão de entrega usada para distribuí-lo.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-105">The report execution logs provide comprehensive information about report execution, including the name of the report, the name of the user who ran the report, report execution time, and the delivery extension used to distribute the report.</span></span> <span data-ttu-id="ee3ff-106">Para visualizar e analisar esses dados, você pode copiar o log de execução do relatório nas tabelas do banco de dados que são fáceis de consultar e relatar.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-106">To view and analyze this data, you can copy the report execution log into database tables that are easy to query and report on.</span></span>  
  
 <span data-ttu-id="ee3ff-107">Os arquivos de log contêm muitas entradas sobre a execução de relatório e outra atividade de servidor.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-107">Log files contain many entries about report execution and other server activity.</span></span> <span data-ttu-id="ee3ff-108">Uma vez que os arquivos de log contêm tantos dados, talvez você queira usar o Gerenciador de Relatórios apenas se quiser verificar quando foi a última execução do relatório.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-108">Because log files contain so much data, you may want to use Report Manager if you only want to verify when the report last ran.</span></span> <span data-ttu-id="ee3ff-109">Se quiser informações adicionais, exiba os arquivos de log.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-109">If you require additional information, you must view the log files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ee3ff-110">O Gerenciador de Relatórios não mostra os horários de processamento dos relatórios executados sob demanda.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-110">Report Manager does not show the processing times of reports that run on demand.</span></span>  
  
 <span data-ttu-id="ee3ff-111">A tabela a seguir descreve como exibir a data e hora do processamento para vários tipos de relatórios.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-111">The following table describes how to view the processing date and time for various types of reports.</span></span>  
  
|<span data-ttu-id="ee3ff-112">Para este tipo de relatório</span><span class="sxs-lookup"><span data-stu-id="ee3ff-112">For this type of report</span></span>|<span data-ttu-id="ee3ff-113">As informações sobre data e hora estão localizadas aqui</span><span class="sxs-lookup"><span data-stu-id="ee3ff-113">Date and time information is located here</span></span>|<span data-ttu-id="ee3ff-114">Para exibir as informações, faça o seguinte</span><span class="sxs-lookup"><span data-stu-id="ee3ff-114">To view the information, do the following</span></span>|  
|-----------------------------|-----------------------------------------------|-----------------------------------------------|  
|<span data-ttu-id="ee3ff-115">Um relatório que é executado como um instantâneo de relatório.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-115">A report that runs as a report snapshot.</span></span>|<span data-ttu-id="ee3ff-116">Na página Conteúdo.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-116">On the Contents page.</span></span> <span data-ttu-id="ee3ff-117">Para obter mais informações, consulte [Página Conteúdo &#40;Gerenciador de Relatórios&#41;](../contents-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="ee3ff-117">For more information, see [Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md).</span></span>|<span data-ttu-id="ee3ff-118">1) Localize a pasta que contém o relatório.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-118">1) Locate the folder that contains the report.</span></span><br /><span data-ttu-id="ee3ff-119">2) Defina a pasta na exibição Detalhes.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-119">2) Set the folder in Details view.</span></span><br /><span data-ttu-id="ee3ff-120">3) 3) Observe a data e a hora na coluna **quando executar** .</span><span class="sxs-lookup"><span data-stu-id="ee3ff-120">3) 3) Note the date and time in the **When Run** column.</span></span>|  
|<span data-ttu-id="ee3ff-121">Um instantâneo no histórico de relatórios.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-121">A snapshot in report history.</span></span>|<span data-ttu-id="ee3ff-122">Na página Propriedades do Histórico.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-122">On the History Properties page.</span></span> <span data-ttu-id="ee3ff-123">Para obter mais informações, consulte [Página de propriedades Opções de Instantâneo &#40;Gerenciador de Relatórios&#41;](../snapshot-options-properties-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="ee3ff-123">For more information, see [Snapshot Options Properties Page &#40;Report Manager&#41;](../snapshot-options-properties-page-report-manager.md).</span></span>|<span data-ttu-id="ee3ff-124">1) Abra o relatório.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-124">1) Open the report.</span></span><br /><span data-ttu-id="ee3ff-125">2) Clique na página **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="ee3ff-125">2) Click the **Properties** page.</span></span><br /><span data-ttu-id="ee3ff-126">3) Clique na guia **Histórico** .</span><span class="sxs-lookup"><span data-stu-id="ee3ff-126">3) Click the **History** tab.</span></span><br /><span data-ttu-id="ee3ff-127">4) Observe a data e hora na coluna **Quando Executado** .</span><span class="sxs-lookup"><span data-stu-id="ee3ff-127">4) Note the date and time in the **When Run** column.</span></span>|  
|<span data-ttu-id="ee3ff-128">Um relatório armazenado em cache.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-128">A cached report.</span></span>|<span data-ttu-id="ee3ff-129">Na agenda usada para criar e atualizar o relatório armazenado em cache.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-129">In the schedule used to create and refresh the cached report.</span></span>|<span data-ttu-id="ee3ff-130">1) Abra o relatório.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-130">1) Open the report.</span></span><br /><span data-ttu-id="ee3ff-131">2) Clique na página **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="ee3ff-131">2) Click the **Properties** page.</span></span><br /><span data-ttu-id="ee3ff-132">3) Clique na guia **Execução** .</span><span class="sxs-lookup"><span data-stu-id="ee3ff-132">3) Click the **Execution** tab.</span></span><br /><span data-ttu-id="ee3ff-133">4) Abra a agenda.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-133">4) Open the schedule.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ee3ff-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ee3ff-134">See Also</span></span>  
 <span data-ttu-id="ee3ff-135">[Fontes e arquivos de log do Reporting Services](../report-server/reporting-services-log-files-and-sources.md) </span><span class="sxs-lookup"><span data-stu-id="ee3ff-135">[Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md) </span></span>  
 <span data-ttu-id="ee3ff-136">[Definir as propriedades do processamento de relatórios](set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="ee3ff-136">[Set Report Processing Properties](set-report-processing-properties.md) </span></span>  
 [<span data-ttu-id="ee3ff-137">Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ee3ff-137">Report Manager  &#40;SSRS Native Mode&#41;</span></span>](../report-manager-ssrs-native-mode.md)  
  
  
