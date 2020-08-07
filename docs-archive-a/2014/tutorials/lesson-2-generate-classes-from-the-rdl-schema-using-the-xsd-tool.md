---
title: 'Lição 2: gerar classes a partir do esquema RDL usando a ferramenta xsd | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a81c87f1-7977-4b30-b6ac-b38b3e2b6398
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 2c5db118ad8f94afc72cea44b9a2489f2b4fd7f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681967"
---
# <a name="lesson-2-generate-classes-from-the-rdl-schema-using-the-xsd-tool"></a><span data-ttu-id="15f7d-102">Lição 2: Gerar classes do esquema RDL usando a ferramenta xsd </span><span class="sxs-lookup"><span data-stu-id="15f7d-102">Lesson 2: Generate Classes from the RDL Schema using the xsd Tool</span></span>
  <span data-ttu-id="15f7d-103">Depois que você criar seu projeto do [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], a próxima etapa será recuperar uma cópia local do esquema de definição de relatório e executar a Ferramenta de Definição de Esquema XML (Xsd.exe).</span><span class="sxs-lookup"><span data-stu-id="15f7d-103">After you have created your [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] project, the next step is to retrieve a local copy of the report definition schema and run the XML Schema Definition Tool (Xsd.exe).</span></span>  
  
### <a name="to-generate-the-rdl-classes"></a><span data-ttu-id="15f7d-104">Para gerar as classes RDL</span><span class="sxs-lookup"><span data-stu-id="15f7d-104">To generate the RDL classes</span></span>  
  
1.  <span data-ttu-id="15f7d-105">Abra uma instância do [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Explorer (ou navegador da Web equivalente) e navegue até a seguinte URL:</span><span class="sxs-lookup"><span data-stu-id="15f7d-105">Open an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Explorer (or equivalent Web browser) and navigate to the following URL:</span></span>  
  
    ```  
    https://schemas.microsoft.com/sqlserver/reporting/2010/01/reportdefinition/ReportDefinition.xsd  
    ```  
  
2.  <span data-ttu-id="15f7d-106">Depois que o esquema RDL tiver sido aberto no navegador, navegue até o menu **arquivo** e selecione **salvar como**.</span><span class="sxs-lookup"><span data-stu-id="15f7d-106">Once the RDL schema has been opened in the browser, browse to the **File** menu, and select **Save As**.</span></span>  
  
3.  <span data-ttu-id="15f7d-107">Navegue até o local em que você criou o projeto do [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] e salve o esquema com o nome de arquivo ReportDefinition.xsd.</span><span class="sxs-lookup"><span data-stu-id="15f7d-107">Browse to the location where you created your [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] project and save the schema with the file name ReportDefinition.xsd.</span></span>  
  
4.  <span data-ttu-id="15f7d-108">Depois que o arquivo tiver sido salvo, abra uma instância do [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="15f7d-108">After the file has been saved, open an instance of the [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] command prompt.</span></span> <span data-ttu-id="15f7d-109">Para abrir uma instância do prompt de comando, clique no menu Iniciar, aponte para **todos os programas**, aponte para **Microsoft Visual Studio 2010**, aponte para **Ferramentas do Visual Studio** e clique em **prompt de comando do Visual Studio (2010)**.</span><span class="sxs-lookup"><span data-stu-id="15f7d-109">To open an instance of the command prompt, click the Start menu, point to **All Programs**, point to **Microsoft Visual Studio 2010**, point to **Visual Studio Tools** and click **Visual Studio Command Prompt (2010)**.</span></span>  
  
5.  <span data-ttu-id="15f7d-110">Altere o caminho atual para o local em que você salvou o arquivo ReportDefinition.xsd:</span><span class="sxs-lookup"><span data-stu-id="15f7d-110">Change the current path to the location where you saved the ReportDefinition.xsd file:</span></span>  
  
     `CD\<ReportDefinition.xsd Path>`  
  
6.  <span data-ttu-id="15f7d-111">Gere o arquivo ReportDefinition.cs que contém as classes para o esquema RDL com o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="15f7d-111">Generate the ReportDefinition.cs file that contains the classes for the RDL schema with the following command:</span></span>  
  
     `xsd /c /n:SampleRDLSchema ReportDefinition.xsd`  
  
     <span data-ttu-id="15f7d-112">Para gerar um arquivo ReportDefinition.vb, use este comando:</span><span class="sxs-lookup"><span data-stu-id="15f7d-112">To generate a ReportDefinition.vb file use this command:</span></span>  
  
     `xsd /c /l:VB /n:SampleRDLSchema ReportDefinition.xsd`  
  
7.  <span data-ttu-id="15f7d-113">Adicionar ReportDefinition.xsd a seu projeto.</span><span class="sxs-lookup"><span data-stu-id="15f7d-113">Add ReportDefinition.xsd your project.</span></span> <span data-ttu-id="15f7d-114">No menu **projeto** , clique em **Adicionar item existente**.</span><span class="sxs-lookup"><span data-stu-id="15f7d-114">From the **Project** menu, click **Add Existing Item**.</span></span> <span data-ttu-id="15f7d-115">Navegue até o local do arquivo ReportDefinition. xsd, selecione ReportDefinition. xsd e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="15f7d-115">Browse to the location of the ReportDefinition.xsd file, select ReportDefinition.xsd, and click **Add**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="15f7d-116">Depois de adicionar o arquivo ReportDefinition. xsd ao projeto, você notará em **Gerenciador de soluções** que o arquivo ReportDefinition.cs (. vb) não está lá.</span><span class="sxs-lookup"><span data-stu-id="15f7d-116">After you have added the ReportDefinition.xsd file to the project you will notice in **Solution Explorer** that the ReportDefinition.cs (.vb) file is not there.</span></span> <span data-ttu-id="15f7d-117">Para exibir o arquivo, clique no botão expandir/recolher ao lado do arquivo ReportDefinition.xsd.</span><span class="sxs-lookup"><span data-stu-id="15f7d-117">To display the file, click the expand/collapse button next to the ReportDefinition.xsd file.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="15f7d-118">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="15f7d-118">Next Lesson</span></span>  
 <span data-ttu-id="15f7d-119">Na próxima lição, você escreverá código para carregar uma definição de relatório de um servidor de relatório usando as classes geradas com base no esquema RDL.</span><span class="sxs-lookup"><span data-stu-id="15f7d-119">In the next lesson, you will write code to load a report definition from a report server using the classes you generated from the RDL schema.</span></span> <span data-ttu-id="15f7d-120">Consulte [lição 3: carregar uma definição de relatório do servidor de relatório](../../2014/tutorials/lesson-3-load-a-report-definition-from-the-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="15f7d-120">See [Lesson 3: Load a Report Definition from the Report Server](../../2014/tutorials/lesson-3-load-a-report-definition-from-the-report-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15f7d-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="15f7d-121">See Also</span></span>  
 <span data-ttu-id="15f7d-122">[Atualizando relatórios usando classes geradas do esquema RDL &#40;tutorial do SSRS&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="15f7d-122">[Updating Reports Using Classes Generated from the RDL Schema &#40;SSRS Tutorial&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span></span>  
 [<span data-ttu-id="15f7d-123">Linguagem RDL &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="15f7d-123">Report Definition Language &#40;SSRS&#41;</span></span>](../reporting-services/reports/report-definition-language-ssrs.md)  
  
  
