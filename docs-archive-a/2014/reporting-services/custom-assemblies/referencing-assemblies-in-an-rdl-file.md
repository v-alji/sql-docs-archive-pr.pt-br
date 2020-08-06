---
title: Referenciando assemblies em um arquivo RDL | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- RDL [Reporting Services], referencing assemblies
- referencing custom assemblies
- custom assemblies [Reporting Services], referencing
- Report Definition Language, referencing assemblies
- report definition files [Reporting Services]
ms.assetid: 9a48e552-7d47-4243-9be1-894990c506d9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 14593717d2319d7d702fd0c414e0c24428006f51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679187"
---
# <a name="referencing-assemblies-in-an-rdl-file"></a><span data-ttu-id="180d3-102">Referenciando assemblies em um arquivo RDL</span><span class="sxs-lookup"><span data-stu-id="180d3-102">Referencing Assemblies in an RDL File</span></span>
  <span data-ttu-id="180d3-103">Para dar suporte ao uso de assemblies de código personalizado em arquivos de definição de relatório, dois elementos da linguagem RDL foram incluídos na especificação de RDL: o elemento **CodeModules** e o elemento **Classes**.</span><span class="sxs-lookup"><span data-stu-id="180d3-103">To support the use of custom code assemblies in report definition files, two Report Definition Language (RDL) elements are included in the RDL specification: the **CodeModules** element and the **Classes** element.</span></span>  
  
 <span data-ttu-id="180d3-104">O elemento **CodeModules** permite referenciar assemblies de código gerenciado em expressões de relatório.</span><span class="sxs-lookup"><span data-stu-id="180d3-104">The **CodeModules** element enables you to refer to managed code assemblies in report expressions.</span></span> <span data-ttu-id="180d3-105">**CodeModules** é um elemento de nível superior que contém a referência ao assembly usado nos arquivos de definição de relatório para chamar funções especializadas.</span><span class="sxs-lookup"><span data-stu-id="180d3-105">**CodeModules** is a top-level element that contains the reference to the assembly that you use in your report definition files to call specialized functions.</span></span> <span data-ttu-id="180d3-106">Uma entrada em uma definição de relatório que dá suporte ao uso de um assembly personalizado poderia ser assim:</span><span class="sxs-lookup"><span data-stu-id="180d3-106">An entry in a report definition that supports the use of a custom assembly might look like the following:</span></span>  
  
```  
<CodeModules>  
   <CodeModule>CurrencyConversion, Version=1.0.1363.31103, Culture=neutral, PublicKeyToken=null</CodeModule>  
</CodeModules>  
```  
  
 <span data-ttu-id="180d3-107">Em vez de chamar <xref:System.Reflection.Assembly.Load%2A> do código personalizado, registre os assemblies personalizados manualmente adicionando elementos **CodeModule** ao arquivo RDL ou usando a guia **Referências** da caixa de diálogo **Propriedades do Relatório**.</span><span class="sxs-lookup"><span data-stu-id="180d3-107">Instead of calling <xref:System.Reflection.Assembly.Load%2A> from your custom code, register your custom assemblies by either manually adding **CodeModule** elements to your RDL file or by using the **References** tab of the **Report Properties** dialog.</span></span> <span data-ttu-id="180d3-108">Para obter mais informações, consulte [Referências a código personalizado e assemblies em expressões no Designer de Relatórios &#40;SSRS&#41;](../report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="180d3-108">For more information, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](../report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  
  
 <span data-ttu-id="180d3-109">O elemento **Classes** dá suporte ao uso de membros de instância em uma definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="180d3-109">The **Classes** element supports the use of instance members in a report definition.</span></span> <span data-ttu-id="180d3-110">**Classes** é um elemento de nível superior que contém uma referência ao nome de classe e um nome de instância.</span><span class="sxs-lookup"><span data-stu-id="180d3-110">**Classes** is a top-level element that contains a reference to the class name and an instance name.</span></span> <span data-ttu-id="180d3-111">Uma entrada em uma definição de relatório que dá suporte ao uso de membros de instância poderia ser assim:</span><span class="sxs-lookup"><span data-stu-id="180d3-111">An entry in a report definition that supports the use of instance members might look like the following:</span></span>  
  
```  
<Classes>  
   <Class>  
      <ClassName>CurrencyConversion.DollarCurrencyConversion</ClassName>  
      <InstanceName>m_myDollarConversion</InstanceName>  
   </Class>  
</Classes>  
```  
  
 <span data-ttu-id="180d3-112">Para obter mais informações, consulte [Acessando assemblies personalizados por meio de expressões](accessing-custom-assemblies-through-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="180d3-112">For more information, see [Accessing Custom Assemblies Through Expressions](accessing-custom-assemblies-through-expressions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="180d3-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="180d3-113">See Also</span></span>  
 [<span data-ttu-id="180d3-114">Usando assemblies personalizados com relatórios</span><span class="sxs-lookup"><span data-stu-id="180d3-114">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
