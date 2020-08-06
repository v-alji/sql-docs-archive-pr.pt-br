---
title: Omitindo valores para objetos opcionais de serviço Web | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], omitted values
- XML Web service [Reporting Services], omitted values
- Report Server Web service, omitted values
- omitting values [Reporting Services]
ms.assetid: ceb68b8b-9214-4745-abc9-f47f33ecd6f7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3858f73e1b332acfa1a1bbc640007f6f0884abff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679683"
---
# <a name="omitting-values-for-optional-web-service-objects"></a><span data-ttu-id="7248e-102">Omitindo valores para objetos de serviço Web opcionais</span><span class="sxs-lookup"><span data-stu-id="7248e-102">Omitting Values for Optional Web Service Objects</span></span>
  <span data-ttu-id="7248e-103">Propriedades de vários tipos complexos de serviço Web Servidor de Relatórios têm uma propriedade complementar conhecida como propriedade Specified.</span><span class="sxs-lookup"><span data-stu-id="7248e-103">Properties of several of the Report Server Web service complex types have an accompanying property known as the Specified property.</span></span> <span data-ttu-id="7248e-104">O nome da propriedade consiste no nome de propriedade original com a palavra "Especificada" anexada a ele.</span><span class="sxs-lookup"><span data-stu-id="7248e-104">The name of the property consists of the original property name with the word "Specified" appended to it.</span></span> <span data-ttu-id="7248e-105">A presença dessa propriedade indica que um valor da propriedade original às vezes pode ser omitido.</span><span class="sxs-lookup"><span data-stu-id="7248e-105">The presence of this property indicates that a value for the original property may sometimes be omitted.</span></span> <span data-ttu-id="7248e-106">Este é um resultado direto da conversão da WSDL (Web Service Description Language) em uma classe proxy [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7248e-106">This is a direct result of the translation from the Web Service Description Language (WSDL) to a [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] proxy class.</span></span> <span data-ttu-id="7248e-107">Por exemplo, a propriedade de serviço Web <xref:ReportService2010.DataSourceDefinition.Enabled%2A> do tipo complexo <xref:ReportService2010.DataSourceDefinition> tem uma propriedade associada nomeada <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A>.</span><span class="sxs-lookup"><span data-stu-id="7248e-107">For example, the Web service property <xref:ReportService2010.DataSourceDefinition.Enabled%2A> of the complex type <xref:ReportService2010.DataSourceDefinition> has an accompanying property named <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A>.</span></span> <span data-ttu-id="7248e-108">Se você estiver criando um aplicativo e não quiser definir um valor para a propriedade <xref:ReportService2010.DataSourceDefinition.Enabled%2A>, não precisará fornecer um valor para <xref:ReportService2010.DataSourceDefinition.Enabled%2A>; o valor padrão de `true` é usado.</span><span class="sxs-lookup"><span data-stu-id="7248e-108">If you are building an application and do not want to set a value for the <xref:ReportService2010.DataSourceDefinition.Enabled%2A> property, you do not have to supply a value for <xref:ReportService2010.DataSourceDefinition.Enabled%2A>; the default value of `true` is used.</span></span> <span data-ttu-id="7248e-109">Porém, você ainda precisa definir <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A> como `false`.</span><span class="sxs-lookup"><span data-stu-id="7248e-109">However, you still need to set <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A> to `false`.</span></span> <span data-ttu-id="7248e-110">Se você fornecer um valor para a propriedade <xref:ReportService2010.DataSourceDefinition.Enabled%2A>, precisará definir <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A> igual a `true`.</span><span class="sxs-lookup"><span data-stu-id="7248e-110">If you supply a value for the <xref:ReportService2010.DataSourceDefinition.Enabled%2A> property, you need to set <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A> equal to `true`.</span></span> <span data-ttu-id="7248e-111">Esse é o caso de propriedades graváveis.</span><span class="sxs-lookup"><span data-stu-id="7248e-111">This is the case for writable properties.</span></span> <span data-ttu-id="7248e-112">Para propriedades somente leitura, você não precisa tomar uma ação.</span><span class="sxs-lookup"><span data-stu-id="7248e-112">For read-only properties, you do not need to take any action.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7248e-113">A falha em especificar uma propriedade usando a técnica supracitada pode resultar em comportamento de serviço Web imprevisível.</span><span class="sxs-lookup"><span data-stu-id="7248e-113">Failure to specify a property using the above-mentioned technique can result in unpredictable Web service behavior.</span></span>  
  
 <span data-ttu-id="7248e-114">Os tipos de dados que geralmente exigem que você manipule a propriedade adicional especificada são `Boolean` , `DateTime` e `Enumeration` .</span><span class="sxs-lookup"><span data-stu-id="7248e-114">The data types that usually require you to handle the additional Specified property are `Boolean`, `DateTime`, and `Enumeration`.</span></span>  
  
 <span data-ttu-id="7248e-115">Para obter um exemplo, consulte o método <xref:ReportService2010.ReportingService2010.CreateDataSource%2A>.</span><span class="sxs-lookup"><span data-stu-id="7248e-115">For an example, see <xref:ReportService2010.ReportingService2010.CreateDataSource%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7248e-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7248e-116">See Also</span></span>  
 <span data-ttu-id="7248e-117">[Criando aplicativos usando o serviço Web e o .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="7248e-117">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="7248e-118">Referência técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7248e-118">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
