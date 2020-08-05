---
title: Salvar um relatório em uma biblioteca do SharePoint (Construtor de Relatórios) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4daa1eee-78b7-43d0-8b22-4a98e8fa66ba
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 49878a0d7115a11e804382cb5139aa0ec7b3d254
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573779"
---
# <a name="save-a-report-to-a-sharepoint-library-report-builder"></a><span data-ttu-id="bf248-102">Salvar um relatório em uma biblioteca do SharePoint (Construtor de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="bf248-102">Save a Report to a SharePoint Library (Report Builder)</span></span>
  <span data-ttu-id="bf248-103">Para salvar um relatório em um servidor de relatório configurado para integração com o SharePoint, vá até o servidor do SharePoint e estabeleça uma conexão com o servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="bf248-103">To save a report to a report server configured for SharePoint integration, you must browse to the SharePoint server and establish a connection to the report server.</span></span> <span data-ttu-id="bf248-104">Na definição de relatório, todas as referências a itens relacionados ao relatório devem usar valores específicos a um servidor de relatório do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bf248-104">In the report definition, all references to items related to the report must use values that are specific to a SharePoint report server.</span></span> <span data-ttu-id="bf248-105">Os itens relacionados incluem sub-relatórios, relatórios detalhados e recursos, como imagens baseadas na Web.</span><span class="sxs-lookup"><span data-stu-id="bf248-105">Related items include subreports, drillthrough reports, and resources such as Web-based images.</span></span> <span data-ttu-id="bf248-106">Para obter mais informações, consulte [Especificando caminhos para itens externos &#40;Construtor de Relatórios e SSRS&#41;](../report-design/specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bf248-106">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](../report-design/specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="bf248-107">Você deve ter permissão de **Membro** ou **Proprietário** no site do SharePoint para definir as propriedades no projeto.</span><span class="sxs-lookup"><span data-stu-id="bf248-107">You must have **Member** or **Owner** permission on the SharePoint site to set the properties on the project.</span></span>  
  
### <a name="to-save-a-report-to-a-sharepoint-site"></a><span data-ttu-id="bf248-108">Para salvar um relatório em um site do SharePoint</span><span class="sxs-lookup"><span data-stu-id="bf248-108">To save a report to a SharePoint site</span></span>  
  
1.  <span data-ttu-id="bf248-109">No botão Construtor de Relatórios, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="bf248-109">From the Report Builder button, click **Save**.</span></span> <span data-ttu-id="bf248-110">A caixa de diálogo **salvar como** _\<Report Item>_ é aberta.</span><span class="sxs-lookup"><span data-stu-id="bf248-110">The **Save As**_\<Report Item>_ dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bf248-111">Se você estiver salvando um relatório de novo, ele será salvo novamente automaticamente em seu local anterior.</span><span class="sxs-lookup"><span data-stu-id="bf248-111">If you are resaving a report, it is automatically resaved to its previous location.</span></span> <span data-ttu-id="bf248-112">Use a opção **Salvar como** para alterar o local.</span><span class="sxs-lookup"><span data-stu-id="bf248-112">Use the **Save As** option to change location.</span></span>  
  
2.  <span data-ttu-id="bf248-113">Se desejar, clique em **Sites e Servidores Recentes** para mostrar uma lista de servidores de relatório e sites do SharePoint usados recentemente.</span><span class="sxs-lookup"><span data-stu-id="bf248-113">Optionally, click **Recent Sites and Servers** to show a list of recently used report servers and SharePoint sites.</span></span>  
  
3.  <span data-ttu-id="bf248-114">Navegue até o site do SharePoint e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="bf248-114">Browse to the SharePoint site, and then click **Save**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bf248-115">Se você deixar um relatório alterado durante mais de 10 horas sem salvá-lo, ele será desconectado do servidor sem ser salvado.</span><span class="sxs-lookup"><span data-stu-id="bf248-115">If you leave a changed report for more than 10 hours without saving it, it is disconnected from the server without being saved.</span></span> <span data-ttu-id="bf248-116">Se isso acontecer, na barra de status inferior direita, clique em **Desconectar**e clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="bf248-116">If that happens, in the lower-right status bar, click **Disconnect**, and then click **Connect**.</span></span> <span data-ttu-id="bf248-117">O servidor mais recente estará na lista de servidores disponíveis.</span><span class="sxs-lookup"><span data-stu-id="bf248-117">The most recent server will be in the list of available servers.</span></span> <span data-ttu-id="bf248-118">Selecione-o e o relatório reconectará.</span><span class="sxs-lookup"><span data-stu-id="bf248-118">Select it and the report will reconnect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf248-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bf248-119">See Also</span></span>  
 [<span data-ttu-id="bf248-120">Localizando, exibindo e gerenciando relatórios &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bf248-120">Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;</span></span>](finding-viewing-and-managing-reports-report-builder-and-ssrs.md)  
  
  
