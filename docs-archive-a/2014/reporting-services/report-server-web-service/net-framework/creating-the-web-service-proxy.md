---
title: Criando o proxy do serviço Web | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Report Server Web service, proxies
- proxies [Reporting Services]
- XML Web service [Reporting Services], proxies
- Web service [Reporting Services], proxies
- Web references [Reporting Services]
ms.assetid: b1217843-8d3d-49f3-a0d2-d35b0db5b2df
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0d080b96fa29e906c044561a684d58275af9f61e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679685"
---
# <a name="creating-the-web-service-proxy"></a><span data-ttu-id="2d20d-102">Criando o proxy de serviço Web</span><span class="sxs-lookup"><span data-stu-id="2d20d-102">Creating the Web Service Proxy</span></span>
  <span data-ttu-id="2d20d-103">Um cliente e um serviço Web podem se comunicar usando mensagens SOAP que encapsulam os parâmetros de entrada e de saída como XML.</span><span class="sxs-lookup"><span data-stu-id="2d20d-103">A client and a Web service can communicate using SOAP messages, which encapsulate the input and output parameters as XML.</span></span> <span data-ttu-id="2d20d-104">Uma classe de proxy mapeia parâmetros para elementos XML e então envia as mensagens SOAP pela rede.</span><span class="sxs-lookup"><span data-stu-id="2d20d-104">A proxy class maps parameters to XML elements and then sends the SOAP messages over a network.</span></span> <span data-ttu-id="2d20d-105">Dessa forma, a classe proxy libera você de ter de se comunicar com o serviço Web no nível de SOAP e permite que você invoque métodos do serviço Web em qualquer ambiente de desenvolvimento que dê suporte a SOAP e a proxies de serviço Web.</span><span class="sxs-lookup"><span data-stu-id="2d20d-105">In this way, the proxy class frees you from having to communicate with the Web service at the SOAP level and allows you to invoke Web service methods in any development environment that supports SOAP and Web service proxies.</span></span>  
  
 <span data-ttu-id="2d20d-106">Há duas maneiras de adicionar uma classe proxy ao seu projeto de desenvolvimento usando o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] : com a ferramenta WSDL no [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] e adicionando uma referência Web no [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2d20d-106">There are two ways to add a proxy class to your development project using the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]: with the WSDL tool in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], and by adding a Web reference in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="2d20d-107">As seções a seguir discutem este assunto em mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="2d20d-107">The following sections discuss this subject in further detail.</span></span>  
  
## <a name="adding-the-proxy-using-the-wsdl-tool"></a><span data-ttu-id="2d20d-108">Adicionando o proxy usando a ferramenta WSDL</span><span class="sxs-lookup"><span data-stu-id="2d20d-108">Adding the Proxy Using the WSDL Tool</span></span>  
 <span data-ttu-id="2d20d-109">O SDK do [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] inclui a ferramenta Wsdl.exe (Web Services Description Language), que permite a você gerar um proxy de serviço Web para uso em um ambiente de desenvolvimento do [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d20d-109">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK includes the Web Services Description Language tool (Wsdl.exe), which enables you to generate a Web service proxy for use in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] development environment.</span></span> <span data-ttu-id="2d20d-110">A maneira mais comum de criar um proxy de cliente em idiomas que dão suporte aos serviços Web (atualmente C# e [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] ) é usar a ferramenta WSDL.</span><span class="sxs-lookup"><span data-stu-id="2d20d-110">The most common way to create a client proxy in languages that support Web services (currently C# and [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) is to use the WSDL tool.</span></span>  
  
 <span data-ttu-id="2d20d-111">**Para adicionar uma classe proxy ao projeto usando Wsdl.exe**</span><span class="sxs-lookup"><span data-stu-id="2d20d-111">**To add a proxy class to your project using Wsdl.exe**</span></span>  
  
1.  <span data-ttu-id="2d20d-112">Em um prompt de comando, use Wsdl.exe para criar uma classe proxy, especificando (no mínimo) a URL do serviço Web Servidor de Relatório.</span><span class="sxs-lookup"><span data-stu-id="2d20d-112">From a command prompt, use Wsdl.exe to create a proxy class, specifying (at a minimum) the URL to the Report Server Web service.</span></span>  
  
     <span data-ttu-id="2d20d-113">Por exemplo, a instrução de prompt de comando a seguir especifica uma URL para o ponto de extremidade de gerenciamento do serviço Web Servidor de Relatório:</span><span class="sxs-lookup"><span data-stu-id="2d20d-113">For example, the following command prompt statement specifies a URL for the management endpoint of the Report Server Web service:</span></span>  
  
    ```  
    wsdl /language:CS /n:"Microsoft.SqlServer.ReportingServices2010" http://<Server Name>/reportserver/reportservice2010.asmx?wsdl  
    ```  
  
     <span data-ttu-id="2d20d-114">A ferramenta WSDL aceita vários argumentos de prompt de comando para gerar um proxy.</span><span class="sxs-lookup"><span data-stu-id="2d20d-114">The WSDL tool accepts a number of command-prompt arguments for generating a proxy.</span></span> <span data-ttu-id="2d20d-115">O exemplo anterior especifica a linguagem C#, um namespace sugerido para ser usado no proxy (para impedir a colisão de nomes se você estiver usando mais de um ponto de extremidade de serviço Web) e gera um arquivo C# chamado ReportingService2010.cs.</span><span class="sxs-lookup"><span data-stu-id="2d20d-115">The preceding example specifies the language C#, a suggested namespace to use in the proxy (to prevent name collision if using more than one Web service endpoint), and generates a C# file called ReportingService2010.cs.</span></span> <span data-ttu-id="2d20d-116">Se o exemplo tivesse especificado [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)], teria gerado um arquivo de proxy com o nome ReportingService2010.vb.</span><span class="sxs-lookup"><span data-stu-id="2d20d-116">If the example had specified [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)], the example would have generated a proxy file with the name ReportingService2010.vb.</span></span> <span data-ttu-id="2d20d-117">Esse arquivo é criado no diretório a partir do qual você executou o comando.</span><span class="sxs-lookup"><span data-stu-id="2d20d-117">This file is created in the directory from which you run the command.</span></span>  
  
2.  <span data-ttu-id="2d20d-118">Compile a classe proxy em um arquivo de assembly (com a extensão .dll) e faça referência a ele em seu projeto, ou adicione a classe como um item de projeto.</span><span class="sxs-lookup"><span data-stu-id="2d20d-118">Compile the proxy class into an assembly file (with the extension .dll) and reference it in your project, or add the class as a project item.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2d20d-119">Quando você adicionar uma classe proxy manualmente ao seu projeto, terá de acrescentar uma referência a System.Web.Services.dll.</span><span class="sxs-lookup"><span data-stu-id="2d20d-119">When you add a proxy class to your project manually, you need to add a reference to System.Web.Services.dll.</span></span> <span data-ttu-id="2d20d-120">Se você adicionar o proxy usando uma referência da Web em Visual Studio .NET, a referência será criada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2d20d-120">If you add the proxy using a Web reference in Visual Studio .NET, the reference is automatically created for you.</span></span> <span data-ttu-id="2d20d-121">Para obter mais informações, consulte "Adicionando o proxy usando uma referência da Web no Visual Studio" mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="2d20d-121">For more information, see "Adding the Proxy Using a Web Reference in Visual Studio" later in this topic.</span></span>  
  
     <span data-ttu-id="2d20d-122">Depois de adicionar a classe proxy como um item ao seu projeto, o arquivo associado será exibido no Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="2d20d-122">After you add the proxy class as an item to your project, the associated file appears in Solution Explorer.</span></span>  
  
3.  <span data-ttu-id="2d20d-123">Para chamar o serviço programaticamente, crie uma instância da classe proxy.</span><span class="sxs-lookup"><span data-stu-id="2d20d-123">To call the service programmatically, create an instance of the proxy class.</span></span>  
  
     <span data-ttu-id="2d20d-124">O exemplo de código a seguir mostra a sintaxe para a criação de uma instância da classe proxy <xref:ReportService2010.ReportingService2010> em um projeto:</span><span class="sxs-lookup"><span data-stu-id="2d20d-124">The following code example shows the syntax for creating an instance of the <xref:ReportService2010.ReportingService2010> proxy class in a project:</span></span>  
  
```vb  
Dim service As New ReportingService2010()  
```  
  
```csharp  
ReportingService2010 service = new ReportingService2010();  
  
```  
  
 <span data-ttu-id="2d20d-125">Para obter mais informações sobre a ferramenta Wsdl.exe, incluindo a sua sintaxe completa, consulte "Ferramenta Web Services Description Language" na documentação do SDK do [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d20d-125">For more information about the Wsdl.exe tool, including its full syntax, see "Web Services Description Language Tool" in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK documentation.</span></span> <span data-ttu-id="2d20d-126">Para obter uma explicação completa sobre proxies de serviço Web, consulte "Criando um proxy de serviço Web XML" na documentação do SDK do [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d20d-126">For a full explanation of Web service proxies, see "Creating an XML Web Service Proxy" in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
## <a name="adding-the-proxy-using-a-web-reference-in-visual-studio"></a><span data-ttu-id="2d20d-127">Adicionando o proxy usando uma referência da Web no Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2d20d-127">Adding the Proxy Using a Web Reference in Visual Studio</span></span>  
 <span data-ttu-id="2d20d-128">Uma referência Web permite que um projeto consuma um ou mais serviços Web.</span><span class="sxs-lookup"><span data-stu-id="2d20d-128">A Web reference enables a project to consume one or more Web services.</span></span> <span data-ttu-id="2d20d-129">O [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] permite que os usuários adicionem referências de serviço Web a projetos seguindo algumas etapas simples.</span><span class="sxs-lookup"><span data-stu-id="2d20d-129">[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] enables users to add Web service references to projects by following a few simple steps.</span></span>  
  
 <span data-ttu-id="2d20d-130">**Para adicionar uma referência Web a um projeto**</span><span class="sxs-lookup"><span data-stu-id="2d20d-130">**To add a Web reference to a project**</span></span>  
  
1.  <span data-ttu-id="2d20d-131">No **Gerenciador de Soluções**, selecione o projeto que consumirá o serviço Web.</span><span class="sxs-lookup"><span data-stu-id="2d20d-131">In **Solution Explorer**, select the project that will consume the Web service.</span></span>  
  
2.  <span data-ttu-id="2d20d-132">No menu **Projeto**, clique em **Adicionar Referência Web**.</span><span class="sxs-lookup"><span data-stu-id="2d20d-132">On the **Project** menu, click **Add Web Reference**.</span></span>  
  
     <span data-ttu-id="2d20d-133">A caixa de diálogo **Adicionar Referência Web** será aberta.</span><span class="sxs-lookup"><span data-stu-id="2d20d-133">The **Add Web Reference** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="2d20d-134">No campo **URL**, insira o caminho completo para o serviço Web Servidor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="2d20d-134">In the **URL** field, enter the complete path to the Report Server Web service.</span></span>  
  
     <span data-ttu-id="2d20d-135">Uma URL simplificada para o ponto de extremidade de execução de relatório do serviço Web Servidor de Relatório poderia ser assim:</span><span class="sxs-lookup"><span data-stu-id="2d20d-135">A simplified URL for the report execution endpoint of the Report Server Web service might look like this:</span></span>  
  
    ```  
    http://<Server Name>/reportserver/reportexecution2005.asmx  
    ```  
  
     <span data-ttu-id="2d20d-136">A URL contém o domínio no qual o serviço Web Servidor de Relatório foi implantado, o nome da pasta que contém o serviço e o nome do arquivo de descoberta para o serviço.</span><span class="sxs-lookup"><span data-stu-id="2d20d-136">The URL contains the domain in which the Report Server Web service is deployed, the name of the folder containing the service, and the name of the discovery file for the service.</span></span> <span data-ttu-id="2d20d-137">Para obter uma descrição completa dos diferentes elementos de URL, consulte [Acessando a API SOAP](../accessing-the-soap-api.md).</span><span class="sxs-lookup"><span data-stu-id="2d20d-137">For a complete description of the different URL elements, see [Accessing the SOAP API](../accessing-the-soap-api.md).</span></span>  
  
     <span data-ttu-id="2d20d-138">Uma descrição dos métodos e das propriedades fornecidos pelo serviço Web é exibida no painel Navegador à esquerda.</span><span class="sxs-lookup"><span data-stu-id="2d20d-138">A description of the methods and properties provided by the Web service appears in the Browser pane on the left.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2d20d-139">Para obter mais informações sobre os itens associados ao serviço Web Servidor de Relatórios, consulte [Métodos do serviço Web Servidor de Relatórios](../methods/report-server-web-service-methods.md).</span><span class="sxs-lookup"><span data-stu-id="2d20d-139">For more information about the items associated with the Report Server Web service, see [Report Server Web Service Methods](../methods/report-server-web-service-methods.md).</span></span>  
  
4.  <span data-ttu-id="2d20d-140">Verifique se o seu projeto pode usar o serviço Web Servidor de Relatório e se você tem a permissão apropriada para acessar o servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="2d20d-140">Verify that your project can use the Report Server Web service, and that you have appropriate permission to access the report server.</span></span>  
  
5.  <span data-ttu-id="2d20d-141">No campo **Nome da referência Web**, insira um nome que você usará no código para acessar o serviço Web Servidor de Relatórios de forma programática.</span><span class="sxs-lookup"><span data-stu-id="2d20d-141">In the **Web reference name** field, enter a name that you will use in your code to access the Report Server Web service programmatically.</span></span>  
  
6.  <span data-ttu-id="2d20d-142">Selecione o botão **Adicionar Referência** para criar uma referência no aplicativo ao serviço Web.</span><span class="sxs-lookup"><span data-stu-id="2d20d-142">Select the **Add Reference** button to create a reference in your application to the Web service.</span></span>  
  
     <span data-ttu-id="2d20d-143">A nova referência será exibida no **Gerenciador de Soluções**, sob o nó Referências Web do projeto ativo, nomeada como especificado no campo **Nome da referência Web**.</span><span class="sxs-lookup"><span data-stu-id="2d20d-143">The new reference appears in **Solution Explorer** under the Web References node for the active project, named as specified in the **Web reference name** field.</span></span>  
  
7.  <span data-ttu-id="2d20d-144">No **Gerenciador de Soluções**, expanda a pasta Referências Web para observar o namespace das classes de referência Web disponíveis para os itens do projeto.</span><span class="sxs-lookup"><span data-stu-id="2d20d-144">In **Solution Explorer**, expand the Web References folder to note the namespace for the Web reference classes that are available to the items in your project.</span></span>  
  
     <span data-ttu-id="2d20d-145">Depois de adicionar uma referência Web ao projeto, os arquivos associados serão exibidos em uma pasta dentro da pasta Referências Web do **Gerenciador de Soluções**.</span><span class="sxs-lookup"><span data-stu-id="2d20d-145">After adding a Web reference to your project, the associated files are displayed in a folder within the Web References folder of **Solution Explorer**.</span></span>  
  
 <span data-ttu-id="2d20d-146">Depois de adicionar a referência da Web, use a sintaxe a seguir para criar uma instância da classe proxy:</span><span class="sxs-lookup"><span data-stu-id="2d20d-146">After you add the Web reference, use the following syntax to create an instance of the proxy class:</span></span>  
  
```vb  
Dim rs As New myNamespace.myReferenceName.ReportExecutionService()  
rs.Url = "http://<Server Name>/reportserver/reportexecution2005.asmx?wsdl"  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
```  
  
```csharp  
myNamespace.myReferenceName.ReportExecutionService rs = new myNamespace.myReferenceName.ReportExecutionService();  
rs.Url = "http://<Server Name>/reportserver/reportexecution2005.asmx?wsdl"  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
  
```  
  
 <span data-ttu-id="2d20d-147">Você também pode adicionar uma diretiva **using** (**Import** no [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) à referência de serviço Web Servidor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="2d20d-147">You can also add a **using** (**Import** in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) directive to the Report Server Web service reference.</span></span> <span data-ttu-id="2d20d-148">Se você usar essa política, não precisará qualificar os tipos completamente no namespace.</span><span class="sxs-lookup"><span data-stu-id="2d20d-148">If you use this directive, you do not need to fully qualify the types in the namespace.</span></span> <span data-ttu-id="2d20d-149">Para fazer isso, adicione o código a seguir ao seu arquivo:</span><span class="sxs-lookup"><span data-stu-id="2d20d-149">To do this, add the following code to your file:</span></span>  
  
```vb  
Import myNamespace.myReferenceName  
```  
  
```csharp  
using myNamespace.myReferenceName;  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d20d-150">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2d20d-150">See Also</span></span>  
 <span data-ttu-id="2d20d-151">[Serviço Web Servidor de Relatórios](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="2d20d-151">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="2d20d-152">[Criando aplicativos usando o serviço Web e o .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="2d20d-152">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="2d20d-153">Referência técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2d20d-153">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
