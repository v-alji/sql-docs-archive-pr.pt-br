---
title: 'Lição 9: Criar e executar o aplicativo | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f52d3f3a-0b09-4b34-9112-0b3655271587
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 068deb075f0f60dde634ac29f6f8f934448dc6a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570509"
---
# <a name="lesson-9-build-and-run-the-application"></a><span data-ttu-id="2431b-102">Lesson 9: Build and Run the Application</span><span class="sxs-lookup"><span data-stu-id="2431b-102">Lesson 9: Build and Run the Application</span></span>
  <span data-ttu-id="2431b-103">Após criar um filtro de dados para a tabela de dados, a próxima etapa será criar e executar o aplicativo de site.</span><span class="sxs-lookup"><span data-stu-id="2431b-103">After you create a data filter for the data table, your next step is to build and run the website application.</span></span>

### <a name="to-build-and-run-the-application"></a><span data-ttu-id="2431b-104">Para criar e executar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="2431b-104">To build and run the application</span></span>

1.  <span data-ttu-id="2431b-105">Pressione **CTRL+F5** para executar a página Default.aspx sem depuração ou pressione F5 para executar a página com depuração.</span><span class="sxs-lookup"><span data-stu-id="2431b-105">Press **CTRL+F5** to run the Default.aspx page without debugging, or press F5 to run the page with debugging.</span></span>

     <span data-ttu-id="2431b-106">Como parte do processo de criação, o relatório é compilado e todos os erros encontrados (por exemplo, um erro de sintaxe em uma expressão usada no relatório) são adicionados à **Lista de Tarefas** , localizada na parte inferior da janela do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2431b-106">As part of the build process, the report is compiled and any errors found (such as a syntax error in an expression used in the report) are added to the **Task List** that is located at the bottom of the Visual Studio window.</span></span>

     <span data-ttu-id="2431b-107">A página da Web aparece no navegador.</span><span class="sxs-lookup"><span data-stu-id="2431b-107">The webpage appears in the browser.</span></span> <span data-ttu-id="2431b-108">O controle ReportViewer exibe o relatório.</span><span class="sxs-lookup"><span data-stu-id="2431b-108">The ReportViewer control displays the report.</span></span> <span data-ttu-id="2431b-109">Você pode usar a barra de ferramentas para navegar pelo relatório, aplicar zoom e exportar o relatório para o Excel.</span><span class="sxs-lookup"><span data-stu-id="2431b-109">You can use the toolbar to browse through the report, zoom, and export the report to Excel.</span></span>

2.  <span data-ttu-id="2431b-110">Passe o mouse sobre qualquer uma das linhas na coluna **Nome** .</span><span class="sxs-lookup"><span data-stu-id="2431b-110">Hover the mouse over any of the rows under **Name** column.</span></span> <span data-ttu-id="2431b-111">O cursor do mouse exibirá um símbolo de mão.</span><span class="sxs-lookup"><span data-stu-id="2431b-111">The mouse cursor will display a Hand symbol.</span></span>

3.  <span data-ttu-id="2431b-112">Clique em um valor na coluna **Nome** .</span><span class="sxs-lookup"><span data-stu-id="2431b-112">Click a value in the **Name** column.</span></span> <span data-ttu-id="2431b-113">O relatório filho é mostrado com os dados filtrados correspondentes.</span><span class="sxs-lookup"><span data-stu-id="2431b-113">The child report is shown with the corresponding filtered data.</span></span>

4.  <span data-ttu-id="2431b-114">Clique no ícone **Voltar para o relatório pai**na barra de ferramentas **ReportViewer** para retornar ao relatório **Pai** .</span><span class="sxs-lookup"><span data-stu-id="2431b-114">Click the icon, **Go back to parent report**, in the **ReportViewer** tool bar to navigate back to the **Parent** report.</span></span>

     <span data-ttu-id="2431b-115">![detalhamento do SSRS usando o ReportViewer](../../2014/tutorials/media/ssrs-drillthrough-report.png "detalhamento do SSRS usando o ReportViewer")</span><span class="sxs-lookup"><span data-stu-id="2431b-115">![ssrs drill through using ReportViewer](../../2014/tutorials/media/ssrs-drillthrough-report.png "ssrs drill through using ReportViewer")</span></span>

5.  <span data-ttu-id="2431b-116">Feche o navegador para sair.</span><span class="sxs-lookup"><span data-stu-id="2431b-116">Close the browser to exit.</span></span>


