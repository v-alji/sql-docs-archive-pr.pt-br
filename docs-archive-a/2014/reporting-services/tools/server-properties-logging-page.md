---
title: Propriedades do servidor (página Registrar em log) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.serverproperties.logging.f1
ms.assetid: b338deab-4868-4951-9f22-0605add2fc95
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2a04c27fd790a1ad5c4ba453b43af5983a6440e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575016"
---
# <a name="server-properties-logging-page"></a><span data-ttu-id="aebce-102">Propriedades do Servidor (página Log)</span><span class="sxs-lookup"><span data-stu-id="aebce-102">Server Properties (Logging Page)</span></span>
  <span data-ttu-id="aebce-103">Use essa página para definir limites nos dados de execução de relatório que são coletados por um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="aebce-103">Use this page to set limits on the report execution data that is collected by a report server.</span></span> <span data-ttu-id="aebce-104">Dados de execução são armazenados internamente no banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="aebce-104">Execution data is stored internally in the report server database.</span></span> <span data-ttu-id="aebce-105">Você pode controlar atividade de relatório para servidor de relatório que executa em modo nativo ou em modo integrado de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="aebce-105">You can track report activity for report server that runs in native mode or SharePoint integrated mode.</span></span> <span data-ttu-id="aebce-106">Se o servidor de relatório for parte de uma implantação em expansão, o log de execução do relatório manterá um registro de todas as atividades do relatório para toda a implantação, em um único arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="aebce-106">If the report server is part of a scale-out deployment, the report execution log maintains a record of all report activity for the entire deployment in a single log file.</span></span>  
  
 <span data-ttu-id="aebce-107">Para abrir essa página, inicie o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conecte-se a um servidor de relatório, clique com o botão direito do mouse no nome do servidor de relatório e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="aebce-107">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, right-click the report server name, and select **Properties**.</span></span> <span data-ttu-id="aebce-108">Clique em **Log** para abrir esta página.</span><span class="sxs-lookup"><span data-stu-id="aebce-108">Click **Logging** to open this page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="aebce-109">Opções</span><span class="sxs-lookup"><span data-stu-id="aebce-109">Options</span></span>  
 <span data-ttu-id="aebce-110">**Habilitar log de execução de relatório**</span><span class="sxs-lookup"><span data-stu-id="aebce-110">**Enable report execution logging**</span></span>  
 <span data-ttu-id="aebce-111">Clique para criar e armazenar informações sobre atividade de relatório no servidor.</span><span class="sxs-lookup"><span data-stu-id="aebce-111">Click to create and store information about report activity on the server.</span></span> <span data-ttu-id="aebce-112">Se essa opção estiver habilitada, o servidor de relatório controlará quais relatórios serão usados, a frequência de processamento do relatório, o tipo de operação executado, o formato de saída e quem executou o relatório.</span><span class="sxs-lookup"><span data-stu-id="aebce-112">If this option is enabled, the report server will track which reports are used, the frequency of report processing, the type of report operation that was performed, the output format, and who ran the report.</span></span> <span data-ttu-id="aebce-113">Para obter mais informações sobre pontos de dados adicionais que são capturados no log, consulte [log de execução do servidor de relatório e a exibição ExecutionLog3](../report-server/report-server-executionlog-and-the-executionlog3-view.md).</span><span class="sxs-lookup"><span data-stu-id="aebce-113">For more information about additional data points that are captured in the log, see [Report Server Execution Log and the ExecutionLog3 View](../report-server/report-server-executionlog-and-the-executionlog3-view.md).</span></span>  
  
 <span data-ttu-id="aebce-114">**Remova entradas de log mais antigas que este número de dias**</span><span class="sxs-lookup"><span data-stu-id="aebce-114">**Remove log entries older than this number of days**</span></span>  
 <span data-ttu-id="aebce-115">Especifique o número de dias depois dos quais as entradas de log serão apagadas do log de execução de relatório.</span><span class="sxs-lookup"><span data-stu-id="aebce-115">Specify the number of days after which log entries will be trimmed from the report execution log.</span></span> <span data-ttu-id="aebce-116">O valor padrão é 60 dias.</span><span class="sxs-lookup"><span data-stu-id="aebce-116">The default value is 60 days.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aebce-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aebce-117">See Also</span></span>  
 <span data-ttu-id="aebce-118">[Definir propriedades do servidor de relatório &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="aebce-118">[Set Report Server Properties &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span></span>  
 <span data-ttu-id="aebce-119">[Conectar-se a um servidor de relatório no Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="aebce-119">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="aebce-120">[Fontes e arquivos de log do Reporting Services](../report-server/reporting-services-log-files-and-sources.md) </span><span class="sxs-lookup"><span data-stu-id="aebce-120">[Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md) </span></span>  
 <span data-ttu-id="aebce-121">[Servidor de relatório na ajuda Management Studio F1](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="aebce-121">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 [<span data-ttu-id="aebce-122">Log de execução do servidor de relatório e a exibição ExecutionLog3</span><span class="sxs-lookup"><span data-stu-id="aebce-122">Report Server Execution Log and the ExecutionLog3 View</span></span>](../report-server/report-server-executionlog-and-the-executionlog3-view.md)  
  
  
