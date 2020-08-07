---
title: Exibir um relatório de conjuntos de coleta (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dc.reporthistory.calendar.f1
helpviewer_keywords:
- collection sets [SQL Server], viewing reports
- reports [SQL Server], viewing collection set
ms.assetid: c3b1e791-9aa1-4bba-9622-4954568e1820
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cb8755c67e6c03bb318fdb86d703f6d647d5a3eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581958"
---
# <a name="view-a-collection-set-report-sql-server-management-studio"></a><span data-ttu-id="da782-102">Exibir um relatório de conjuntos de coleta (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="da782-102">View a Collection Set Report (SQL Server Management Studio)</span></span>
  <span data-ttu-id="da782-103">Depois de configurar o data warehouse de gerenciamento, você pode exibir um relatório do conjunto de coleta no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da782-103">After you have configured the management data warehouse, you can view a collection set report in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="da782-104">Os relatórios são fornecidos para os conjuntos de coleta de Dados do Sistema instalados durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="da782-104">Reports are provided for the System Data collection sets that are installed during Setup.</span></span> <span data-ttu-id="da782-105">Os relatórios incluídos são:</span><span class="sxs-lookup"><span data-stu-id="da782-105">The reports include the following:</span></span>  
  
-   <span data-ttu-id="da782-106">Resumo de Uso do Disco</span><span class="sxs-lookup"><span data-stu-id="da782-106">Disk Usage Summary</span></span>  
  
-   <span data-ttu-id="da782-107">Histórico de Estatísticas de Consulta</span><span class="sxs-lookup"><span data-stu-id="da782-107">Query Statistics History</span></span>  
  
-   <span data-ttu-id="da782-108">Histórico de Atividade do Servidor</span><span class="sxs-lookup"><span data-stu-id="da782-108">Server Activity History</span></span>  
  
 <span data-ttu-id="da782-109">Este procedimento exibe o relatório para o conjunto de coleta **Uso do Disco** .</span><span class="sxs-lookup"><span data-stu-id="da782-109">This procedure displays the report for the **Disk Usage** collection set.</span></span> <span data-ttu-id="da782-110">É possível seguir o mesmo procedimento geral para exibir os relatórios para os outros conjuntos de coleta de Dados do Sistema.</span><span class="sxs-lookup"><span data-stu-id="da782-110">You can follow the same general procedure to view the reports for the other System Data collection sets.</span></span>  
  
### <a name="to-view-a-collection-set-report"></a><span data-ttu-id="da782-111">Para exibir um relatório de conjunto de coleta</span><span class="sxs-lookup"><span data-stu-id="da782-111">To view a collection set report</span></span>  
  
1.  <span data-ttu-id="da782-112">As tabelas de um relatório são criadas apenas na primeira vez em que os dados coletados são carregados.</span><span class="sxs-lookup"><span data-stu-id="da782-112">The tables for a report are created the first time that the collected data is uploaded.</span></span> <span data-ttu-id="da782-113">Se você tentar exibir um relatório antes desse primeiro carregamento, ocorrerá um erro e nenhum relatório será exibido.</span><span class="sxs-lookup"><span data-stu-id="da782-113">If you try to view a report before this first upload, an error occurs and no report is displayed.</span></span> <span data-ttu-id="da782-114">Para carregar os dados do conjunto de coleta Uso do Disco, no Pesquisador de Objetos, expanda a pasta **Gerenciamento** , **Coleta de Dados**e **Conjuntos de Coleta de Dados do Sistema**, clique com o botão direito do mouse no conjunto de coleta **Uso do Disco** e clique em **Coletar e Carregar Agora**.</span><span class="sxs-lookup"><span data-stu-id="da782-114">To upload data for the Disk Usage collection set, in Object Explorer, expand the **Management** folder, expand **Data Collection**, expand **System Data Collection Sets**, right-click the **Disk Usage** collection set, and then click **Collect and Upload Now**.</span></span>  
  
2.  <span data-ttu-id="da782-115">Para exibir o relatório, no Pesquisador de Objetos, expanda a pasta **Gerenciamento** , clique com o botão direito do mouse em **Coleta de Dados**, aponte para **Relatórios**, aponte para **Data Warehouse de Gerenciamento**e clique em **Resumo de Uso do Disco**.</span><span class="sxs-lookup"><span data-stu-id="da782-115">To view the report, in Object Explorer, expand the **Management** folder, right-click **Data Collection**, point to **Reports**, point to **Management Data Warehouse**, and then click **Disk Usage Summary**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="da782-116">Alguns relatórios podem exibir um botão de calendário sob a linha de tempo de coleta de dados.</span><span class="sxs-lookup"><span data-stu-id="da782-116">Some reports might display a calendar button under the data collection timeline.</span></span> <span data-ttu-id="da782-117">Clique neste botão para acessar o **Calendário de Relatório de Coleta de Dados**.</span><span class="sxs-lookup"><span data-stu-id="da782-117">Click this button to access the **Data Collection Report Calendar**.</span></span>  
  
#### <a name="data-collection-report-calendar"></a><span data-ttu-id="da782-118">Calendário de Relatório de Coleta de Dados</span><span class="sxs-lookup"><span data-stu-id="da782-118">Data Collection Report Calendar</span></span>  
 <span data-ttu-id="da782-119">Use essa caixa de diálogo para especificar a data e a hora de início e a duração dos dados que servirão de base para o relatório.</span><span class="sxs-lookup"><span data-stu-id="da782-119">Use this dialog box to specify the start date, start time, and duration of the data that you want to report on.</span></span> <span data-ttu-id="da782-120">Por exemplo, talvez você queira gerar um relatório sobre a atividade de utilização do disco de um servidor em um período de 12 horas específico da última quarta-feira.</span><span class="sxs-lookup"><span data-stu-id="da782-120">For example, you may want to report on the disk usage activity of a server for a specific 12-hour period last Wednesday.</span></span>  
  
 <span data-ttu-id="da782-121">**Data de início**</span><span class="sxs-lookup"><span data-stu-id="da782-121">**Start date**</span></span>  
 <span data-ttu-id="da782-122">Digite uma data inicial para obter os dados do relatório ou selecione-a no calendário.</span><span class="sxs-lookup"><span data-stu-id="da782-122">Enter a beginning date for the report data, or select one from the calendar.</span></span>  
  
 <span data-ttu-id="da782-123">**Hora de início**</span><span class="sxs-lookup"><span data-stu-id="da782-123">**Start time**</span></span>  
 <span data-ttu-id="da782-124">Digite uma hora inicial para obter os dados do relatório ou especifique-a clicando nas setas.</span><span class="sxs-lookup"><span data-stu-id="da782-124">Enter a beginning time for the report data or specify one by clicking the arrows.</span></span>  
  
 <span data-ttu-id="da782-125">**Duration**</span><span class="sxs-lookup"><span data-stu-id="da782-125">**Duration**</span></span>  
 <span data-ttu-id="da782-126">Especifique o intervalo de tempo que será incluído no relatório.</span><span class="sxs-lookup"><span data-stu-id="da782-126">Specify the time range to include in the report.</span></span> <span data-ttu-id="da782-127">O valor padrão é 240 minutos.</span><span class="sxs-lookup"><span data-stu-id="da782-127">The default value is 240 minutes.</span></span> <span data-ttu-id="da782-128">Os valores disponíveis para seleção são 15 minutos, 60 minutos, 240 minutos (4 horas), 720 minutos (12 horas) e 1440 minutos (24 horas).</span><span class="sxs-lookup"><span data-stu-id="da782-128">The possible values to select from are 15 minutes, 60 minutes, 240 minutes (4 hours), 720 minutes (12 hours), and 1440 minutes (24 hours).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da782-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="da782-129">See Also</span></span>  
 <span data-ttu-id="da782-130">[Coleta de Dados](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="da782-130">[Data Collection](data-collection.md) </span></span>  
 <span data-ttu-id="da782-131">[Relatórios personalizados no Management Studio](../../ssms/object/custom-reports-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="da782-131">[Custom Reports in Management Studio](../../ssms/object/custom-reports-in-management-studio.md) </span></span>  
 [<span data-ttu-id="da782-132">Configurar o Data Warehouse de Gerenciamento &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="da782-132">Configure the Management Data Warehouse &#40;SQL Server Management Studio&#41;</span></span>](configure-the-management-data-warehouse-sql-server-management-studio.md)  
  
  
