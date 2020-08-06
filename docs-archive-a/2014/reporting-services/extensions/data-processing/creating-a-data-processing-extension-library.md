---
title: Criando uma biblioteca de extensões de processamento de dados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- data processing extensions [Reporting Services], namespace assignments
- library [Reporting Services]
- assigning namespaces to extensions
ms.assetid: 82f4b71b-dd39-467d-8d8c-6771eb2b12de
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a3c14ed699e94c7d8ed0f6f3d727e9ba6e355b7e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686161"
---
# <a name="creating-a-data-processing-extension-library"></a><span data-ttu-id="62ae6-102">Criando uma biblioteca de extensões de processamento de dados</span><span class="sxs-lookup"><span data-stu-id="62ae6-102">Creating a Data Processing Extension Library</span></span>
  <span data-ttu-id="62ae6-103">Cada extensão de processamento de dados do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] que você cria deve ser atribuída a um namespace exclusivo e criada em uma biblioteca ou em um arquivo de assembly.</span><span class="sxs-lookup"><span data-stu-id="62ae6-103">Each [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension you create should be assigned to a unique namespace and built into a library or assembly file.</span></span> <span data-ttu-id="62ae6-104">O nome exato do namespace não é importante, mas deve ser exclusivo e não deve ser compartilhado com qualquer outra extensão.</span><span class="sxs-lookup"><span data-stu-id="62ae6-104">The exact name of the namespace is not important, but it must be unique and not shared with any other extension.</span></span> <span data-ttu-id="62ae6-105">O [!INCLUDE[msCoName](../../../includes/msconame-md.md)] usa o namespace <xref:Microsoft.ReportingServices.DataProcessing> para as extensões de processamento de dados fornecidas com o [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62ae6-105">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] uses the namespace <xref:Microsoft.ReportingServices.DataProcessing> for the data processing extensions that ship with [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="62ae6-106">Crie os seus próprios namespaces exclusivos para as extensões de processamento de dados de sua empresa.</span><span class="sxs-lookup"><span data-stu-id="62ae6-106">You should create your own unique namespaces for your company's data processing extensions.</span></span>  
  
 <span data-ttu-id="62ae6-107">O exemplo a seguir mostra o código para iniciar uma extensão de processamento de dados do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], que usa os espaços para nome que contêm as interfaces de processamento de dados e qualquer classe utilitária.</span><span class="sxs-lookup"><span data-stu-id="62ae6-107">The following example shows the code to begin a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension, which uses the namespaces that contain the data processing interfaces and any utility classes.</span></span>  
  
```vb  
Imports System  
Imports Microsoft.ReportingServices.DataProcessing  
Imports Microsoft.ReportingServices.Interfaces  
  
Namespace CompanyName.ExtensionName  
   ...  
```  
  
```csharp  
using System;  
using Microsoft.ReportingServices.DataProcessing;  
using Microsoft.ReportingServices.Interfaces;  
  
namespace CompanyName.ExtensionName  
{  
   ...  
```  
  
 <span data-ttu-id="62ae6-108">Durante a compilação de uma extensão de processamento de dados do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], forneça ao compilador uma referência a Microsoft.ReportingServices.Interfaces.dll, já que as interfaces de extensão de processamento de dados estão contidas ali.</span><span class="sxs-lookup"><span data-stu-id="62ae6-108">When compiling a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension, you must supply to the compiler a reference to Microsoft.ReportingServices.Interfaces.dll, because the data processing extension interfaces are contained there.</span></span> <span data-ttu-id="62ae6-109">O namespace <xref:Microsoft.ReportingServices.DataProcessing> é necessário para implementar as interfaces de extensão de processamento de dados e o namespace <xref:Microsoft.ReportingServices.Interfaces> é necessário para implementar a interface <xref:Microsoft.ReportingServices.Interfaces.IExtension>.</span><span class="sxs-lookup"><span data-stu-id="62ae6-109">The <xref:Microsoft.ReportingServices.DataProcessing> namespace is needed to implement the data processing extension interfaces, and the <xref:Microsoft.ReportingServices.Interfaces> namespace is needed to implement the <xref:Microsoft.ReportingServices.Interfaces.IExtension> interface.</span></span> <span data-ttu-id="62ae6-110">Por exemplo, se todos os arquivos com código para implementar uma extensão de processamento de dados do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] escrita em C# estivessem em um único diretório com a extensão .cs, o comando a seguir seria emitido a partir desse diretório para compilar os arquivos armazenados em CompanyName.ExtensionName.dll.</span><span class="sxs-lookup"><span data-stu-id="62ae6-110">For example, if all the files containing the code to implement a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension written in C# were in a single directory with the extension .cs, the following command would be issued from that directory to compile the files stored in CompanyName.ExtensionName.dll.</span></span>  
  
```csharp  
csc /t:library /out:CompanyName.ExtensionName.dll *.cs /r:System.dll /r:Microsoft.ReportingServices.Interfaces.dll  
```  
  
 <span data-ttu-id="62ae6-111">O exemplo de código a seguir mostra o comando que seria usado para arquivos do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] com a extensão .vb.</span><span class="sxs-lookup"><span data-stu-id="62ae6-111">The following code example shows the command that would be used for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] files with the extension .vb.</span></span>  
  
```vb  
vbc /t:library /out:CompanyName.ExtensionName.dll *.vb /r:System.dll /r:Microsoft.ReportingServices.Interfaces.dll  
```  
  
> [!NOTE]  
>  <span data-ttu-id="62ae6-112">Você também pode criar, desenvolver e compilar sua própria extensão de processamento de dados usando o [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62ae6-112">You can also design, develop, and build your data processing extension using [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="62ae6-113">Para obter mais informações sobre como desenvolver assemblies no [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], consulte a documentação do [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62ae6-113">For more information about developing assemblies in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], see your [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62ae6-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="62ae6-114">See Also</span></span>  
 <span data-ttu-id="62ae6-115">[Extensões do Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="62ae6-115">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="62ae6-116">[Implementando uma extensão de processamento de dados](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="62ae6-116">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="62ae6-117">Biblioteca de extensões do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="62ae6-117">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
