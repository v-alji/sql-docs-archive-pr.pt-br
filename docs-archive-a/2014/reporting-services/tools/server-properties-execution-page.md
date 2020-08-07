---
title: Propriedades do Servidor (página Execução) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.serverproperties.execution.f1
ms.assetid: 53b77db1-b013-4dac-82dd-30c0de276639
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f0ec8725a0cec9e15cb6d8402f8d654320c38471
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575017"
---
# <a name="server-properties-execution-page"></a><span data-ttu-id="76867-102">Propriedades do Servidor (página Execução)</span><span class="sxs-lookup"><span data-stu-id="76867-102">Server Properties (Execution Page)</span></span>
  <span data-ttu-id="76867-103">Use essa página para definir um valor de intervalo para execução do relatório.</span><span class="sxs-lookup"><span data-stu-id="76867-103">Use this page to set a timeout value for report execution.</span></span> <span data-ttu-id="76867-104">Esse valor se aplica a todos os relatórios processados pela instância de servidor do relatório atual.</span><span class="sxs-lookup"><span data-stu-id="76867-104">This value applies to all reports that are processed by the current report server instance.</span></span> <span data-ttu-id="76867-105">Você pode anular esse valor para relatórios individuais.</span><span class="sxs-lookup"><span data-stu-id="76867-105">You can override this value for individual reports.</span></span> <span data-ttu-id="76867-106">O valor especificado deve acomodar todos os processamentos de relatório que ocorrem no servidor de relatório, mais processamento da consulta executado no servidor do banco de dados quando o servidor de relatório recupera dados usados no relatório.</span><span class="sxs-lookup"><span data-stu-id="76867-106">The value you specify must accommodate all report processing that occurs on the report server, plus query processing performed on the database server when the report server retrieves data that is used in the report.</span></span>  
  
 <span data-ttu-id="76867-107">Para abrir essa página, inicie o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conecte-se a uma instância de servidor de relatórios, clique com o botão direito do mouse no nome do servidor de relatórios e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="76867-107">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server instance, right-click the report server name, and select **Properties**.</span></span> <span data-ttu-id="76867-108">Clique em **Execução** para abrir essa página.</span><span class="sxs-lookup"><span data-stu-id="76867-108">Click **Execution** to open this page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="76867-109">Opções</span><span class="sxs-lookup"><span data-stu-id="76867-109">Options</span></span>  
 <span data-ttu-id="76867-110">**Não exceder o tempo limite de execução do relatório**</span><span class="sxs-lookup"><span data-stu-id="76867-110">**Do not timeout report execution**</span></span>  
 <span data-ttu-id="76867-111">Permita a um servidor de relatório tempo ilimitado para concluir o processamento do relatório.</span><span class="sxs-lookup"><span data-stu-id="76867-111">Allow a report server unlimited time to complete report processing.</span></span>  
  
 <span data-ttu-id="76867-112">**Limitar a execução do relatório ao seguinte número de segundos**</span><span class="sxs-lookup"><span data-stu-id="76867-112">**Limit report execution to the following number of seconds**</span></span>  
 <span data-ttu-id="76867-113">Defina uma restrição de tempo na execução do relatório.</span><span class="sxs-lookup"><span data-stu-id="76867-113">Set a time constraint on report execution.</span></span> <span data-ttu-id="76867-114">O período de tempo inicia quando o relatório é solicitado.</span><span class="sxs-lookup"><span data-stu-id="76867-114">The time period starts when the report is requested.</span></span> <span data-ttu-id="76867-115">Se o período de tempo terminar antes que o relatório seja totalmente processado, o servidor de relatório cancelará o processo e quaisquer consultas em andamento às fontes de dados externas.</span><span class="sxs-lookup"><span data-stu-id="76867-115">If the time period ends before the report is fully processed, the report server cancels the process and any in-process queries to external data sources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76867-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="76867-116">See Also</span></span>  
 <span data-ttu-id="76867-117">[Definir propriedades do servidor de relatório &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="76867-117">[Set Report Server Properties &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span></span>  
 <span data-ttu-id="76867-118">[Conectar-se a um servidor de relatório no Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="76867-118">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="76867-119">[Definir as propriedades do processamento de relatórios](../report-server/set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="76867-119">[Set Report Processing Properties](../report-server/set-report-processing-properties.md) </span></span>  
 <span data-ttu-id="76867-120">[Definindo valores de tempo limite para processamento de relatórios e conjuntos de dados compartilhados &#40;SSRS&#41;](../report-server/setting-time-out-values-for-report-and-shared-dataset-processing-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="76867-120">[Setting Time-out Values for Report and Shared Dataset Processing &#40;SSRS&#41;](../report-server/setting-time-out-values-for-report-and-shared-dataset-processing-ssrs.md) </span></span>  
 [<span data-ttu-id="76867-121">Servidor de Relatório na ajuda F1 do Management Studio</span><span class="sxs-lookup"><span data-stu-id="76867-121">Report Server in Management Studio F1 Help</span></span>](report-server-in-management-studio-f1-help.md)  
  
  
