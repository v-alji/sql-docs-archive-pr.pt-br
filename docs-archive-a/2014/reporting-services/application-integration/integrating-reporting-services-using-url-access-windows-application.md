---
title: Usando o acesso à URL em um aplicativo do Windows | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Windows applications [Reporting Services]
- Web Browser controls [Reporting Services]
- Windows Forms [Reporting Services]
- browser controls [Reporting Services]
- URL access [Reporting Services], Windows applications
ms.assetid: a4b222e5-0cbd-409c-92c4-046a674db8ac
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8f8b901481b1d6fcc3cdd8626b43cd3a69174c1a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682180"
---
# <a name="using-url-access-in-a-windows-application"></a><span data-ttu-id="ad2b7-102">Usando acesso à URL em um aplicativo do Windows</span><span class="sxs-lookup"><span data-stu-id="ad2b7-102">Using URL Access in a Windows Application</span></span>
  <span data-ttu-id="ad2b7-103">Embora o acesso à URL a um servidor de relatório seja otimizado para um ambiente da Web, você também pode usá-lo para inserir relatórios do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] em um aplicativo do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="ad2b7-103">Although URL access to a report server is optimized for a Web environment, you can also use URL access to embed [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] reports into a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application.</span></span> <span data-ttu-id="ad2b7-104">No entanto, o acesso à URL que envolve o Windows Forms ainda exige que você use tecnologia de navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="ad2b7-104">However, URL access that involves Windows Forms still requires that you use Web browser technology.</span></span> <span data-ttu-id="ad2b7-105">Você pode usar os seguintes cenários de integração com o acesso à URL e o Windows Forms:</span><span class="sxs-lookup"><span data-stu-id="ad2b7-105">You can use the following integration scenarios with URL access and Windows Forms:</span></span>  
  
-   <span data-ttu-id="ad2b7-106">Exiba um relatório de um aplicativo Windows Form iniciando um navegador da Web programaticamente.</span><span class="sxs-lookup"><span data-stu-id="ad2b7-106">Display a report from a Windows Form application by starting a Web browser programmatically.</span></span>  
  
-   <span data-ttu-id="ad2b7-107">Use o controle <xref:System.Windows.Forms.WebBrowser> em um Windows Form para exibir um relatório.</span><span class="sxs-lookup"><span data-stu-id="ad2b7-107">Use the <xref:System.Windows.Forms.WebBrowser> control on a Windows Form to display a report.</span></span>  
  
## <a name="starting-internet-explorer-from-a-windows-form"></a><span data-ttu-id="ad2b7-108">Iniciando o Internet Explorer a partir de um Windows Form</span><span class="sxs-lookup"><span data-stu-id="ad2b7-108">Starting Internet Explorer from a Windows Form</span></span>  
 <span data-ttu-id="ad2b7-109">Você pode usar a classe <xref:System.Diagnostics.Process> para acessar um processo que esteja em execução em um computador.</span><span class="sxs-lookup"><span data-stu-id="ad2b7-109">You can use the <xref:System.Diagnostics.Process> class to access a process that is running on a computer.</span></span> <span data-ttu-id="ad2b7-110">A <xref:System.Diagnostics.Process> classe é uma [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] construção útil para iniciar, interromper, controlar e monitorar aplicativos.</span><span class="sxs-lookup"><span data-stu-id="ad2b7-110">The <xref:System.Diagnostics.Process> class is a useful [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] construct for starting, stopping, controlling, and monitoring applications.</span></span> <span data-ttu-id="ad2b7-111">Para exibir um relatório específico no banco de dados do servidor de relatório, inicie o processo **IExplore**, passando a URL para o relatório.</span><span class="sxs-lookup"><span data-stu-id="ad2b7-111">To view a specific report in your report server database, you can start the **IExplore** process, passing in the URL to the report.</span></span> <span data-ttu-id="ad2b7-112">O exemplo de código a seguir pode ser usado para iniciar o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer e para passar uma URL específica do relatório quando o usuário clicar em um botão de um Windows Form.</span><span class="sxs-lookup"><span data-stu-id="ad2b7-112">The following code example can be used to start [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer and pass a specific report URL when the user clicks a button on a Windows Form.</span></span>  
  
```vb  
Private Sub viewReportButton_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles viewReportButton.Click  
   ' Build the URL access string based on values supplied by a user  
   Dim url As String = serverUrlTextBox.Text + "?" & reportPathTextBox.Text & _  
   "&rs:Command=Render" & "&rs:Format=HTML4.0"  
  
   ' If the user does not select the toolbar check box,  
   ' turn the toolbar off in the HTML Viewer  
   If toolbarCheckBox.Checked = False Then  
      url += "&rc:Toolbar=False"  
   End If  
   ' load report in the Web browser  
   Try  
      System.Diagnostics.Process.Start("IExplore", url)  
   Catch  
      MessageBox.Show("The system could not start the specified report using Internet Explorer.", _  
      "An error has occurred", MessageBoxButtons.OK, MessageBoxIcon.Error)  
   End Try  
End Sub 'viewReportButton_Click  
```  
  
```csharp  
// Sample click event for a Button control on a Windows Form  
private void viewReportButton_Click(object sender, System.EventArgs e)  
{  
   // Build the URL access string based on values supplied by a user  
   string url = serverUrlTextBox.Text + "?" + reportPathTextBox.Text +  
      "&rs:Command=Render" + "&rs:Format=HTML4.0";  
  
   // If the user does not check the toolbar check box,  
   // turn the toolbar off in the HTML Viewer  
   if (toolbarCheckBox.Checked == false)  
      url += "&rc:Toolbar=False";  
  
   // load report in the Web browser  
   try  
   {  
      System.Diagnostics.Process.Start("IExplore", url);  
   }  
  
   catch (Exception)  
   {  
      MessageBox.Show(  
         "The system could not open the specified report using Internet Explorer.",   
         "An error has occurred", MessageBoxButtons.OK, MessageBoxIcon.Error);  
   }  
}  
```  
  
## <a name="embedding-a-browser-control-on-a-windows-form"></a><span data-ttu-id="ad2b7-113">Inserindo um controle de navegador em um Windows Form</span><span class="sxs-lookup"><span data-stu-id="ad2b7-113">Embedding a Browser Control on a Windows Form</span></span>  
 <span data-ttu-id="ad2b7-114">Se você não quiser exibir o seu relatório em um navegador da Web externo, poderá inserir um navegador da Web de forma direta, como parte do seu Windows Form, usando o controle <xref:System.Windows.Forms.WebBrowser>.</span><span class="sxs-lookup"><span data-stu-id="ad2b7-114">If you do not want to view your report in an external Web browser, you can embed a Web browser seamlessly as part of your Windows Form using the <xref:System.Windows.Forms.WebBrowser> control.</span></span>  
  
###### <a name="to-add-the-webbrowser-control-to-your-windows-form"></a><span data-ttu-id="ad2b7-115">Para adicionar o controle WebBrowser ao seu Windows Form</span><span class="sxs-lookup"><span data-stu-id="ad2b7-115">To add the WebBrowser control to your Windows Form</span></span>  
  
1.  <span data-ttu-id="ad2b7-116">Crie um novo aplicativo do Windows no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../includes/csprcs-md.md)] ou no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ad2b7-116">Create a new Windows application in either [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../includes/csprcs-md.md)] or [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span></span>  
  
2.  <span data-ttu-id="ad2b7-117">Localize o controle <xref:System.Windows.Forms.WebBrowser> na caixa de diálogo **Caixa de Ferramentas**.</span><span class="sxs-lookup"><span data-stu-id="ad2b7-117">Locate the <xref:System.Windows.Forms.WebBrowser> control in the **Toolbox** Dialog Box.</span></span>  
  
     <span data-ttu-id="ad2b7-118">Se a **Caixa de Ferramentas** não estiver visível, acesse-a clicando no item de menu **Exibir** e selecionando **Caixa de Ferramentas**.</span><span class="sxs-lookup"><span data-stu-id="ad2b7-118">If the **Toolbox** is not visible you can access it by clicking the **View** menu item and selecting **Toolbox**.</span></span>  
  
3.  <span data-ttu-id="ad2b7-119">Arraste o controle <xref:System.Windows.Forms.WebBrowser> para a superfície de design do Windows Form.</span><span class="sxs-lookup"><span data-stu-id="ad2b7-119">Drag the <xref:System.Windows.Forms.WebBrowser>control onto the design surface of your Windows Form.</span></span>  
  
     <span data-ttu-id="ad2b7-120">O controle <xref:System.Windows.Forms.WebBrowser> chamado webBrowser1 será adicionado ao Form</span><span class="sxs-lookup"><span data-stu-id="ad2b7-120">The <xref:System.Windows.Forms.WebBrowser>control named webBrowser1 is added to the Form</span></span>  
  
 <span data-ttu-id="ad2b7-121">Direcione o controle <xref:System.Windows.Forms.WebBrowser> para uma URL chamando seu método **Navigate**.</span><span class="sxs-lookup"><span data-stu-id="ad2b7-121">You direct the <xref:System.Windows.Forms.WebBrowser> control to a URL by calling its **Navigate** method.</span></span> <span data-ttu-id="ad2b7-122">Você pode atribuir uma cadeia de caracteres de acesso à URL específica ao seu controle <xref:System.Windows.Forms.WebBrowser> em tempo de execução como mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="ad2b7-122">You can assign a specific URL access string to your <xref:System.Windows.Forms.WebBrowser> control at run time as shown in the following example.</span></span>  
  
```vb  
Dim url As String = "http://localhost/reportserver?/" & _  
                    "AdventureWorks2012 Sample Reports/" & _  
                    "Company Sales&rs:Command=Render"  
WebBrowser1.Navigate(url)  
```  
  
```csharp  
string url = "http://localhost/reportserver?/" +  
             "AdventureWorks2012 Sample Reports/" +  
             "Company Sales&rs:Command=Render";  
webBrowser1.Navigate(url);  
```  
  
## <a name="see-also"></a><span data-ttu-id="ad2b7-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ad2b7-123">See Also</span></span>  
 <span data-ttu-id="ad2b7-124">[Integrando Reporting Services em aplicativos](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="ad2b7-124">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 <span data-ttu-id="ad2b7-125">[Integrando Reporting Services usando o acesso à URL](integrating-reporting-services-using-url-access.md) </span><span class="sxs-lookup"><span data-stu-id="ad2b7-125">[Integrating Reporting Services Using URL Access](integrating-reporting-services-using-url-access.md) </span></span>  
 <span data-ttu-id="ad2b7-126">[Integrando Reporting Services usando SOAP](integrating-reporting-services-using-soap.md) </span><span class="sxs-lookup"><span data-stu-id="ad2b7-126">[Integrating Reporting Services Using SOAP](integrating-reporting-services-using-soap.md) </span></span>  
 <span data-ttu-id="ad2b7-127">[Integrando Reporting Services usando os controles ReportViewer](integrating-reporting-services-using-reportviewer-controls.md) </span><span class="sxs-lookup"><span data-stu-id="ad2b7-127">[Integrating Reporting Services Using the ReportViewer Controls](integrating-reporting-services-using-reportviewer-controls.md) </span></span>  
 [<span data-ttu-id="ad2b7-128">Acesso à URL &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ad2b7-128">URL Access &#40;SSRS&#41;</span></span>](../url-access-ssrs.md)  
  
  
