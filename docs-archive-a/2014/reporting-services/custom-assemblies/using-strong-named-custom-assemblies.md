---
title: Usando assemblies de nome forte personalizados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- AllowPartiallyTrustedCallersAttribute attribute
- strong-named custom assemblies [Reporting Services]
- strong names [Reporting Services]
- assemblies [Reporting Services], strong names
- custom assemblies [Reporting Services], strong-named
ms.assetid: ca9f19d7-6e86-46f2-b9ad-9bf807eaa52e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5e685ecda39e0487eb4b469920820fa6e4a10daa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569214"
---
# <a name="using-strong-named-custom-assemblies"></a><span data-ttu-id="c0bb1-102">Usando assemblies de nome forte personalizados</span><span class="sxs-lookup"><span data-stu-id="c0bb1-102">Using Strong-Named Custom Assemblies</span></span>
  <span data-ttu-id="c0bb1-103">Um nome forte identifica um assembly e inclui seu nome de texto, o número de versão de quatro partes, informações de cultura (se fornecidas), uma chave pública e uma assinatura digital armazenada no manifesto do assembly.</span><span class="sxs-lookup"><span data-stu-id="c0bb1-103">A strong name identifies an assembly and includes the assembly's text name, four-part version number, culture information (if provided), a public key, and a digital signature stored in the assembly's manifest.</span></span> <span data-ttu-id="c0bb1-104">Um nome forte identifica exclusivamente um assembly para o CLR (common language runtime) e garante a integridade binária.</span><span class="sxs-lookup"><span data-stu-id="c0bb1-104">A strong name uniquely identifies an assembly to the common language runtime (CLR) and ensures binary integrity.</span></span>  
  
## <a name="using-allowpartiallytrustedcallersattribute"></a><span data-ttu-id="c0bb1-105">Usando AllowPartiallyTrustedCallersAttribute</span><span class="sxs-lookup"><span data-stu-id="c0bb1-105">Using AllowPartiallyTrustedCallersAttribute</span></span>  
 <span data-ttu-id="c0bb1-106">Para usar assemblies de nome forte com relatórios, é necessário permitir que o assembly de nome forte seja chamado por um código parcialmente confiável usando o atributo **AllowPartiallyTrustedCallers** do assembly.</span><span class="sxs-lookup"><span data-stu-id="c0bb1-106">To use strong-named assemblies with reports, you must allow your strong-named assembly to be called by partially trusted code using the assembly's **AllowPartiallyTrustedCallers** attribute.</span></span> <span data-ttu-id="c0bb1-107">Você pode usar **AllowPartiallyTrustedCallersAttribute** para permitir que assemblies de nome forte sejam chamados pelo Designer de Relatórios ou pelo servidor de relatório em expressões de relatório.</span><span class="sxs-lookup"><span data-stu-id="c0bb1-107">You can use **AllowPartiallyTrustedCallersAttribute** to allow strong-named assemblies to be called by Report Designer or the report server in report expressions.</span></span> <span data-ttu-id="c0bb1-108">Para permitir que o código parcialmente confiável chame assemblies de nome forte, adicione o atributo de nível de assembly a seguir ao seu arquivo de atributo de assembly.</span><span class="sxs-lookup"><span data-stu-id="c0bb1-108">To allow partially trusted code to call strong-named assemblies, add the following assembly-level attribute to your assembly attribute file.</span></span>  
  
```vb  
<assembly:AllowPartiallyTrustedCallers>  
```  
  
```csharp  
[assembly:AllowPartiallyTrustedCallers]  
```  
  
 <span data-ttu-id="c0bb1-109">**AllowPartiallyTrustedCallersAttribute** só será efetivo quando aplicado por um assembly de nome forte no nível de assembly.</span><span class="sxs-lookup"><span data-stu-id="c0bb1-109">**AllowPartiallyTrustedCallersAttribute** is effective only when applied by a strong-named assembly at the assembly level.</span></span> <span data-ttu-id="c0bb1-110">Para obter mais informações sobre como aplicar atributos no nível do assembly, consulte "Aplicando atributos" na [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] documentação do SDK.</span><span class="sxs-lookup"><span data-stu-id="c0bb1-110">For more information about applying attributes at the assembly level, see "Applying Attributes" in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="c0bb1-111">Quando **AllowPartiallyTrustedCallersAttribute** estiver presente, as verificações de segurança de **FullTrustLinkDemand** serão impedidas, fazendo com que o assembly possa ser chamado de qualquer outro assembly parcialmente confiável.</span><span class="sxs-lookup"><span data-stu-id="c0bb1-111">When **AllowPartiallyTrustedCallersAttribute** is present, the default **FullTrustLinkDemand** security checks are prevented, making the assembly callable from any other partially trusted assembly.</span></span> <span data-ttu-id="c0bb1-112">Todas as verificações de segurança, incluindo os atributos de segurança declarativos de nível de classe e de nível de método, devem ser declaradas de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="c0bb1-112">All security checks, including class-level or method-level declarative security attributes, must be explicitly stated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0bb1-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c0bb1-113">See Also</span></span>  
 [<span data-ttu-id="c0bb1-114">Usando assemblies personalizados com relatórios</span><span class="sxs-lookup"><span data-stu-id="c0bb1-114">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
