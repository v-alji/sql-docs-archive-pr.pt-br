---
title: 'Lição 6: Adicionar um controle ReportViewer ao aplicativo | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f9492a97-5609-4059-ae76-0fba111d4968
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bb04008fa47801f0500de711592a3cec45ca3dd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582824"
---
# <a name="lesson-6-add-a-reportviewer-control-to-the-application"></a><span data-ttu-id="f7613-102">Lição 6: adicionar um controle ReportViewer ao aplicativo</span><span class="sxs-lookup"><span data-stu-id="f7613-102">Lesson 6: Add a ReportViewer Control to the Application</span></span>
  <span data-ttu-id="f7613-103">Depois que você criar o relatório filho usando o Assistente de Relatório, a próxima etapa será adicionar um controle ReportViewer ao aplicativo de site.</span><span class="sxs-lookup"><span data-stu-id="f7613-103">After you design the child report by using the Report Wizard, your next step is to add a ReportViewer control to the website application.</span></span>  
  
### <a name="to-add-a-reportviewer-control-to-the-application"></a><span data-ttu-id="f7613-104">Para adicionar um controle ReportViewer ao aplicativo</span><span class="sxs-lookup"><span data-stu-id="f7613-104">To add a ReportViewer control to the application</span></span>  
  
1.  <span data-ttu-id="f7613-105">No **Gerenciador de Soluções**, clique com o botão direito do mouse em **Default.aspx**e clique em **Designer de Exibição**.</span><span class="sxs-lookup"><span data-stu-id="f7613-105">In **Solution Explorer**, right-click **Default.aspx**, and then click **View Designer**.</span></span>  
  
2.  <span data-ttu-id="f7613-106">No grupo **Extensões AJAX** na janela **Caixa de Ferramentas** , arraste um controle **ScriptManager** à superfície de design.</span><span class="sxs-lookup"><span data-stu-id="f7613-106">From the **AJAX Extensions** group in the **Toolbox** window, drag a **ScriptManager** control to the design surface.</span></span>  
  
3.  <span data-ttu-id="f7613-107">No grupo **Relatórios** , arraste um controle **ReportViewer** para a superfície de design abaixo do controle **ScriptManager** .</span><span class="sxs-lookup"><span data-stu-id="f7613-107">From the **Reporting** group, drag a **ReportViewer** control to the design surface below the **ScriptManager** control.</span></span>  
  
4.  <span data-ttu-id="f7613-108">Abra a janela **Tarefas do ReportViewer** clicando na seta no canto superior direito do controle de **ReportViewer** .</span><span class="sxs-lookup"><span data-stu-id="f7613-108">Open the **ReportViewer Tasks** window by clicking the arrow in the top right-hand corner of the **ReportViewer** control.</span></span>  
  
5.  <span data-ttu-id="f7613-109">Na caixa **Escolher Relatório** , selecione o relatório pai que você criou.</span><span class="sxs-lookup"><span data-stu-id="f7613-109">In the **Choose Report** box, select Parent report you created.</span></span>  
  
     <span data-ttu-id="f7613-110">Quando você seleciona um relatório, as instâncias das fontes de dados usadas no relatório são criadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f7613-110">When you select a report, instances of data sources used in the report are created automatically.</span></span> <span data-ttu-id="f7613-111">O código é gerado para criar uma instância de cada DataTable (e de seu contêiner [DataSet](https://msdn.microsoft.com/library/system.data.dataset\(v=vs.100\).aspx) ).</span><span class="sxs-lookup"><span data-stu-id="f7613-111">Code is generated to instantiate each DataTable (and its [DataSet](https://msdn.microsoft.com/library/system.data.dataset\(v=vs.100\).aspx) container).</span></span> <span data-ttu-id="f7613-112">Um controle [ObjectDataSource](https://msdn.microsoft.com/library/system.web.ui.webcontrols.objectdatasource\(v=vs.100\).aspx) é adicionado à superfície de design, correspondente a cada fonte de dados usada no relatório.</span><span class="sxs-lookup"><span data-stu-id="f7613-112">An [ObjectDataSource](https://msdn.microsoft.com/library/system.web.ui.webcontrols.objectdatasource\(v=vs.100\).aspx) control is added to the design surface, corresponding to each data source used in the report.</span></span> <span data-ttu-id="f7613-113">Esse controle do código-fonte é configurado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f7613-113">This data source control is configured automatically.</span></span>  
  
     <span data-ttu-id="f7613-114">Se você estiver usando Microsoft Visual Studio 2012, verifique se o controle ObjectDataSource está associado a DataSet1 que é totalmente qualificado com o namespace do projeto, se o nome totalmente qualificado estiver listado na caixa de listagem suspensa **escolher seu objeto comercial** (por exemplo, Projectnamespace. DataSet1TableAdapters. ProductTableAdapter).</span><span class="sxs-lookup"><span data-stu-id="f7613-114">If you're using Microsoft Visual Studio 2012, make sure that the ObjectDataSource control is bound with DataSet1 that is fully qualified with the project namespace, if the fully qualified name is listed in the **Choose your business object** drop-down list box (for example, Projectnamespace.DataSet1TableAdapters.ProductTableAdapter).</span></span> <span data-ttu-id="f7613-115">Acesse a caixa de listagem clicando com o botão direito do mouse em ObjectDataSource e clicando em **Configurar Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="f7613-115">You access the list box by right-clicking ObjectDataSource, and then clicking **Configure Data Source**.</span></span>  
  
6.  <span data-ttu-id="f7613-116">No menu Criar, clique em Criar site.</span><span class="sxs-lookup"><span data-stu-id="f7613-116">On the Build menu, click Build website.</span></span>  
  
     <span data-ttu-id="f7613-117">O relatório é compilado e quaisquer erros como um erro de sintaxe em uma expressão de relatório aparecem na área de **Lista de Erros** .</span><span class="sxs-lookup"><span data-stu-id="f7613-117">The report is compiled and any errors such as a syntax error in a report expression appear in the **Error List** area.</span></span> <span data-ttu-id="f7613-118">Clique em **Lista de Erros** na parte inferior da janela do Visual Studio para exibir a área **Lista de Erros** .</span><span class="sxs-lookup"><span data-stu-id="f7613-118">Click **Error List** at the bottom of the Visual Studio window to display the **Error List** area.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="f7613-119">Próxima tarefa</span><span class="sxs-lookup"><span data-stu-id="f7613-119">Next Task</span></span>  
 <span data-ttu-id="f7613-120">Você adicionou um controle ReportViewer ao aplicativo de site.</span><span class="sxs-lookup"><span data-stu-id="f7613-120">You have successfully added a ReportViewer control to the website application.</span></span> <span data-ttu-id="f7613-121">Em seguida, você adicionar uma ação de detalhamento ao relatório pai.</span><span class="sxs-lookup"><span data-stu-id="f7613-121">Next, you will add a drillthrough action on the parent report.</span></span>  
  
  
