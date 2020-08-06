---
title: Salvar relatórios em um servidor de relatório (Construtor de Relatórios) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 48dfef01-ed8c-4f23-90c3-de67c90a97dd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d80e35c447593e89d422e72ea31ec6be34c3619f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684564"
---
# <a name="save-reports-to-a-report-server-report-builder"></a><span data-ttu-id="aa2aa-102">Salvar relatórios em um servidor de relatório (Construtor de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="aa2aa-102">Save Reports to a Report Server (Report Builder)</span></span>
  <span data-ttu-id="aa2aa-103">No Construtor de Relatórios, é possível salvar uma definição de relatório em um servidor de relatório (processo também conhecido como publicação de relatório).</span><span class="sxs-lookup"><span data-stu-id="aa2aa-103">In Report Builder, you can save a report definition to a report server (also known as publishing a report).</span></span> <span data-ttu-id="aa2aa-104">Quando o relatório for salvo em um servidor de relatório, outros usuários poderão exibi-lo.</span><span class="sxs-lookup"><span data-stu-id="aa2aa-104">When the report is saved to a report server, other users can view the report.</span></span> <span data-ttu-id="aa2aa-105">Cada vez que você executa o relatório publicado, recupera os dados mais atuais.</span><span class="sxs-lookup"><span data-stu-id="aa2aa-105">Each time you run the published report, you will retrieve the most current data.</span></span> <span data-ttu-id="aa2aa-106">Para salvar uma cópia estática de um relatório renderizado, exporte o relatório para um formato de arquivo diferente e salve-o ou use o recurso de histórico de relatório para salvar versões dos relatórios renderizados.</span><span class="sxs-lookup"><span data-stu-id="aa2aa-106">To save a static copy of a rendered report, export the report to a different file format and save it or use the report history feature to save versions of rendered reports.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aa2aa-107">O local da definição de relatório salva não afeta se o relatório é processado no servidor ou localmente quando você o visualiza.</span><span class="sxs-lookup"><span data-stu-id="aa2aa-107">The location of the saved report definition does not affect whether the report is processed on the server or processed locally when you preview the report.</span></span>  
  
### <a name="to-save-a-report-to-a-report-server"></a><span data-ttu-id="aa2aa-108">Para salvar um relatório em um servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="aa2aa-108">To save a report to a report server</span></span>  
  
1.  <span data-ttu-id="aa2aa-109">No botão Construtor de Relatórios, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="aa2aa-109">From the Report Builder button, click **Save**.</span></span> <span data-ttu-id="aa2aa-110">A caixa de diálogo **salvar como** _\<Report Item\>_ é aberta.</span><span class="sxs-lookup"><span data-stu-id="aa2aa-110">The **Save As**_\<Report Item\>_ dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="aa2aa-111">Se você estiver salvando um relatório de novo, ele será salvo novamente automaticamente em seu local anterior.</span><span class="sxs-lookup"><span data-stu-id="aa2aa-111">If you are resaving a report, it is automatically resaved to its previous location.</span></span> <span data-ttu-id="aa2aa-112">Use a opção Salvar como para alterar o local.</span><span class="sxs-lookup"><span data-stu-id="aa2aa-112">Use the Save As option to change location.</span></span>  
  
2.  <span data-ttu-id="aa2aa-113">Se desejar, clique em **Sites e Servidores Recentes** para mostrar uma lista de servidores de relatório e sites do SharePoint usados recentemente.</span><span class="sxs-lookup"><span data-stu-id="aa2aa-113">Optionally, click **Recent Sites and Servers** to show a list of recently used report servers and SharePoint sites.</span></span>  
  
3.  <span data-ttu-id="aa2aa-114">Procure o local do servidor de relatório em que você deseja salvar o relatório.</span><span class="sxs-lookup"><span data-stu-id="aa2aa-114">Browse to the report server location where you want to save the report.</span></span>  
  
4.  <span data-ttu-id="aa2aa-115">Em **Nome**, digite o nome do relatório.</span><span class="sxs-lookup"><span data-stu-id="aa2aa-115">In **Name**, type the name of the report.</span></span>  
  
5.  <span data-ttu-id="aa2aa-116">Em **Itens de tipo**, selecione o tipo de item de relatório que você está salvando.</span><span class="sxs-lookup"><span data-stu-id="aa2aa-116">In **Items of type**, select the type of report item you are saving.</span></span> <span data-ttu-id="aa2aa-117">O tipo de relatórios é Relatórios (\*.rdl).</span><span class="sxs-lookup"><span data-stu-id="aa2aa-117">The type for reports is Reports(\*.rdl).</span></span>  
  
### <a name="to-save-a-report-as-a-different-name"></a><span data-ttu-id="aa2aa-118">Para salvar um relatório com um nome diferente</span><span class="sxs-lookup"><span data-stu-id="aa2aa-118">To save a report as a different name</span></span>  
  
1.  <span data-ttu-id="aa2aa-119">No botão Construtor de Relatórios , clique em **Salvar como**.</span><span class="sxs-lookup"><span data-stu-id="aa2aa-119">From the Report Builder button, click **Save As**.</span></span> <span data-ttu-id="aa2aa-120">A caixa de diálogo **salvar como** _\<Report Item\>_ é aberta.</span><span class="sxs-lookup"><span data-stu-id="aa2aa-120">The **Save As**_\<Report Item\>_ dialog box opens.</span></span>  
  
2.  <span data-ttu-id="aa2aa-121">Vá até o local do servidor de relatório ou o compartilhamento de arquivo em que você deseja salvar o relatório.</span><span class="sxs-lookup"><span data-stu-id="aa2aa-121">Browse to the report server location or to the file share where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="aa2aa-122">Em **Nome**, digite o nome do relatório.</span><span class="sxs-lookup"><span data-stu-id="aa2aa-122">In **Name**, type the name of the report.</span></span>  
  
4.  <span data-ttu-id="aa2aa-123">Em **Itens de tipo**, selecione o tipo de item de relatório que você está salvando.</span><span class="sxs-lookup"><span data-stu-id="aa2aa-123">In **Items of type**, select the type of report item you are saving.</span></span> <span data-ttu-id="aa2aa-124">O tipo de relatórios é Relatórios (\*.rdl).</span><span class="sxs-lookup"><span data-stu-id="aa2aa-124">The type for reports is Reports(\*.rdl).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa2aa-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="aa2aa-125">See Also</span></span>  
 <span data-ttu-id="aa2aa-126">[Localizando, exibindo e gerenciando relatórios &#40;Construtor de Relatórios e SSRS &#41;](finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="aa2aa-126">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="aa2aa-127">[Exportando relatórios &#40;Construtor de Relatórios e SSRS&#41;](export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="aa2aa-127">[Exporting Reports &#40;Report Builder and SSRS&#41;](export-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="aa2aa-128">[Salvando relatórios &#40;Construtor de Relatórios&#41;](saving-reports-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="aa2aa-128">[Saving Reports &#40;Report Builder&#41;](saving-reports-report-builder.md) </span></span>  
 [<span data-ttu-id="aa2aa-129">Exportar um relatório como outro tipo de arquivo &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="aa2aa-129">Export a Report as Another File Type &#40;Report Builder and SSRS&#41;</span></span>](../export-a-report-as-another-file-type-report-builder-and-ssrs.md)  
  
  
