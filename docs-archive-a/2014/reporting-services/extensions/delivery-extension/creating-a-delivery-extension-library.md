---
title: Criando uma biblioteca de extensões de entrega | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- delivery extensions [Reporting Services], namespace assignments
- library [Reporting Services]
- assigning namespaces to extensions
ms.assetid: 63b32f93-4bab-4b07-bd72-39a47aca1cda
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c9891c2b0c1bb9c7d495b3ab1f8f2267ce04b79f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685431"
---
# <a name="creating-a-delivery-extension-library"></a><span data-ttu-id="829c2-102">Criando uma biblioteca de extensões de entrega</span><span class="sxs-lookup"><span data-stu-id="829c2-102">Creating a Delivery Extension Library</span></span>
  <span data-ttu-id="829c2-103">Cada extensão de entrega do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] que você cria deve ser atribuída a um namespace exclusivo e criada em uma biblioteca ou em um arquivo de assembly.</span><span class="sxs-lookup"><span data-stu-id="829c2-103">Each [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension you create should be assigned to a unique namespace and built into a library or assembly file.</span></span> <span data-ttu-id="829c2-104">O nome exato do namespace não é importante, mas deve ser exclusivo e não deve ser compartilhado com qualquer outra extensão.</span><span class="sxs-lookup"><span data-stu-id="829c2-104">The exact name of the namespace is not important, but it must be unique and not shared with any other extension.</span></span> <span data-ttu-id="829c2-105">Você deve criar seus próprios namespaces exclusivos para as extensões de entrega da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="829c2-105">You should create your own unique namespaces for your company's delivery extensions.</span></span>  
  
 <span data-ttu-id="829c2-106">O exemplo a seguir mostra o código para iniciar uma extensão de entrega do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], que usa os namespaces que contêm as interfaces de entrega e qualquer classe utilitária.</span><span class="sxs-lookup"><span data-stu-id="829c2-106">The following example shows the code to begin a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension, which uses the namespaces that contain the delivery interfaces and any utility classes.</span></span>  
  
```vb  
Imports System  
Imports Microsoft.ReportingServices.Interfaces  
  
Namespace CompanyName.ExtensionName  
   ...  
```  
  
```csharp  
using System;  
using Microsoft.ReportingServices.Interfaces;  
  
namespace CompanyName.ExtensionName  
{  
   ...  
```  
  
 <span data-ttu-id="829c2-107">Durante a compilação de uma extensão de entrega do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], forneça ao compilador uma referência a Microsoft.ReportingServices.Interfaces.dll, já que as interfaces e classes de extensão de entrega estão contidas ali.</span><span class="sxs-lookup"><span data-stu-id="829c2-107">When compiling a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension, you must supply to the compiler a reference to Microsoft.ReportingServices.Interfaces.dll, because the delivery extension interfaces and classes are contained there.</span></span> <span data-ttu-id="829c2-108">O namespace de <xref:Microsoft.ReportingServices.Interfaces> é necessário para a implementação da interface de <xref:Microsoft.ReportingServices.Interfaces.IExtension>, da interface de <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> e mais.</span><span class="sxs-lookup"><span data-stu-id="829c2-108">The <xref:Microsoft.ReportingServices.Interfaces> namespace is needed to implement the <xref:Microsoft.ReportingServices.Interfaces.IExtension> interface, the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> interface, and more.</span></span> <span data-ttu-id="829c2-109">Por exemplo, se todos os arquivos que contêm o código para implementar uma extensão de entrega do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] escrita em C# estiverem em um único diretório com a extensão .cs, o comando a seguir será emitido desse diretório para compilar os arquivos armazenados em CompanyName.ExtensionName.dll.</span><span class="sxs-lookup"><span data-stu-id="829c2-109">For example, if all the files containing the code to implement a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension written in C# were in a single directory with the extension .cs, the following command would be issued from that directory to compile the files stored in CompanyName.ExtensionName.dll.</span></span>  
  
```csharp  
csc /t:library /out:CompanyName.ExtensionName.dll *.cs /r:System.dll   
/r:Microsoft.ReportingServices.Interfaces.dll  
```  
  
 <span data-ttu-id="829c2-110">O exemplo de código a seguir mostra o comando que seria usado para arquivos do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] com a extensão .vb.</span><span class="sxs-lookup"><span data-stu-id="829c2-110">The following code example shows the command that would be used for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] files with the extension .vb.</span></span>  
  
```vb  
vbc /t:library /out:CompanyName.ExtensionName.dll *.vb /r:System.dll   
/r:Microsoft.ReportingServices.Interfaces.dll  
```  
  
> [!NOTE]  
>  <span data-ttu-id="829c2-111">Você também pode criar e desenvolver a sua própria extensão de entrega usando o [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="829c2-111">You can also design, develop, and build your delivery extension using [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="829c2-112">Para obter mais informações sobre como desenvolver assemblies no [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], consulte a documentação do [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="829c2-112">For more information about developing assemblies in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], see your [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="829c2-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="829c2-113">See Also</span></span>  
 <span data-ttu-id="829c2-114">[Extensões do Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="829c2-114">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="829c2-115">[Implementando uma extensão de entrega](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="829c2-115">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="829c2-116">Biblioteca de extensões do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="829c2-116">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
