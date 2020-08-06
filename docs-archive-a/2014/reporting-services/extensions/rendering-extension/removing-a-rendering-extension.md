---
title: Removendo uma extensão de renderização | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- deleting rendering extensions
- removing rendering extensions
- rendering extensions [Reporting Services], removing
ms.assetid: 2abfebfb-065f-45cc-a904-c914394cf900
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 77a8a9ac44b35f338f978913985617e4f264ddb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574533"
---
# <a name="removing-a-rendering-extension"></a><span data-ttu-id="4d0c6-102">Removendo uma extensão de renderização</span><span class="sxs-lookup"><span data-stu-id="4d0c6-102">Removing a Rendering Extension</span></span>
  <span data-ttu-id="4d0c6-103">Para remover uma [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] extensão de renderização, basta remover o `Extension` elemento da extensão de renderização do arquivo rsreportserver.config, localizado em **%programfiles%\microsoft SQL Server \ MSRS10_50. \<Instance Name> Pasta \Reporting Services\ReportServer**</span><span class="sxs-lookup"><span data-stu-id="4d0c6-103">To remove a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] rendering extension, simply remove the `Extension` element for your rendering extension from the rsreportserver.config file, located in **%ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<Instance Name>\Reporting Services\ReportServer** folder.</span></span> <span data-ttu-id="4d0c6-104">Se você tiver feito entradas para um Report Designer, bem como um servidor de relatório, remova o `Extension` elemento do [arquivo de configuração RSReportDesigner](../../report-server/rsreportdesigner-configuration-file.md) também.</span><span class="sxs-lookup"><span data-stu-id="4d0c6-104">If you made entries for a Report Designer as well as a report server, remove the `Extension` element from the [RSReportDesigner Configuration File](../../report-server/rsreportdesigner-configuration-file.md) as well.</span></span> <span data-ttu-id="4d0c6-105">Após a remoção das informações de configuração, a extensão de renderização não estará mais disponível para o componente.</span><span class="sxs-lookup"><span data-stu-id="4d0c6-105">After the configuration information is removed, the rendering extension is no longer available to the component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d0c6-106">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4d0c6-106">See Also</span></span>  
 <span data-ttu-id="4d0c6-107">[Arquivos de configuração do Reporting Services](../../report-server/reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="4d0c6-107">[Reporting Services Configuration Files](../../report-server/reporting-services-configuration-files.md) </span></span>  
 <span data-ttu-id="4d0c6-108">[Implementando uma extensão de renderização](implementing-a-rendering-extension.md) </span><span class="sxs-lookup"><span data-stu-id="4d0c6-108">[Implementing a Rendering Extension](implementing-a-rendering-extension.md) </span></span>  
 <span data-ttu-id="4d0c6-109">[Visão geral das extensões de renderização](rendering-extensions-overview.md) </span><span class="sxs-lookup"><span data-stu-id="4d0c6-109">[Rendering Extensions Overview](rendering-extensions-overview.md) </span></span>  
 <span data-ttu-id="4d0c6-110">[Implementando a interface IRenderingExtension](implementing-the-irenderingextension-interface.md) </span><span class="sxs-lookup"><span data-stu-id="4d0c6-110">[Implementing the IRenderingExtension Interface](implementing-the-irenderingextension-interface.md) </span></span>  
 <span data-ttu-id="4d0c6-111">[Considerações sobre segurança para extensões](../security-considerations-for-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="4d0c6-111">[Security Considerations for Extensions](../security-considerations-for-extensions.md) </span></span>  
 [<span data-ttu-id="4d0c6-112">Implantando uma extensão de renderização</span><span class="sxs-lookup"><span data-stu-id="4d0c6-112">Deploying a Rendering Extension</span></span>](deploying-a-rendering-extension.md)  
  
  
