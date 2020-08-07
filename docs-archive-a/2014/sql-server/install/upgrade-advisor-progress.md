---
title: Andamento do supervisor de atualização | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor [SQL Server], analysis progress status
- analyzing system [Upgrade Advisor], progress information
- SQL Server Upgrade Advisor, analysis progress status
- monitoring analysis progress
- progress information [Upgrade Advisor]
- status information [Upgrade Advisor]
ms.assetid: a9e3d1c8-d492-4beb-93c7-f1bc40d4a910
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b504b8f1c8392ad2cf55837dc65bbb2f019d6f48
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573415"
---
# <a name="upgrade-advisor-progress"></a><span data-ttu-id="6e820-102">Progresso do Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="6e820-102">Upgrade Advisor Progress</span></span>
  <span data-ttu-id="6e820-103">A análise do Supervisor de Atualização inicia com um analisador dedicado que faz uma análise de cada componente selecionado do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6e820-103">Upgrade Advisor analysis starts with a dedicated analyzer that performs an analysis of each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] component that you selected.</span></span> <span data-ttu-id="6e820-104">À medida que os componentes são analisados, o progresso é relatado na caixa de diálogo de **progresso** .</span><span class="sxs-lookup"><span data-stu-id="6e820-104">As components are analyzed, progress is reported in the **Progress** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6e820-105">Opções</span><span class="sxs-lookup"><span data-stu-id="6e820-105">Options</span></span>  
 <span data-ttu-id="6e820-106">**Ação**</span><span class="sxs-lookup"><span data-stu-id="6e820-106">**Action**</span></span>  
 <span data-ttu-id="6e820-107">Especifica o componente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que é selecionado para análise.</span><span class="sxs-lookup"><span data-stu-id="6e820-107">Specifies the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] component that is selected for analysis.</span></span>  
  
 <span data-ttu-id="6e820-108">**Status**</span><span class="sxs-lookup"><span data-stu-id="6e820-108">**Status**</span></span>  
 <span data-ttu-id="6e820-109">Exibe o valor de status retornado pela interface de progresso do componente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6e820-109">Displays the status value returned from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] component progress interface.</span></span>  
  
 <span data-ttu-id="6e820-110">**Message**</span><span class="sxs-lookup"><span data-stu-id="6e820-110">**Message**</span></span>  
 <span data-ttu-id="6e820-111">Exibe mensagens de erro, falha ou de sucesso retornadas pelo analisador individual do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6e820-111">Displays error, failure, or success messages returned from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] individual analyzer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6e820-112">Se a análise demorar muito tempo, você pode interrompê-la. Basta sair do Assistente para Análise do Supervisor de Atualização e depois executar novamente o assistente.</span><span class="sxs-lookup"><span data-stu-id="6e820-112">If the analysis is taking too long, you can stop the analysis, exit the Upgrade Advisor Analysis Wizard, and then rerun the wizard.</span></span> <span data-ttu-id="6e820-113">Para reduzir o tempo da análise, selecione menos componentes para verificar.</span><span class="sxs-lookup"><span data-stu-id="6e820-113">To reduce analysis time, select fewer components to scan.</span></span>  
  
 <span data-ttu-id="6e820-114">Quando a análise estiver completa, o relatório será gravado em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="6e820-114">When analysis is complete, the report is written to a file.</span></span> <span data-ttu-id="6e820-115">Você pode exibir o relatório clicando em **Iniciar relatório** para iniciar o Visualizador de relatórios nesta página.</span><span class="sxs-lookup"><span data-stu-id="6e820-115">You can view the report by clicking **Launch Report** to launch the report viewer from this page.</span></span> <span data-ttu-id="6e820-116">Se desejar exibir o relatório mais tarde, você poderá abrir o **Visualizador de relatórios do supervisor de atualização** na página inicial do supervisor de atualização.</span><span class="sxs-lookup"><span data-stu-id="6e820-116">If you want to view the report later, you can open the **Upgrade Advisor Report Viewer** from the Upgrade Advisor start page.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6e820-117">Os relatórios anteriores são salvos sempre que você analisa um servidor.</span><span class="sxs-lookup"><span data-stu-id="6e820-117">Previous reports are saved every time you analyze a server.</span></span> <span data-ttu-id="6e820-118">Os relatórios são salvos com o carimbo de data/hora do nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="6e820-118">The reports are saved using the timestamp for the file name.</span></span> <span data-ttu-id="6e820-119">O visualizador de relatórios exibe os cinco relatórios mais recentes salvos.</span><span class="sxs-lookup"><span data-stu-id="6e820-119">The report viewer displays the latest five saved reports.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e820-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6e820-120">See Also</span></span>  
 <span data-ttu-id="6e820-121">[Como iniciar o supervisor de atualização](../../../2014/sql-server/install/how-to-launch-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="6e820-121">[How to: Launch Upgrade Advisor](../../../2014/sql-server/install/how-to-launch-upgrade-advisor.md) </span></span>  
 <span data-ttu-id="6e820-122">[Como executar o assistente de análise do supervisor de atualização](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="6e820-122">[How to: Run the Upgrade Advisor Analysis Wizard](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span></span>  
 <span data-ttu-id="6e820-123">[Componentes do SQL Server](../../../2014/sql-server/install/sql-server-components.md) </span><span class="sxs-lookup"><span data-stu-id="6e820-123">[SQL Server Components](../../../2014/sql-server/install/sql-server-components.md) </span></span>  
 <span data-ttu-id="6e820-124">[Referência da interface do usuário do supervisor de atualização](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md) </span><span class="sxs-lookup"><span data-stu-id="6e820-124">[Upgrade Advisor User Interface Reference](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md) </span></span>  
 [<span data-ttu-id="6e820-125">Trabalhando com o Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="6e820-125">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
