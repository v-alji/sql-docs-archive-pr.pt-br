---
title: Converter uma fonte de dados de inserido em compartilhado (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- data sources [Reporting Services], embedded
- data sources [Reporting Services], shared
ms.assetid: 0e099c7e-8c03-43eb-9ea3-76e52d9ebbe3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5827bab564b58e7a2b7922f01a33f550a6f523f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570463"
---
# <a name="convert-a-data-source-from-embedded-to-shared-report-builder-and-ssrs"></a><span data-ttu-id="a52e0-102">Converter uma fonte de dados inserida em compartilhada (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="a52e0-102">Convert a Data Source from Embedded to Shared (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a52e0-103">Cada fonte de dados no painel de dados do relatório é inserida e específica do relatório ou é compartilhada.</span><span class="sxs-lookup"><span data-stu-id="a52e0-103">Each data source in the Report Data pane is embedded and specific to the report or is shared.</span></span> <span data-ttu-id="a52e0-104">No Construtor de Relatórios, uma fonte de dados compartilhada aponta para uma fonte de dados compartilhada publicada em um servidor de relatório ou no site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a52e0-104">In Report Builder, a shared data source points to a published shared data source on a report server or SharePoint site.</span></span> <span data-ttu-id="a52e0-105">No Designer de Relatórios, uma fonte de dados compartilhada aponta para uma fonte de dados compartilhada na pasta **Fontes de Dados Compartilhadas** do Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="a52e0-105">In Report Designer, a shared data source points to a shared data source in the **Shared Data Sources** folder in Solution Explorer.</span></span>  
  
 <span data-ttu-id="a52e0-106">Para obter mais informações sobre as diferenças entre fontes de dados inseridas e compartilhadas, consulte [Conexões de dados ou fontes de dados inseridas e compartilhadas &#40;Construtor de Relatórios e SSRS&#41;](../embedded-and-shared-data-connections-or-data-sources-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a52e0-106">For more information about the differences between embedded and shared data sources, see [Embedded and Shared Data Connections or Data Sources &#40;Report Builder and SSRS&#41;](../embedded-and-shared-data-connections-or-data-sources-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="a52e0-107">Para obter mais informações sobre como criar uma fonte de dados compartilhada, consulte [Criar uma fonte de dados inserida ou compartilhada &#40;SSRS&#41;](../create-an-embedded-or-shared-data-source-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a52e0-107">For more information on how to create a shared data source, see [Create an Embedded or Shared Data Source &#40;SSRS&#41;](../create-an-embedded-or-shared-data-source-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="report-designer"></a><span data-ttu-id="a52e0-108">Designer de Relatórios</span><span class="sxs-lookup"><span data-stu-id="a52e0-108">Report Designer</span></span>  
  
#### <a name="to-convert-a-data-source-from-embedded-to-shared"></a><span data-ttu-id="a52e0-109">Para converter uma fonte de dados inserida em compartilhada</span><span class="sxs-lookup"><span data-stu-id="a52e0-109">To convert a data source from embedded to shared</span></span>  
  
-   <span data-ttu-id="a52e0-110">No painel Dados do Relatório, clique com o botão direito do mouse na fonte de dados e clique em **Converter em Fonte de Dados Compartilhada**.</span><span class="sxs-lookup"><span data-stu-id="a52e0-110">In the Report Data pane, right-click the data source, and then click **Convert to Shared Data Source**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a52e0-111">Se o painel Dados do Relatório não estiver visível, no menu **Exibir** , clique em **Dados do Relatório**.</span><span class="sxs-lookup"><span data-stu-id="a52e0-111">If the Report Data pane is not visible, on the **View** menu, click **Report Data**.</span></span> <span data-ttu-id="a52e0-112">Se o painel for aberto como uma janela flutuante, você poderá encaixá-la.</span><span class="sxs-lookup"><span data-stu-id="a52e0-112">If the pane opens as a floating window, you can dock it.</span></span> <span data-ttu-id="a52e0-113">Para obter mais informações, consulte [Encaixar o painel de dados do relatório no Designer de Relatórios &#40;SSRS&#41;](../tools/dock-the-report-data-pane-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a52e0-113">For more information, see [Dock the Report Data Pane in Report Designer &#40;SSRS&#41;](../tools/dock-the-report-data-pane-in-report-designer-ssrs.md).</span></span>  
  
     <span data-ttu-id="a52e0-114">No painel de dados do relatório, o ícone da fonte de dados muda para o ícone de fonte de dados compartilhada.</span><span class="sxs-lookup"><span data-stu-id="a52e0-114">In the Report Data pane, the data source icon changes to the shared data source icon.</span></span> <span data-ttu-id="a52e0-115">No Gerenciador de Soluções, uma fonte de dados compartilhada com o mesmo nome é exibida na pasta **Fonte de Dados Compartilhada** .</span><span class="sxs-lookup"><span data-stu-id="a52e0-115">In Solution Explorer, a shared data source with the same name appears under the **Shared Data Source** folder.</span></span>  
  
### <a name="to-convert-a-data-source-from-shared-to-embedded"></a><span data-ttu-id="a52e0-116">Para converter uma fonte de dados de compartilhada em inserida</span><span class="sxs-lookup"><span data-stu-id="a52e0-116">To convert a data source from shared to embedded</span></span>  
  
-   <span data-ttu-id="a52e0-117">No painel Dados do Relatório, clique com o botão direito do mouse na fonte de dados, abra a caixa de diálogo **Propriedades da Fonte de Dados** e clique em **Conexão Inserida**.</span><span class="sxs-lookup"><span data-stu-id="a52e0-117">In the Report Data pane, right-click the data source, open the **Data Source Properties** dialog box, and then click **Embedded Connection**.</span></span> <span data-ttu-id="a52e0-118">Insira as informações necessárias.</span><span class="sxs-lookup"><span data-stu-id="a52e0-118">Enter the required information.</span></span>  
  
     <span data-ttu-id="a52e0-119">No painel de dados do relatório, o ícone da fonte de dados muda para o ícone de fonte de dados compartilhada.</span><span class="sxs-lookup"><span data-stu-id="a52e0-119">In the Report Data pane, the data source icon changes to the shared data source icon.</span></span>  
  
## <a name="report-builder"></a><span data-ttu-id="a52e0-120">Construtor de Relatórios</span><span class="sxs-lookup"><span data-stu-id="a52e0-120">Report Builder</span></span>  
  
#### <a name="to-convert-a-data-source-from-embedded-to-shared"></a><span data-ttu-id="a52e0-121">Para converter uma fonte de dados inserida em compartilhada</span><span class="sxs-lookup"><span data-stu-id="a52e0-121">To convert a data source from embedded to shared</span></span>  
  
-   <span data-ttu-id="a52e0-122">No painel Dados do Relatório, clique com o botão direito do mouse na fonte de dados para abrir a caixa de diálogo **Propriedades da Fonte de Dados** e clique em **Conexão Inserida**.</span><span class="sxs-lookup"><span data-stu-id="a52e0-122">In the Report Data pane, right-click the data source to open the **Data Source Properties** dialog box, and then click **Embedded Connection**.</span></span> <span data-ttu-id="a52e0-123">Insira as informações necessárias.</span><span class="sxs-lookup"><span data-stu-id="a52e0-123">Enter the required information.</span></span>  
  
     <span data-ttu-id="a52e0-124">No painel de dados do relatório, o ícone da fonte de dados muda para o ícone de fonte de dados compartilhada.</span><span class="sxs-lookup"><span data-stu-id="a52e0-124">In the Report Data pane, the data source icon changes to the shared data source icon.</span></span>  
  
#### <a name="to-convert-a-data-source-from-shared-to-embedded"></a><span data-ttu-id="a52e0-125">Para converter uma fonte de dados de compartilhada em inserida</span><span class="sxs-lookup"><span data-stu-id="a52e0-125">To convert a data source from shared to embedded</span></span>  
  
-   <span data-ttu-id="a52e0-126">No painel Dados do Relatório, clique com o botão direito do mouse na fonte de dados, abra a caixa de diálogo **Propriedades da Fonte de Dados** e clique em **Conexão Inserida**.</span><span class="sxs-lookup"><span data-stu-id="a52e0-126">In the Report Data pane, right-click the data source, open the **Data Source Properties** dialog box, and then click **Embedded Connection**.</span></span> <span data-ttu-id="a52e0-127">Insira as informações necessárias.</span><span class="sxs-lookup"><span data-stu-id="a52e0-127">Enter the required information.</span></span>  
  
     <span data-ttu-id="a52e0-128">No painel de dados do relatório, o ícone da fonte de dados muda para o ícone de fonte de dados compartilhada.</span><span class="sxs-lookup"><span data-stu-id="a52e0-128">In the Report Data pane, the data source icon changes to the shared data source icon.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a52e0-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a52e0-129">See Also</span></span>  
 <span data-ttu-id="a52e0-130">[Gerenciar fontes de dados de relatório](manage-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="a52e0-130">[Manage Report Data Sources](manage-report-data-sources.md) </span></span>  
 [<span data-ttu-id="a52e0-131">Conexões de dados, fontes de dados e cadeias de conexão no Reporting Services</span><span class="sxs-lookup"><span data-stu-id="a52e0-131">Data Connections, Data Sources, and Connection Strings in Reporting Services</span></span>](../data-connections-data-sources-and-connection-strings-in-reporting-services.md)  
  
  
