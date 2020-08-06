---
title: 'Lição 5: Criar o relatório filho usando o Assistente de Relatório | Microsoft Docs'
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 19a3f927-ea97-4f40-a5f8-cd5f2598e4da
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f188a914fc2a2bb8370843191a31474a54c02aa8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570517"
---
# <a name="lesson-5-design-the-child-report-using-the-report-wizard"></a><span data-ttu-id="1d27f-102">Lição 5: Criar o relatório filho usando o Assistente de Relatório</span><span class="sxs-lookup"><span data-stu-id="1d27f-102">Lesson 5: Design the Child Report using the Report Wizard</span></span>
  <span data-ttu-id="1d27f-103">Após criar uma conexão de dados e uma tabela de dados para o relatório filho, a próxima etapa será criar o relatório filho usando o Assistente de Relatório no Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="1d27f-103">After you create a data connection and data table for the child report, your next step is to design the child report using the Report Wizard in Report Designer.</span></span> <span data-ttu-id="1d27f-104">Para obter mais informações sobre o Designer de Relatórios, consulte [Criar relatórios com o Designer de Relatórios &#40;SSRS&#41;](tools/design-reporting-services-paginated-reports-with-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1d27f-104">For more information about Report Designer, see [Design Reports with Report Designer &#40;SSRS&#41;](tools/design-reporting-services-paginated-reports-with-report-designer-ssrs.md).</span></span>  
  
### <a name="to-design-the-child-report-using-the-report-wizard"></a><span data-ttu-id="1d27f-105">Para criar o relatório filho usando o Assistente de Relatório</span><span class="sxs-lookup"><span data-stu-id="1d27f-105">To design the child report using the Report Wizard</span></span>  
  
1.  <span data-ttu-id="1d27f-106">Verifique se esse site de nível superior está selecionado no **Gerenciador de Soluções**.</span><span class="sxs-lookup"><span data-stu-id="1d27f-106">Make sure that the top-level website is selected in **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="1d27f-107">Clique com o botão direito do mouse no site e selecione **Adicionar Novo Item**.</span><span class="sxs-lookup"><span data-stu-id="1d27f-107">Right-click on the website and select **Add New Item**.</span></span>  
  
3.  <span data-ttu-id="1d27f-108">Na caixa de diálogo **Adicionar novo item** , clique em **Assistente de relatório**, insira um nome para o arquivo de relatório e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1d27f-108">In the **Add New Item** dialog box, click **Report Wizard**, enter a name for the report file, and then click **Add**.</span></span>  
  
     <span data-ttu-id="1d27f-109">Isso iniciará o Assistente de Relatório.</span><span class="sxs-lookup"><span data-stu-id="1d27f-109">This launches the Report Wizard.</span></span>  
  
4.  <span data-ttu-id="1d27f-110">Na página **Propriedades de DataSet** , na caixa **fonte de dados** , clique em **DataSet2**.</span><span class="sxs-lookup"><span data-stu-id="1d27f-110">In the **Dataset Properties** page, in the **Data source** box, click **DataSet2**.</span></span>  
  
     <span data-ttu-id="1d27f-111">A caixa **Conjuntos de dados disponíveis** é atualizada automaticamente com a DataTable criada.</span><span class="sxs-lookup"><span data-stu-id="1d27f-111">The **Available datasets** box is automatically updated with the DataTable you created.</span></span>  
  
5.  <span data-ttu-id="1d27f-112">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1d27f-112">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="1d27f-113">Na página **Organizar campos** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1d27f-113">In the **Arrange Fields** page do the following:</span></span>  
  
    1.  <span data-ttu-id="1d27f-114">Arraste **ProductID**, **PurchaseOrderID**, **PurchaseOrderDetailID**, **OrderQty**, **ReceivedQty**, **RejectedQty**e **StockedQty** de **Campos disponíveis** até a caixa **Valores** .</span><span class="sxs-lookup"><span data-stu-id="1d27f-114">Drag **ProductID**, **PurchaseOrderID**, **PurchaseOrderDetailID**, **OrderQty**, **ReceivedQty**, **RejectedQty**, and **StockedQty** from **Available Fields** to the **Values** box.</span></span>  
  
    2.  <span data-ttu-id="1d27f-115">Clique na seta ao lado de **Soma (ProductID)**, **Soma (PurchaseOrderID)**, **Soma (PurchaseOrderDetailID)**, **Soma (OrderQty)**, **Soma (ReceivedQty)**, **Soma (RejectedQty)** e **Soma (StockedQty)** e desmarque a seleção **soma** .</span><span class="sxs-lookup"><span data-stu-id="1d27f-115">Click the arrow next to **Sum(ProductID)**, **Sum(PurchaseOrderID)**, **Sum(PurchaseOrderDetailID)**, **Sum(OrderQty)**, **Sum(ReceivedQty)**, **Sum(RejectedQty)**, and **Sum(StockedQty)** and clear the **Sum** selection.</span></span>  
  
7.  <span data-ttu-id="1d27f-116">Clique em **Avançar** duas vezes e, em seguida, clique em **concluir** para fechar o **Assistente de relatório**.</span><span class="sxs-lookup"><span data-stu-id="1d27f-116">Click **Next** twice, then click **Finish** to close the **Report Wizard**.</span></span>  
  
     <span data-ttu-id="1d27f-117">Agora você criou o arquivo .rdlc.</span><span class="sxs-lookup"><span data-stu-id="1d27f-117">You've now created the .rdlc file.</span></span> <span data-ttu-id="1d27f-118">O arquivo é aberto no Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="1d27f-118">The file opens in Report Designer.</span></span> <span data-ttu-id="1d27f-119">Agora, o tablix que você criou será exibido na superfície de design.</span><span class="sxs-lookup"><span data-stu-id="1d27f-119">The tablix you designed is now displayed in the design surface.</span></span>  
  
8.  <span data-ttu-id="1d27f-120">Com o arquivo .rdlc aberto, adicione um parâmetro da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="1d27f-120">With the .rdlc file open, add a parameter by doing the following:</span></span>  
  
    1.  <span data-ttu-id="1d27f-121">Clique em **parâmetros** no painel **dados do relatório** e, em seguida, clique em **adicionar parâmetros**.</span><span class="sxs-lookup"><span data-stu-id="1d27f-121">Click **Parameters** in the **Report Data** pane, and then click **Add Parameters**.</span></span>  
  
    2.  <span data-ttu-id="1d27f-122">Insira **productid** na caixa **Nome** .</span><span class="sxs-lookup"><span data-stu-id="1d27f-122">Enter **productid** in the **Name** box.</span></span>  
  
    3.  <span data-ttu-id="1d27f-123">Confirme se a opção **Inteiro** está selecionada na caixa de listagem **Tipo de Dados** .</span><span class="sxs-lookup"><span data-stu-id="1d27f-123">Confirm that **Integer** is selected in the **Data Type** list box.</span></span>  
  
    4.  <span data-ttu-id="1d27f-124">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1d27f-124">Click **OK**.</span></span>  
  
9. <span data-ttu-id="1d27f-125">Salve o arquivo .rdlc.</span><span class="sxs-lookup"><span data-stu-id="1d27f-125">Save the .rdlc file.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="1d27f-126">Próxima tarefa</span><span class="sxs-lookup"><span data-stu-id="1d27f-126">Next Task</span></span>  
 <span data-ttu-id="1d27f-127">Você criou o relatório filho com êxito usando o Assistente de Relatório.</span><span class="sxs-lookup"><span data-stu-id="1d27f-127">You have successfully designed the child report by using the Report Wizard.</span></span> <span data-ttu-id="1d27f-128">Em seguida, você adicionará um controle ReportViewer ao aplicativo de site.</span><span class="sxs-lookup"><span data-stu-id="1d27f-128">Next, you will add a ReportViewer control to the website application.</span></span>  
  
  
