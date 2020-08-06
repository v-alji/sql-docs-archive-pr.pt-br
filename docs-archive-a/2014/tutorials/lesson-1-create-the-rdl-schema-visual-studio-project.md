---
title: 'Lição 1: criar o projeto de esquema RDL do Visual Studio | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f420509c-51aa-4170-8c25-64c2954f4bb9
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: a8411e3f0458ccda8c291d5c86a4467bb051a263
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678379"
---
# <a name="lesson-1-create-the-rdl-schema-visual-studio-project"></a><span data-ttu-id="da7b6-102">Lição 1: Criar o projeto do Visual Studio de esquema RDL</span><span class="sxs-lookup"><span data-stu-id="da7b6-102">Lesson 1: Create the RDL Schema Visual Studio Project</span></span>
  <span data-ttu-id="da7b6-103">Para este tutorial, você criará um aplicativo de console simples.</span><span class="sxs-lookup"><span data-stu-id="da7b6-103">For this tutorial, you will create a simple console application.</span></span> <span data-ttu-id="da7b6-104">Este tutorial pressupõe que você está desenvolvendo no [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="da7b6-104">This tutorial assumes you are developing in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="da7b6-105">Ao acessar o serviço Web Servidor de Relatório que está em execução no [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] com Advanced Services, é preciso incluir "_SQLExpress" no caminho do "ReportServer".</span><span class="sxs-lookup"><span data-stu-id="da7b6-105">When accessing the Report Server Web service running on [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] with Advanced Services, you must append "_SQLExpress" to the "ReportServer" path.</span></span> <span data-ttu-id="da7b6-106">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="da7b6-106">For example:</span></span>  
>   
>  `http://myserver/reportserver_sqlexpress/reportservice2010.asmx"`  
  
### <a name="to-create-the-web-service-proxy"></a><span data-ttu-id="da7b6-107">Para criar o proxy do serviço Web</span><span class="sxs-lookup"><span data-stu-id="da7b6-107">To create the web service proxy</span></span>  
  
1.  <span data-ttu-id="da7b6-108">No menu **Iniciar** , selecione **todos os programas**, Microsoft Visual Studio, em seguida, **Ferramentas do Visual Studio**e, em seguida, o Prompt de **comando do Visual Studio 2010**.</span><span class="sxs-lookup"><span data-stu-id="da7b6-108">From the **Start** menu, select **All Programs**, then Microsoft Visual Studio, then **Visual Studio Tools**, and then **Visual Studio 2010 Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="da7b6-109">Na janela do prompt de comando, execute o seguinte comando se estiver usando o C#:</span><span class="sxs-lookup"><span data-stu-id="da7b6-109">In the command prompt window, run the following command if you are using C#:</span></span>  
  
    ```  
    wsdl /language:CS /n:"ReportService2010" http://<Server Name>/reportserver/reportservice2010.asmx?wsdl  
    ```  
  
     <span data-ttu-id="da7b6-110">Se estiver usando o Visual Basic, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="da7b6-110">If you are using Visual Basic, then run the following command:</span></span>  
  
    ```  
    wsdl /language:VB /n:"ReportService2010" http://<Server Name>/reportserver/reportservice2010.asmx?wsdl  
    ```  
  
     <span data-ttu-id="da7b6-111">Esse comando gera um arquivo .cs ou .vb.</span><span class="sxs-lookup"><span data-stu-id="da7b6-111">This command generates a .cs or .vb file.</span></span> <span data-ttu-id="da7b6-112">Adicione esse arquivo ao seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="da7b6-112">You will add this file to your application.</span></span>  
  
### <a name="to-create-a-console-application"></a><span data-ttu-id="da7b6-113">Para criar um aplicativo de console</span><span class="sxs-lookup"><span data-stu-id="da7b6-113">To create a console application</span></span>  
  
1.  <span data-ttu-id="da7b6-114">No menu **arquivo** , aponte para **novo**e clique em **projeto** para abrir a caixa de diálogo **novo projeto** .</span><span class="sxs-lookup"><span data-stu-id="da7b6-114">On the **File** menu, point to **New**, and then click **Project** to open the **New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="da7b6-115">No painel esquerdo, em **modelos instalados**, clique em **Visual Basic** ou no nó **Visual C#** e selecione uma categoria de tipos de projeto na lista expandida.</span><span class="sxs-lookup"><span data-stu-id="da7b6-115">In the left pane, under **Installed Templates**, click either **Visual Basic** or the **Visual C#** node, and select a category of project types from the expanded list.</span></span>  
  
3.  <span data-ttu-id="da7b6-116">Escolha o tipo de projeto de **aplicativo de console** .</span><span class="sxs-lookup"><span data-stu-id="da7b6-116">Choose the **Console Application** project type.</span></span>  
  
4.  <span data-ttu-id="da7b6-117">Na caixa **nome** , insira um nome para o seu projeto.</span><span class="sxs-lookup"><span data-stu-id="da7b6-117">In the **Name** box, enter a name for your project.</span></span> <span data-ttu-id="da7b6-118">Digite o nome `SampleRDLSchema` .</span><span class="sxs-lookup"><span data-stu-id="da7b6-118">Type the name `SampleRDLSchema`.</span></span>  
  
5.  <span data-ttu-id="da7b6-119">Na caixa **local** , digite o caminho onde você deseja salvar o projeto ou clique em **procurar** para navegar até a pasta.</span><span class="sxs-lookup"><span data-stu-id="da7b6-119">In the **Location** box, type the path where you want to save your project, or click **Browse** to navigate to the folder.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]<span data-ttu-id="da7b6-120">Uma exibição recolhida do seu projeto é exibida no Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="da7b6-120">A collapsed view of your project appears in Solution Explorer.</span></span>  
  
7.  <span data-ttu-id="da7b6-121">No menu **Projeto** , clique em **Adicionar Item Existente**.</span><span class="sxs-lookup"><span data-stu-id="da7b6-121">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
8.  <span data-ttu-id="da7b6-122">Navegue até o local do arquivo. cs ou. vb gerado por você e, em seguida, selecione o arquivo e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="da7b6-122">Navigate to the location for the .cs or .vb file you generated, then select the file, and then click **Add**.</span></span>  
  
     <span data-ttu-id="da7b6-123">Você também precisará adicionar uma referência ao namespace <xref:System.Web.Services> para que a referência da Web funcione.</span><span class="sxs-lookup"><span data-stu-id="da7b6-123">You will also need to add a reference to the <xref:System.Web.Services> namespace for your Web reference to work.</span></span>  
  
9. <span data-ttu-id="da7b6-124">No menu Projeto, clique em **Adicionar Referência**.</span><span class="sxs-lookup"><span data-stu-id="da7b6-124">On the Project menu, click **Add Reference**.</span></span>  
  
     <span data-ttu-id="da7b6-125">Na caixa de diálogo **Adicionar referência** , na guia **.net** , selecione **System. Web. Services**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="da7b6-125">In the **Add Reference** dialog box, in the **.NET** tab, select **System.Web.Services**, then click **OK**.</span></span>  
  
     <span data-ttu-id="da7b6-126">Para obter mais informações sobre como se conectar ao serviço Web servidor de relatórios, consulte [criando aplicativos usando o serviço Web e o .NET Framework](../reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md).</span><span class="sxs-lookup"><span data-stu-id="da7b6-126">For more information about how to connect to the Report Server Web service, see [Building Applications Using the Web Service and the .NET Framework](../reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md).</span></span>  
  
10. <span data-ttu-id="da7b6-127">No Gerenciador de Soluções, expanda o nó do projeto.</span><span class="sxs-lookup"><span data-stu-id="da7b6-127">In Solution Explorer, expand the project node.</span></span> <span data-ttu-id="da7b6-128">Você verá que um arquivo de código com o nome padrão de Program.cs (Module1.vb para o [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) foi adicionado ao seu projeto.</span><span class="sxs-lookup"><span data-stu-id="da7b6-128">You will see a code file with the default name of Program.cs (Module1.vb for [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) has been added to your project.</span></span>  
  
11. <span data-ttu-id="da7b6-129">Abra o arquivo Program.cs (Module1.vb para o [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) e substitua o código pelo seguinte:</span><span class="sxs-lookup"><span data-stu-id="da7b6-129">Open the Program.cs (Module1.vb for [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) file and replace the code with the following:</span></span>  
  
     <span data-ttu-id="da7b6-130">O código a seguir fornece os fragmentos de método que serão utilizados para implementar a funcionalidade Carregar, Atualizar e Salvar.</span><span class="sxs-lookup"><span data-stu-id="da7b6-130">The following code provides the method stubs we will use to implement the Load, Update and Save functionality.</span></span>  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.IO;  
    using System.Text;  
    using System.Xml;  
    using System.Xml.Serialization;  
    using ReportService2010;  
  
    namespace SampleRDLSchema  
    {  
        class ReportUpdater  
        {  
            ReportingService2010 _reportService;  
  
            static void Main(string[] args)  
            {  
                ReportUpdater reportUpdater = new ReportUpdater();  
                reportUpdater.UpdateReport();  
            }  
  
            private void UpdateReport()  
            {  
                try  
                {  
                    // Set up the Report Service connection  
                    _reportService = new ReportingService2010();  
                    _reportService.Credentials =  
                        System.Net.CredentialCache.DefaultCredentials;  
                    _reportService.Url =  
                       "http://<Server Name>/reportserver/" +  
                                       "reportservice2010.asmx";  
  
                    // Call the methods to update a report definition  
                    LoadReportDefinition();  
                    UpdateReportDefinition();  
                    PublishReportDefinition();  
                }  
                catch (Exception ex)  
                {  
                    System.Console.WriteLine(ex.Message);  
                }  
            }  
  
            private void LoadReportDefinition()  
            {  
                //Lesson 3: Load a report definition from the report   
                //          catalog  
            }  
  
            private void UpdateReportDefinition()  
            {  
                //Lesson 4: Update the report definition using the    
                //          classes generated from the RDL Schema  
            }  
  
            private void PublishReportDefinition()  
            {  
                //Lesson 5: Publish the updated report definition back   
                //          to the report catalog  
            }  
        }  
    }  
    ```  
  
    ```vb  
    Imports System  
    Imports System.Collections.Generic  
    Imports System.IO  
    Imports System.Text  
    Imports System.Xml  
    Imports System.Xml.Serialization  
    Imports ReportService2010  
  
    Namespace SampleRDLSchema  
  
        Module ReportUpdater  
  
            Private m_reportService As ReportingService2010  
  
            Public Sub Main(ByVal args As String())  
  
                Try  
                    'Set up the Report Service connection  
                    m_reportService = New ReportingService2010  
                    m_reportService.Credentials = _  
                        System.Net.CredentialCache.DefaultCredentials  
                    m_reportService.Url = _  
                        "http:// <Server Name>/reportserver/" & _  
                               "reportservice2010.asmx"  
  
                    'Call the methods to update a report definition  
                    LoadReportDefinition()  
                    UpdateReportDefinition()  
                    PublishReportDefinition()  
                Catch ex As Exception  
                    System.Console.WriteLine(ex.Message)  
                End Try  
  
            End Sub  
  
            Private Sub LoadReportDefinition()  
                'Lesson 3: Load a report definition from the report   
                '          catalog  
            End Sub  
  
            Private Sub UpdateReportDefinition()  
                'Lesson 4: Update the report definition using the   
                '          classes generated from the RDL Schema  
            End Sub  
  
            Private Sub PublishReportDefinition()  
                'Lesson 5: Publish the updated report definition back   
                '          to the report catalog  
            End Sub  
  
        End Module  
  
    End Namespace   
    ```  
  
## <a name="next-lesson"></a><span data-ttu-id="da7b6-131">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="da7b6-131">Next Lesson</span></span>  
 <span data-ttu-id="da7b6-132">Na próxima lição, você usará a Ferramenta de Definição de Esquema XML (Xsd.exe) para gerar classes com base no esquema RDL e incluí-las no seu projeto.</span><span class="sxs-lookup"><span data-stu-id="da7b6-132">In the next lesson, you will use the XML Schema Definition Tool (Xsd.exe) to generate classes from the RDL schema and include them in your project.</span></span> <span data-ttu-id="da7b6-133">Consulte [lição 2: gerar classes a partir do esquema RDL usando a ferramenta xsd](../../2014/tutorials/lesson-2-generate-classes-from-the-rdl-schema-using-the-xsd-tool.md).</span><span class="sxs-lookup"><span data-stu-id="da7b6-133">See [Lesson 2: Generate Classes from the RDL Schema using the xsd Tool](../../2014/tutorials/lesson-2-generate-classes-from-the-rdl-schema-using-the-xsd-tool.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da7b6-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="da7b6-134">See Also</span></span>  
 <span data-ttu-id="da7b6-135">[Atualizando relatórios usando classes geradas do esquema RDL &#40;tutorial do SSRS&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="da7b6-135">[Updating Reports Using Classes Generated from the RDL Schema &#40;SSRS Tutorial&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span></span>  
 [<span data-ttu-id="da7b6-136">Linguagem RDL &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="da7b6-136">Report Definition Language &#40;SSRS&#41;</span></span>](../reporting-services/reports/report-definition-language-ssrs.md)  
  
  
