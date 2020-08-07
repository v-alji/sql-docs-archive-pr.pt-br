---
title: Criar um relatório vinculado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- linked reports [Reporting Services], creating
ms.assetid: 12be8341-cb57-45e8-a421-2bf66b50234d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ed5e70c9ff8179ae05186685e21303693fc9aed7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575572"
---
# <a name="create-a-linked-report"></a><span data-ttu-id="c841f-102">Criar um relatório vinculado</span><span class="sxs-lookup"><span data-stu-id="c841f-102">Create a Linked Report</span></span>
  <span data-ttu-id="c841f-103">Um relatório vinculado é um item de servidor de relatório que fornece um ponto de acesso a um relatório existente.</span><span class="sxs-lookup"><span data-stu-id="c841f-103">A linked report is a report server item that provides an access point to an existing report.</span></span> <span data-ttu-id="c841f-104">Conceitualmente, é semelhante a um atalho de programa usado para executar um programa ou abrir um arquivo.</span><span class="sxs-lookup"><span data-stu-id="c841f-104">Conceptually, it is similar to a program shortcut that you use to run a program or open a file.</span></span>

 <span data-ttu-id="c841f-105">Um relatório vinculado é derivado de um relatório existente e retém a definição de relatório original.</span><span class="sxs-lookup"><span data-stu-id="c841f-105">A linked report is derived from an existing report and retains the original's report definition.</span></span> <span data-ttu-id="c841f-106">Um relatório vinculado sempre herda as propriedades da fonte de dados e layout de relatório do relatório original.</span><span class="sxs-lookup"><span data-stu-id="c841f-106">A linked report always inherits report layout and data source properties of the original report.</span></span> <span data-ttu-id="c841f-107">Todas as outras propriedades e configurações podem ser diferentes daquelas do relatório original, incluindo segurança, parâmetros, localidade, assinaturas e agendas.</span><span class="sxs-lookup"><span data-stu-id="c841f-107">All other properties and settings can be different from those of the original report, including security, parameters, location, subscriptions, and schedules.</span></span>

 <span data-ttu-id="c841f-108">Você pode criar um relatório vinculado quando você quiser criar versões adicionais de um relatório existente.</span><span class="sxs-lookup"><span data-stu-id="c841f-108">You can create a linked report when you want to create additional versions of an existing report.</span></span> <span data-ttu-id="c841f-109">Por exemplo, você pode usar um único relatório de vendas regional para criar relatórios para regiões específicas para todos os seus territórios de vendas.</span><span class="sxs-lookup"><span data-stu-id="c841f-109">For example, you could use a single regional sales report to create region-specific reports for all of your sales territories.</span></span>

 <span data-ttu-id="c841f-110">Embora os relatórios vinculados sejam normalmente baseados em relatórios com parâmetros, um relatório com parâmetros não é exigido.</span><span class="sxs-lookup"><span data-stu-id="c841f-110">Although linked reports are typically based on parameterized reports, a parameterized report is not required.</span></span> <span data-ttu-id="c841f-111">Você pode criar relatórios vinculados sempre que desejar implantar um relatório existente com configurações diferentes.</span><span class="sxs-lookup"><span data-stu-id="c841f-111">You can create linked reports whenever you want to deploy an existing report with different settings.</span></span>

### <a name="to-create-a-linked-report"></a><span data-ttu-id="c841f-112">Para criar um relatório vinculado</span><span class="sxs-lookup"><span data-stu-id="c841f-112">To create a linked report</span></span>

1.  <span data-ttu-id="c841f-113">No Gerenciador de Relatórios, navegue até a pasta que contém o relatório a ser vinculado, abra o menu de opções e clique em **Criar Relatório Vinculado**.</span><span class="sxs-lookup"><span data-stu-id="c841f-113">In Report Manager, navigate to the folder containing the report that you want to link to, and then open the options menu can click **Create Linked Report**.</span></span>

2.  <span data-ttu-id="c841f-114">Digite um nome para o novo relatório vinculado.</span><span class="sxs-lookup"><span data-stu-id="c841f-114">Type a name for the new linked report.</span></span> <span data-ttu-id="c841f-115">Como opção, digite uma descrição.</span><span class="sxs-lookup"><span data-stu-id="c841f-115">Optionally type a description.</span></span>

3.  <span data-ttu-id="c841f-116">Para selecionar uma pasta diferente para o relatório, clique em **Alterar Local**.</span><span class="sxs-lookup"><span data-stu-id="c841f-116">To select a different folder for the report, click **Change Location**.</span></span> <span data-ttu-id="c841f-117">Clique na pasta que deseja usar ou digite o nome de pasta na caixa **Local** .</span><span class="sxs-lookup"><span data-stu-id="c841f-117">Click the folder you want to use, or type the folder name in the **Location** box.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)] <span data-ttu-id="c841f-118">Se você não selecionar uma pasta diferente, o relatório vinculado será criado na pasta atual (em que o relatório no qual ele se baseia está armazenado).</span><span class="sxs-lookup"><span data-stu-id="c841f-118">If you do not select a different folder, the linked report is created in the current folder (where the report it is based on is stored).</span></span>

4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)] <span data-ttu-id="c841f-119">O relatório vinculado é aberto.</span><span class="sxs-lookup"><span data-stu-id="c841f-119">The linked report opens.</span></span>

     <span data-ttu-id="c841f-120">O ícone de um relatório vinculado difere de outros itens gerenciados por um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="c841f-120">A linked report's icon differs from other items managed by a report server.</span></span> <span data-ttu-id="c841f-121">O ícone a seguir indica um relatório vinculado:</span><span class="sxs-lookup"><span data-stu-id="c841f-121">The following icon indicates a linked report:</span></span>

     <span data-ttu-id="c841f-122">![Ícone do relatório vinculado](../media/hlp-16linked.gif "Ícone do relatório vinculado")</span><span class="sxs-lookup"><span data-stu-id="c841f-122">![Linked report icon](../media/hlp-16linked.gif "Linked report icon")</span></span>

## <a name="see-also"></a><span data-ttu-id="c841f-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c841f-123">See Also</span></span>
 <span data-ttu-id="c841f-124">[Abra e feche um relatório &#40;Report Manager&#41;](../reports/open-and-close-a-report-report-manager.md) [nova página de relatório vinculada &#40;Report Manager](../new-linked-report-page-report-manager.md)&#41;[escolha a página local &#40;](../choose-item-location-page-report-manager.md) Report Manager o SSRS [&#41;&#40;](../report-manager-ssrs-native-mode.md) [de propriedades gerais, relatórios Report Manager&#41;](../general-properties-page-reports-report-manager.md) Reporting Services [conceitos](../reporting-services-concepts-ssrs.md) &#40;</span><span class="sxs-lookup"><span data-stu-id="c841f-124">[Open and Close a Report &#40;Report Manager&#41;](../reports/open-and-close-a-report-report-manager.md) [New Linked Report Page &#40;Report Manager&#41;](../new-linked-report-page-report-manager.md) [Choose Item Location Page &#40;Report Manager&#41;](../choose-item-location-page-report-manager.md) [General Properties Page, Reports &#40;Report Manager&#41;](../general-properties-page-reports-report-manager.md) [Reporting Services Concepts &#40;SSRS&#41;](../reporting-services-concepts-ssrs.md) [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md)</span></span>


