---
title: Exibir entradas de log na janela de eventos de log | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logs [Integration Services], viewing
- Integration Services packages, logs
- packages [Integration Services], logs
ms.assetid: c02123c3-67fc-4370-ad14-91ed259f1873
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 16b6f11758d7de2c833731cd007426000a01d8ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678833"
---
# <a name="view-log-entries-in-the-log-events-window"></a><span data-ttu-id="7e1b8-102">Exibir entradas de log na janela Eventos de Log</span><span class="sxs-lookup"><span data-stu-id="7e1b8-102">View Log Entries in the Log Events Window</span></span>
  <span data-ttu-id="7e1b8-103">Este procedimento descreve como executar um pacote e exibir as entradas de log que ele grava.</span><span class="sxs-lookup"><span data-stu-id="7e1b8-103">This procedure describes how to run a package and view the log entries it writes.</span></span> <span data-ttu-id="7e1b8-104">Você pode exibir as entradas de log em tempo real.</span><span class="sxs-lookup"><span data-stu-id="7e1b8-104">You can view the log entries in real time.</span></span> <span data-ttu-id="7e1b8-105">As entradas de log, gravadas na janela **Eventos de Log** , também podem ser copiadas e salvas para uma análise posterior.</span><span class="sxs-lookup"><span data-stu-id="7e1b8-105">The log entries that are written to the **Log Events** window can also be copied and saved for further analysis.</span></span>  
  
 <span data-ttu-id="7e1b8-106">Não é necessário gravar as entradas de log em um log para gravar as entradas na janela **Eventos de Log** .</span><span class="sxs-lookup"><span data-stu-id="7e1b8-106">It is not necessary to write the log entries to a log to write the entries to the **Log Events** window.</span></span>  
  
### <a name="to-view-log-entries"></a><span data-ttu-id="7e1b8-107">Para exibir entradas de log</span><span class="sxs-lookup"><span data-stu-id="7e1b8-107">To view log entries</span></span>  
  
1.  <span data-ttu-id="7e1b8-108">No [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote desejado.</span><span class="sxs-lookup"><span data-stu-id="7e1b8-108">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="7e1b8-109">No menu **SSIS** , clique em **Eventos de Log**.</span><span class="sxs-lookup"><span data-stu-id="7e1b8-109">On the **SSIS** menu, click **Log Events**.</span></span> <span data-ttu-id="7e1b8-110">Opcionalmente, você pode exibir a janela **Eventos de Log** mapeando o comando View.LogEvents com uma combinação de teclas escolhidas por você na página **Teclado** da caixa de diálogo **Opções** .</span><span class="sxs-lookup"><span data-stu-id="7e1b8-110">You can optionally display the **Log Events** window by mapping the View.LogEvents command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
3.  <span data-ttu-id="7e1b8-111">No menu **Depurar**, clique em **Iniciar Depuração**.</span><span class="sxs-lookup"><span data-stu-id="7e1b8-111">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
     <span data-ttu-id="7e1b8-112">Quando o runtime encontra os eventos e as mensagens personalizadas habilitadas para registro, as entradas de log para cada evento ou mensagem são gravadas na janela **Eventos de Log** .</span><span class="sxs-lookup"><span data-stu-id="7e1b8-112">As the runtime encounters the events and custom messages that are enabled for logging, log entries for each event or message are written to the **Log Events** window.</span></span>  
  
4.  <span data-ttu-id="7e1b8-113">No menu **Depuração**, clique em **Parar Depuração**.</span><span class="sxs-lookup"><span data-stu-id="7e1b8-113">On the **Debug** menu, click **Stop Debugging**.</span></span>  
  
     <span data-ttu-id="7e1b8-114">As entradas de log permanecem disponíveis na janela **Eventos de Log** até que você execute novamente o pacote, execute um pacote diferente ou feche o [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e1b8-114">The log entries remain available in the **Log Events** window until you rerun the package, run a different package, or close [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span></span>  
  
5.  <span data-ttu-id="7e1b8-115">Exibir as entradas de log na janela **Eventos de Log** .</span><span class="sxs-lookup"><span data-stu-id="7e1b8-115">View the log entries in the **Log Events** window.</span></span>  
  
6.  <span data-ttu-id="7e1b8-116">Opcionalmente, clique nas entradas de log para copiar, clique com o botão direito do mouse e clique em **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="7e1b8-116">Optionally, click the log entries to copy, right-click, and then click **Copy**.</span></span>  
  
7.  <span data-ttu-id="7e1b8-117">Opcionalmente, clique duas vezes em uma entrada de log e, na caixa de diálogo **Entrada de Log** , exiba os detalhes de uma única entrada de log.</span><span class="sxs-lookup"><span data-stu-id="7e1b8-117">Optionally, double-click a log entry, and in the **Log Entry** dialog box, view the details for a single log entry.</span></span>  
  
8.  <span data-ttu-id="7e1b8-118">Na caixa de diálogo **Entrada de Log** , clique nas setas para baixo e para cima para exibir a entrada de log anterior ou posterior e clique no ícone de cópia para copiar a entrada de log.</span><span class="sxs-lookup"><span data-stu-id="7e1b8-118">In the **Log Entry** dialog box, click the up and down arrows to display the previous or next log entry, and click the copy icon to copy the log entry.</span></span>  
  
9. <span data-ttu-id="7e1b8-119">Abra um editor de textos, cole e salve a entrada de log em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="7e1b8-119">Open a text editor, paste, and then save the log entry to a text file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e1b8-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7e1b8-120">See Also</span></span>  
 [<span data-ttu-id="7e1b8-121">Registro em Log do SSIS &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7e1b8-121">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
  
