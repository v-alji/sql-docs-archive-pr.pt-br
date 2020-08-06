---
title: Formatar um arquivo de script do Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- scripts [Reporting Services], formats
- formats [Reporting Services], script files
ms.assetid: 85a207dd-4e0f-4d40-a41e-0c75f65d719c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c98a2f6561c3242fec34f7ca11c8304286ccebae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680795"
---
# <a name="format-a-reporting-services-script-file"></a><span data-ttu-id="9efc9-102">Formatar um arquivo de script do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="9efc9-102">Format a Reporting Services Script File</span></span>
  <span data-ttu-id="9efc9-103">Um script [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] é um arquivo de código [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET, escrito em um proxy criado em WSDL, que define a API SOAP do Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="9efc9-103">A [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] script is a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET code file, written against a proxy that is built on Web Service Description Language (WSDL), which defines the Reporting Services SOAP API.</span></span> <span data-ttu-id="9efc9-104">Um arquivo de script é armazenado como arquivo de texto Unicode ou UTF-8 com extensão .rss.</span><span class="sxs-lookup"><span data-stu-id="9efc9-104">A script file is stored as a Unicode or UTF-8 text file with the extension .rss.</span></span>  
  
 <span data-ttu-id="9efc9-105">O arquivo de script funciona como um módulo [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] e pode conter procedimentos definidos pelo usuário e variáveis do nível de módulo.</span><span class="sxs-lookup"><span data-stu-id="9efc9-105">The script file acts as a [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] module and can contain user-defined procedures and module-level variables.</span></span> <span data-ttu-id="9efc9-106">Para que o arquivo de script seja executado com êxito, ele deve conter um procedimento Main.</span><span class="sxs-lookup"><span data-stu-id="9efc9-106">For the script file to run successfully, it must contain a Main procedure.</span></span> <span data-ttu-id="9efc9-107">O procedimento Main é o primeiro procedimento acessado quando o seu arquivo de script é executado.</span><span class="sxs-lookup"><span data-stu-id="9efc9-107">The Main procedure is the first procedure that is accessed when your script file runs.</span></span> <span data-ttu-id="9efc9-108">O Main é o local em que você pode acrescentar operações de serviço Web e executar subprocedimentos definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="9efc9-108">Main is where you can add your Web service operations and run your user defined subprocedures.</span></span> <span data-ttu-id="9efc9-109">O código a seguir cria um procedimento Main:</span><span class="sxs-lookup"><span data-stu-id="9efc9-109">The following code creates a Main procedure:</span></span>  
  
```  
Public Sub Main()  
    ' Your code goes here.  
End Sub  
```  
  
 <span data-ttu-id="9efc9-110">O ambiente de script se conecta automaticamente ao servidor de relatório, cria a classe de proxy da Web e gera uma variável de referência (*rs*) para o objeto proxy de serviço Web.</span><span class="sxs-lookup"><span data-stu-id="9efc9-110">The script environment automatically connects to the report server, creates the Web proxy class, and generates a reference variable (*rs*) to the Web service proxy object.</span></span> <span data-ttu-id="9efc9-111">As instruções individuais que você cria precisam apenas fazer referência à variável do nível de módulo *rs* para realizar qualquer operação de serviço Web disponível na biblioteca de serviços Web.</span><span class="sxs-lookup"><span data-stu-id="9efc9-111">Individual statements that you create need only refer to the *rs* module-level variable to perform any of the Web service operations that are available in the Web service library.</span></span> <span data-ttu-id="9efc9-112">O código [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] a seguir chama o método de serviço Web <xref:ReportService2010.ReportingService2010.ListChildren%2A> do arquivo de script:</span><span class="sxs-lookup"><span data-stu-id="9efc9-112">The following [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] code calls the Web service <xref:ReportService2010.ReportingService2010.ListChildren%2A> method from within a script file:</span></span>  
  
```  
Public Sub Main()  
    Dim items() As CatalogItem  
    items = rs.ListChildren("/", True)  
  
    Dim item As CatalogItem  
    For Each item In items  
        Console.WriteLine(item.Name)  
    Next item  
End Sub   
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9efc9-113">As credenciais de usuário são administradas pelo ambiente de script e passadas pelos argumentos de prompt de comando pelo uso do RS.exe.</span><span class="sxs-lookup"><span data-stu-id="9efc9-113">User credentials are managed by the script environment and passed through command prompt arguments through the use of RS.exe.</span></span> <span data-ttu-id="9efc9-114">Embora seja possível usar a variável *rs* para definir a autenticação do serviço Web, é recomendável que você utilize o ambiente de script.</span><span class="sxs-lookup"><span data-stu-id="9efc9-114">Although you can use the *rs* variable to set the authentication of the Web service, it is recommended that you use the script environment.</span></span> <span data-ttu-id="9efc9-115">Não é necessário autenticar o serviço Web no próprio arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="9efc9-115">You do not need to authenticate the Web service in the script file itself.</span></span> <span data-ttu-id="9efc9-116">Para obter mais informações sobre a autenticação do ambiente de script, consulte [Utilitário RS.exe &#40;SSRS&#41;](rs-exe-utility-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="9efc9-116">For more information about authenticating the script environment, see [RS.exe Utility &#40;SSRS&#41;](rs-exe-utility-ssrs.md).</span></span>  
  
 <span data-ttu-id="9efc9-117">Não declare namespaces dentro do arquivo de script.</span><span class="sxs-lookup"><span data-stu-id="9efc9-117">You do not declare namespaces within the script file.</span></span> <span data-ttu-id="9efc9-118">O ambiente de script disponibiliza vários namespaces úteis [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] disponíveis para você: **System.Web.Services**, **System.Web.Services.Protocols**, **System.Xml** e **System.IO**.</span><span class="sxs-lookup"><span data-stu-id="9efc9-118">The scripting environment makes several useful [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] namespaces available to you: **System.Web.Services**, **System.Web.Services.Protocols**, **System.Xml**, and **System.IO**.</span></span>  
  
 <span data-ttu-id="9efc9-119">Para obter exemplos de script, consulte [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="9efc9-119">For script samples, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9efc9-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9efc9-120">See Also</span></span>  
 <span data-ttu-id="9efc9-121">[Serviço Web Servidor de Relatórios](../report-server-web-service/report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="9efc9-121">[Report Server Web Service](../report-server-web-service/report-server-web-service.md) </span></span>  
 <span data-ttu-id="9efc9-122">[Referência técnica &#40;SSRS&#41;](../technical-reference-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9efc9-122">[Technical Reference &#40;SSRS&#41;](../technical-reference-ssrs.md) </span></span>  
 [<span data-ttu-id="9efc9-123">Utilitário RS.exe &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9efc9-123">RS.exe Utility &#40;SSRS&#41;</span></span>](rs-exe-utility-ssrs.md)  
  
  
