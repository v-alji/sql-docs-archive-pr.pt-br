---
title: 'Lição 3: Criar o relatório pai usando o Assistente de Relatório | Microsoft Docs'
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2f69dcd3-cd6d-45a9-a62a-ba6f5f3179d8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f3cb6a0972a2bb63e82e80c02b3ce90912ba01c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570523"
---
# <a name="lesson-3-design-the-parent-report-using-the-report-wizard"></a><span data-ttu-id="f6446-102">Lição 3: Criar o relatório pai usando o Assistente de Relatório</span><span class="sxs-lookup"><span data-stu-id="f6446-102">Lesson 3: Design the Parent Report using the Report Wizard</span></span>
  <span data-ttu-id="f6446-103">Após criar uma conexão de dados e uma tabela de dados para o relatório pai, a próxima etapa será criar o relatório pai usando o Assistente de Relatório no Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="f6446-103">After you create a data connection and a data table for the parent report, your next step is to design the parent report using the Report Wizard in Report Designer.</span></span> <span data-ttu-id="f6446-104">Para obter mais informações sobre o Designer de Relatórios, consulte [Criar relatórios com o Designer de Relatórios &#40;SSRS&#41;](tools/design-reporting-services-paginated-reports-with-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f6446-104">For more information about Report Designer, see [Design Reports with Report Designer &#40;SSRS&#41;](tools/design-reporting-services-paginated-reports-with-report-designer-ssrs.md).</span></span>  
  
### <a name="to-design-the-parent-report-using-the-report-wizard"></a><span data-ttu-id="f6446-105">Para criar o relatório pai usando o Assistente de Relatório</span><span class="sxs-lookup"><span data-stu-id="f6446-105">To design the parent report using the Report Wizard</span></span>  
  
1.  <span data-ttu-id="f6446-106">Verifique se esse site de nível superior está selecionado no **Gerenciador de Soluções**.</span><span class="sxs-lookup"><span data-stu-id="f6446-106">Make sure that the top-level website is selected in **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="f6446-107">Clique com o botão direito do mouse no site e selecione **Adicionar Novo Item**.</span><span class="sxs-lookup"><span data-stu-id="f6446-107">Right-click on the website and select **Add New Item**.</span></span>  
  
3.  <span data-ttu-id="f6446-108">Na caixa de diálogo **Adicionar novo item** , selecione **Assistente de relatório**, insira um nome para o arquivo de relatório e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="f6446-108">In the **Add New Item** dialog box, select **Report Wizard**, enter a name for the report file, and then click **Add**.</span></span>  
  
     <span data-ttu-id="f6446-109">Isso iniciará o Assistente de Relatório.</span><span class="sxs-lookup"><span data-stu-id="f6446-109">This launches the Report Wizard.</span></span>  
  
4.  <span data-ttu-id="f6446-110">Na página **Propriedades do Conjunto de Dados** , na caixa **Fonte de dados** , selecione o **DataSet1** criado na [Lição 2: Definir uma conexão de dados e uma tabela de dados para o relatório pai](lesson-2-define-a-data-connection-and-data-table-for-parent-report.md).</span><span class="sxs-lookup"><span data-stu-id="f6446-110">On the **Dataset Properties** page, in the **Data source** box, select the **DataSet1** you created in [Lesson 2: Define a Data Connection and Data Table for Parent Report](lesson-2-define-a-data-connection-and-data-table-for-parent-report.md).</span></span>  
    <span data-ttu-id="f6446-111">A caixa **Conjuntos de dados disponíveis** é atualizada automaticamente com a **DataTable** criada acima.</span><span class="sxs-lookup"><span data-stu-id="f6446-111">The **Available datasets** box is automatically updated with the **DataTable** you created above.</span></span>  
  
5.  <span data-ttu-id="f6446-112">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f6446-112">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="f6446-113">Na página **Organizar campos** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f6446-113">In the **Arrange Fields** page do the following:</span></span>  
  
    1.  <span data-ttu-id="f6446-114">Arraste **ProductID**, **Name**, **ProductNumber**, **SafetyStockLevel**e **ReorderLevel** de **Campos disponíveis** até a caixa **Valores** .</span><span class="sxs-lookup"><span data-stu-id="f6446-114">Drag **ProductID**, **Name**, **ProductNumber**, **SafetyStockLevel**, and **ReorderLevel** from **Available fields** to the **Values** box.</span></span>  
  
    2.  <span data-ttu-id="f6446-115">Clique na seta ao lado de **Soma (ProductID)**, **Soma (SafetyStockLevel)**, **Soma (ReorderLevel)** e desmarque a seleção **soma** .</span><span class="sxs-lookup"><span data-stu-id="f6446-115">Click the arrow next to **Sum(ProductID)**, **Sum(SafetyStockLevel)**, **Sum(ReorderLevel)** and clear the **Sum** selection.</span></span>  
  
7.  <span data-ttu-id="f6446-116">Clique em **Avançar** duas vezes e, em seguida, clique em **concluir** para fechar o **Assistente de relatório**.</span><span class="sxs-lookup"><span data-stu-id="f6446-116">Click **Next** twice, then click **Finish** to close the **Report Wizard**.</span></span>  
  
     <span data-ttu-id="f6446-117">Agora você criou o arquivo .rdlc.</span><span class="sxs-lookup"><span data-stu-id="f6446-117">You've now created the .rdlc file.</span></span> <span data-ttu-id="f6446-118">O arquivo é aberto no Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="f6446-118">The file opens in Report Designer.</span></span> <span data-ttu-id="f6446-119">Agora, o tablix que você criou será exibido na superfície de design.</span><span class="sxs-lookup"><span data-stu-id="f6446-119">The tablix you designed is now displayed in the design surface.</span></span>  
  
8.  <span data-ttu-id="f6446-120">Salve o arquivo .rdlc.</span><span class="sxs-lookup"><span data-stu-id="f6446-120">Save the .rdlc file.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="f6446-121">Próxima tarefa</span><span class="sxs-lookup"><span data-stu-id="f6446-121">Next Task</span></span>  
 <span data-ttu-id="f6446-122">Você criou o relatório pai com êxito usando o Assistente de Relatório.</span><span class="sxs-lookup"><span data-stu-id="f6446-122">You have successfully designed the parent report using the Report Wizard.</span></span> <span data-ttu-id="f6446-123">Em seguida, você criará uma conexão de dados e uma tabela de dados para o relatório filho.</span><span class="sxs-lookup"><span data-stu-id="f6446-123">Next, you will create a data connection and a data table for the child report.</span></span>  
  
  
