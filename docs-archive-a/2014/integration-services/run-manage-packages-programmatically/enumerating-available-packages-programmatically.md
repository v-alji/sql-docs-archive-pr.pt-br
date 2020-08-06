---
title: Enumerar pacotes disponíveis programaticamente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- programmatically enumerate packages [SSIS]
- existence testing [Integration Services]
- enumerating packages [Integration Services]
ms.assetid: 254ec7ee-d3ff-4361-8995-46e9b9c4dc95
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 053f2e598b1cc18e68ee2182092188367ee7f10c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679394"
---
# <a name="enumerating-available-packages-programmatically"></a><span data-ttu-id="be605-102">Enumerando pacotes disponíveis programaticamente</span><span class="sxs-lookup"><span data-stu-id="be605-102">Enumerating Available Packages Programmatically</span></span>
  <span data-ttu-id="be605-103">Ao trabalhar programaticamente com pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , talvez você queira determinar se existe um pacote ou pasta individual, ou enumerar os pacotes salvos que estão disponíveis para carregamento e execução.</span><span class="sxs-lookup"><span data-stu-id="be605-103">As you work programmatically with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, you may want to determine whether an individual package or folder exists, or to enumerate the saved packages that are available to load and execute.</span></span> <span data-ttu-id="be605-104">A classe <xref:Microsoft.SqlServer.Dts.Runtime.Application> do namespace <xref:Microsoft.SqlServer.Dts.Runtime> fornece diversos métodos para atender a esses requisitos.</span><span class="sxs-lookup"><span data-stu-id="be605-104">The <xref:Microsoft.SqlServer.Dts.Runtime.Application> class of the <xref:Microsoft.SqlServer.Dts.Runtime> namespace provides a variety of methods to satisfy these requirements.</span></span>  
  
##  <a name="determining-whether-a-package-or-folder-exists"></a><a name="exists"></a> <span data-ttu-id="be605-105">Determinando se existe um pacote ou pasta</span><span class="sxs-lookup"><span data-stu-id="be605-105">Determining Whether a Package or Folder Exists</span></span>  
 <span data-ttu-id="be605-106">Para determinar programaticamente se existe um pacote salvo, chame um dos métodos a seguir antes de tentar carregá-lo e executá-lo:</span><span class="sxs-lookup"><span data-stu-id="be605-106">To determine programmatically whether a saved package exists, call one of the following methods before attempting to load and run it:</span></span>  
  
|<span data-ttu-id="be605-107">Local de armazenamento</span><span class="sxs-lookup"><span data-stu-id="be605-107">Storage Location</span></span>|<span data-ttu-id="be605-108">Método de chamada</span><span class="sxs-lookup"><span data-stu-id="be605-108">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="be605-109">Armazenamento de Pacotes SSIS</span><span class="sxs-lookup"><span data-stu-id="be605-109">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.ExistsOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.ExistsOnSqlServer%2A>|  
  
 <span data-ttu-id="be605-110">Para determinar programaticamente se existe uma pasta antes de tentar listar os pacotes armazenados nela, chame um dos métodos a seguir:</span><span class="sxs-lookup"><span data-stu-id="be605-110">To determine programmatically whether a folder exists before attempting to list the packages stored in it, call one of the following methods:</span></span>  
  
|<span data-ttu-id="be605-111">Local de armazenamento</span><span class="sxs-lookup"><span data-stu-id="be605-111">Storage Location</span></span>|<span data-ttu-id="be605-112">Método de chamada</span><span class="sxs-lookup"><span data-stu-id="be605-112">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="be605-113">Armazenamento de Pacotes SSIS</span><span class="sxs-lookup"><span data-stu-id="be605-113">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.FolderExistsOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.FolderExistsOnSqlServer%2A>|  
  
 [<span data-ttu-id="be605-114">Voltar ao início</span><span class="sxs-lookup"><span data-stu-id="be605-114">Back to top</span></span>](#top)  
  
##  <a name="enumerating-available-packages"></a><a name="listing"></a> <span data-ttu-id="be605-115">Enumerando pacotes disponíveis</span><span class="sxs-lookup"><span data-stu-id="be605-115">Enumerating Available Packages</span></span>  
 <span data-ttu-id="be605-116">Para obter uma lista de pacotes salvos programaticamente, chame um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="be605-116">To obtain a list of saved packages programmatically, call one of the following methods:</span></span>  
  
|<span data-ttu-id="be605-117">Local de armazenamento</span><span class="sxs-lookup"><span data-stu-id="be605-117">Storage Location</span></span>|<span data-ttu-id="be605-118">Método de chamada</span><span class="sxs-lookup"><span data-stu-id="be605-118">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="be605-119">Armazenamento de Pacotes SSIS</span><span class="sxs-lookup"><span data-stu-id="be605-119">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.GetDtsServerPackageInfos%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.GetPackageInfos%2A>|  
  
 <span data-ttu-id="be605-120">Os exemplos a seguir são aplicativos de console que demonstram o uso desses métodos.</span><span class="sxs-lookup"><span data-stu-id="be605-120">The following samples are console applications that demonstrate the use of these methods.</span></span>  
  
###  <a name="example-ssis-package-store"></a><a name="listing_store"></a> <span data-ttu-id="be605-121">Exemplo (Repositório de Pacotes do SSIS)</span><span class="sxs-lookup"><span data-stu-id="be605-121">Example (SSIS Package Store)</span></span>  
 <span data-ttu-id="be605-122">Use o método <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetDtsServerPackageInfos%2A> para listar pacotes armazenados no Armazenamento de Pacotes do SSIS.</span><span class="sxs-lookup"><span data-stu-id="be605-122">Use the <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetDtsServerPackageInfos%2A> method to list packages stored in the SSIS Package Store.</span></span> <span data-ttu-id="be605-123">Os locais de armazenamento padrão gerenciados pelo Repositório de Pacotes do SSIS são Sistema de Arquivos e MSDB.</span><span class="sxs-lookup"><span data-stu-id="be605-123">The default storage locations that are managed by the SSIS Package store are File System and MSDB.</span></span> <span data-ttu-id="be605-124">Você pode criar pastas lógicas adicionais dentro desses locais.</span><span class="sxs-lookup"><span data-stu-id="be605-124">You can create additional logical folders within these locations.</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim sqlFolder As String  
    Dim sqlServer As String  
  
    Dim ssisApplication As Application  
    Dim sqlPackages As PackageInfos  
    Dim sqlPackage As PackageInfo  
  
    sqlServer = "."  
  
    ssisApplication = New Application()  
  
    ' Get packages stored in MSDB.  
    sqlFolder = "MSDB"  
    sqlPackages = ssisApplication.GetDtsServerPackageInfos(sqlFolder, sqlServer)  
    If sqlPackages.Count > 0 Then  
      Console.WriteLine("Packages stored in MSDB:")  
      For Each sqlPackage In sqlPackages  
        Console.WriteLine(sqlPackage.Name)  
      Next  
      Console.WriteLine()  
    End If  
  
    ' Get packages stored in the File System.  
    sqlFolder = "File System"  
    sqlPackages = ssisApplication.GetDtsServerPackageInfos(sqlFolder, sqlServer)  
    If sqlPackages.Count > 0 Then  
      Console.WriteLine("Packages stored in the File System:")  
      For Each sqlPackage In sqlPackages  
        Console.WriteLine(sqlPackage.Name)  
      Next  
    End If  
  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace EnumeratePackagesSSIS_CS  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
  
      string sqlFolder;  
      string sqlServer;  
  
      Application ssisApplication;  
      PackageInfos sqlPackages;  
  
      sqlServer = ".";  
  
      ssisApplication = new Application();  
  
      // Get packages stored in MSDB.  
      sqlFolder = "MSDB";  
      sqlPackages = ssisApplication.GetDtsServerPackageInfos(sqlFolder, sqlServer);  
      if (sqlPackages.Count > 0)  
      {  
        Console.WriteLine("Packages stored in MSDB:");  
        foreach (PackageInfo sqlPackage in sqlPackages)  
        {  
          Console.WriteLine(sqlPackage.Name);  
        }  
        Console.WriteLine();  
      }  
  
      // Get packages stored in the File System.  
      sqlFolder = "File System";  
      sqlPackages = ssisApplication.GetDtsServerPackageInfos(sqlFolder, sqlServer);  
      if (sqlPackages.Count > 0)  
      {  
        Console.WriteLine("Packages stored in the File System:");  
        foreach (PackageInfo sqlPackage in sqlPackages)  
        {  
          Console.WriteLine(sqlPackage.Name);  
        }  
      }  
  
      Console.Read();  
  
    }  
  
  }  
  
}  
```  
  
 [<span data-ttu-id="be605-125">Voltar ao início</span><span class="sxs-lookup"><span data-stu-id="be605-125">Back to top</span></span>](#top)  
  
###  <a name="example-sql-server"></a><a name="listing_sql"></a> <span data-ttu-id="be605-126">Exemplo (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="be605-126">Example (SQL Server)</span></span>  
 <span data-ttu-id="be605-127">Use o método <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetPackageInfos%2A> para listar pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que estão armazenados em uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="be605-127">Use the <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetPackageInfos%2A> method to list [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages that are stored in an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim sqlFolder As String  
    Dim sqlServer As String  
    Dim sqlUser As String  
    Dim sqlPassword As String  
  
    Dim ssisApplication As Application  
    Dim sqlPackages As PackageInfos  
    Dim sqlPackage As PackageInfo  
  
    sqlFolder = String.Empty  
    sqlServer = "(local)"  
    sqlUser = String.Empty  
    sqlPassword = String.Empty  
  
    ssisApplication = New Application()  
  
    sqlPackages = ssisApplication.GetPackageInfos(sqlFolder, sqlServer, sqlUser, sqlPassword)  
  
    For Each sqlPackage In sqlPackages  
      Console.WriteLine(sqlPackage.Name)  
    Next  
  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace EnumeratePackagesSql_CS  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
  
      string sqlFolder;  
      string sqlServer;  
      string sqlUser;  
      string sqlPassword;  
  
      Application ssisApplication;  
      PackageInfos sqlPackages;  
  
      sqlFolder = String.Empty;  
      sqlServer = "(local)";  
      sqlUser = String.Empty;  
      sqlPassword = String.Empty;  
  
      ssisApplication = new Application();  
  
      sqlPackages = ssisApplication.GetPackageInfos(sqlFolder, sqlServer, sqlUser, sqlPassword);  
  
      foreach (PackageInfo sqlPackage in sqlPackages)  
      {  
        Console.WriteLine(sqlPackage.Name);  
      }  
  
      Console.Read();  
  
    }  
  }  
}  
```  
  
 [<span data-ttu-id="be605-128">Voltar ao início</span><span class="sxs-lookup"><span data-stu-id="be605-128">Back to top</span></span>](#top)  
  
<span data-ttu-id="be605-129">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="be605-129">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="be605-130">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="be605-130">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="be605-131">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="be605-131">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="be605-132">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="be605-132">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be605-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="be605-133">See Also</span></span>  
 [<span data-ttu-id="be605-134">Gerenciamento de pacotes &#40;Serviço SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="be605-134">Package Management &#40;SSIS Service&#41;</span></span>](../service/package-management-ssis-service.md)  
  
  
