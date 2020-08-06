---
title: Limitar o histórico de relatórios (Gerenciador de Relatórios) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- viewing report history
- report history [Reporting Services], viewing history
- report history [Reporting Services], configuring history
- historical data [Reporting Services]
- displaying report history
ms.assetid: 8e255792-d9ef-496f-a26c-9e969c1209a0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 01318b1e1ccf0b0bf4512ab57de90cbf5ebc7365
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679667"
---
# <a name="limit-report-history-report-manager"></a><span data-ttu-id="fa35c-102">Limitar o histórico de relatório (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="fa35c-102">Limit Report History (Report Manager)</span></span>
  <span data-ttu-id="fa35c-103">O histórico de relatórios é uma coleção de instantâneos de relatórios que você cria.</span><span class="sxs-lookup"><span data-stu-id="fa35c-103">Report history is a collection of report snapshots that you create over time.</span></span> <span data-ttu-id="fa35c-104">Você pode criar um histórico de relatórios sob demanda ou agendar com que frequência um instantâneo é criado e adicionado ao histórico de relatórios.</span><span class="sxs-lookup"><span data-stu-id="fa35c-104">You can create report history on demand, or schedule how often a snapshot is created and added to report history.</span></span>  
  
 <span data-ttu-id="fa35c-105">O histórico de relatórios é armazenado no banco de dados do servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="fa35c-105">Report history is stored in the report server database.</span></span> <span data-ttu-id="fa35c-106">Se os instantâneos de relatório contiverem uma grande quantidade de dados, limite o histórico de relatórios para minimizar o efeito da retenção de instantâneos no tamanho do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fa35c-106">If report snapshots contain a large amount of data, you might consider limiting report history to minimize the affect of snapshot retention on database size.</span></span>  
  
### <a name="to-configure-report-history-for-a-report-server"></a><span data-ttu-id="fa35c-107">Para configurar o histórico de relatórios para um servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="fa35c-107">To configure report history for a report server</span></span>  
  
1.  <span data-ttu-id="fa35c-108">No Gerenciador de Relatórios, clique em **Configurações de Site** na barra de ferramentas global.</span><span class="sxs-lookup"><span data-stu-id="fa35c-108">In Report Manager, click **Site Settings** on the global toolbar.</span></span>  
  
2.  <span data-ttu-id="fa35c-109">Selecione **Manter um número ilimitado de instantâneos no histórico de relatório** se desejar manter todo o histórico de relatórios indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="fa35c-109">Select **Keep an unlimited number of snapshots in report history** if you want to keep all report history indefinitely.</span></span> <span data-ttu-id="fa35c-110">Caso contrário, selecione **Limitar as cópias do histórico de relatório** para especificar o número máximo de instantâneos que podem ser mantidos em um relatório específico.</span><span class="sxs-lookup"><span data-stu-id="fa35c-110">Otherwise, select **Limit the copies of report history** to specify the maximum number of snapshots that can be kept for any given report.</span></span>  
  
3.  <span data-ttu-id="fa35c-111">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="fa35c-111">Click **Apply**.</span></span>  
  
### <a name="to-configure-report-history-for-a-specific-report"></a><span data-ttu-id="fa35c-112">Para configurar o histórico de relatórios para um relatório específico</span><span class="sxs-lookup"><span data-stu-id="fa35c-112">To configure report history for a specific report</span></span>  
  
1.  <span data-ttu-id="fa35c-113">No Gerenciador de Relatórios, navegue até o relatório para o qual deseja configurar o histórico e, em seguida, clique no relatório para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="fa35c-113">In Report Manager, navigate to the report for which you want to configure history, and then click the report to open it.</span></span>  
  
2.  <span data-ttu-id="fa35c-114">Clique no guia **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="fa35c-114">Click the **Properties** tab.</span></span>  
  
3.  <span data-ttu-id="fa35c-115">Clique na guia **Histórico**.</span><span class="sxs-lookup"><span data-stu-id="fa35c-115">Click the **History** tab.</span></span>  
  
4.  <span data-ttu-id="fa35c-116">Selecione as opções para seu relatório e clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="fa35c-116">Select the options for your report and click **Apply**.</span></span> <span data-ttu-id="fa35c-117">Para obter detalhes sobre cada opção, consulte [Página de propriedades Opções de Instantâneo &#40;Gerenciador de Relatórios&#41;](../snapshot-options-properties-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="fa35c-117">For details about each option, see [Snapshot Options Properties Page &#40;Report Manager&#41;](../snapshot-options-properties-page-report-manager.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa35c-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fa35c-118">See Also</span></span>  
 <span data-ttu-id="fa35c-119">[Adicionar um instantâneo ao histórico de relatório &#40;Report Manager&#41;](../report-server/add-a-snapshot-to-report-history-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="fa35c-119">[Add a Snapshot to Report History &#40;Report Manager&#41;](../report-server/add-a-snapshot-to-report-history-report-manager.md) </span></span>  
 [<span data-ttu-id="fa35c-120">Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="fa35c-120">Report Manager  &#40;SSRS Native Mode&#41;</span></span>](../report-manager-ssrs-native-mode.md)  
  
  
