---
title: 'Como fazer: Implantar um item de relatório personalizado | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom report items, deploying
ms.assetid: 80e97b0d-e355-4240-aebd-08cbc84089ed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 66519610526478caadeb41b48c9823414e88d5d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685462"
---
# <a name="how-to-deploy-a-custom-report-item"></a><span data-ttu-id="e7a0b-102">Como fazer: Implantar um item de relatório personalizado</span><span class="sxs-lookup"><span data-stu-id="e7a0b-102">How to: Deploy a Custom Report Item</span></span>
  <span data-ttu-id="e7a0b-103">Para implantar um item de relatório personalizado no [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], modifique os arquivos de configuração do servidor de relatório e copie os assemblies de componente em tempo de design e em tempo de execução nas pastas de aplicativo apropriadas para o Designer de Relatórios e o servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="e7a0b-103">To deploy a custom report item in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must modify the report server configuration files and copy the design-time and run-time component assemblies into the appropriate application folders for both Report Designer and the report server.</span></span>  
  
### <a name="to-deploy-a-custom-report-item"></a><span data-ttu-id="e7a0b-104">Para implantar um item de relatório personalizado</span><span class="sxs-lookup"><span data-stu-id="e7a0b-104">To deploy a custom report item</span></span>  
  
1.  <span data-ttu-id="e7a0b-105">Edite o arquivo Rsreportdesigner.config para configurar os componentes de item de relatório personalizado em tempo de execução e tempo de design para uso no designer.</span><span class="sxs-lookup"><span data-stu-id="e7a0b-105">Edit the Rsreportdesigner.config file to configure the custom report item run-time and design-time components for use in the designer.</span></span> <span data-ttu-id="e7a0b-106">Observe que a entrada `ReportItemName` deve corresponder ao atributo `CustomReportItemAttribute` usado em sua classe `CustomReportItemDesigner`.</span><span class="sxs-lookup"><span data-stu-id="e7a0b-106">Note that the `ReportItemName` entry must match the `CustomReportItemAttribute` attribute used in your `CustomReportItemDesigner` class.</span></span> <span data-ttu-id="e7a0b-107">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e7a0b-107">For example:</span></span>  
  
    ```  
    <ReportItems>  
       <ReportItem Name="Polygons" Type="PolygonsCRI.PolygonsCRI,PolygonsCRI"/>  
    </ReportItems>  
    <ReportItemDesigner>  
       <ReportItem Name="Polygons" Type="PolygonsCRI.PolygonsDesigner, PolygonsDesigner" />  
    </ReportItemDesigner>  
    <ReportItemConverter>  
       <Converter Source="Chart" Target="Polygons" Type="PolygonsCRI.PolygonsConverter, PolygonsDesigner" />  
    </ReportItemConverter>  
    ```  
  
2.  <span data-ttu-id="e7a0b-108">Edite o arquivo Rsreportserver.config para registrar o componente de item de relatório personalizado em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="e7a0b-108">Edit the Rsreportserver.config file to register the custom report item run-time component.</span></span> <span data-ttu-id="e7a0b-109">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e7a0b-109">For example:</span></span>  
  
    ```  
    <ReportItems>  
       <ReportItem Name="Polygons" Type="PolygonsCRI.PolygonsCRI,PolygonsCRI"/>  
    </ReportItems>  
    ```  
  
3.  <span data-ttu-id="e7a0b-110">Edite o arquivo Rsssrvpolicy.config para adicionar um `CodeGroup` que concede as permissões adequadas ao item de relatório personalizado.</span><span class="sxs-lookup"><span data-stu-id="e7a0b-110">Edit the Rsssrvpolicy.config file to add a `CodeGroup` that grants the proper permissions to the custom report item.</span></span> <span data-ttu-id="e7a0b-111">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e7a0b-111">For example:</span></span>  
  
    ```  
    <CodeGroup   
       class="UnionCodeGroup"   
       version="1"   
       PermissionSetName="FullTrust"  
       Description="This code group grants MyCustomReportItem.dll FullTrust permission. ">  
       <IMembershipCondition   
          class="UrlMembershipCondition"  
          version="1"  
       Url="C:\Program Files\Microsoft SQL Server\ MSRS10_50.SQLSERVER\Reporting Services\ReportServer\bin\MyCustomReportItem.dll" />  
    </CodeGroup>  
    ```  
  
4.  <span data-ttu-id="e7a0b-112">Copie a DLL de componente em tempo de execução de relatório personalizado para os diretórios %ProgramFiles%\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies e \Arquivos de Programas\Microsoft SQL Server\MSRS10_50.SQLSERVER\Reporting Services\ReportServer\bin.</span><span class="sxs-lookup"><span data-stu-id="e7a0b-112">Copy the custom report item run-time component DLL to the %ProgramFiles%\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies and \Program Files\Microsoft SQL Server\MSRS10_50.SQLSERVER\Reporting Services\ReportServer\bin directories.</span></span>  
  
5.  <span data-ttu-id="e7a0b-113">Copie a DLL de componente em tempo de design de item de relatório personalizado para o diretório %ProgramFiles%\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span><span class="sxs-lookup"><span data-stu-id="e7a0b-113">Copy the custom report item design-time component DLL to the %ProgramFiles%\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7a0b-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e7a0b-114">See Also</span></span>  
 <span data-ttu-id="e7a0b-115">[Arquivos de configuração do Reporting Services](../report-server/reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="e7a0b-115">[Reporting Services Configuration Files](../report-server/reporting-services-configuration-files.md) </span></span>  
 [<span data-ttu-id="e7a0b-116">Bibliotecas de classes de itens de relatório personalizados</span><span class="sxs-lookup"><span data-stu-id="e7a0b-116">Custom Report Item Class Libraries</span></span>](custom-report-item-class-libraries.md)  
  
  
