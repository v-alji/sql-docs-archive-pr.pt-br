---
title: Gerar scripts com o utilitário rs.exe e o serviço Web | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Web service [Reporting Services], scripts
- rs utility
- XML Web service [Reporting Services], scripts
- Report Server Web service, scripts
- scripts [Reporting Services], Web service
ms.assetid: 0ec5ac6e-b3cf-49cd-96f6-6b4b7dc29982
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9d84bb8722fd31a08ff7788ad31c601b377c23d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575021"
---
# <a name="script-with-the-rsexe-utility-and-the-web-service"></a><span data-ttu-id="22f6b-102">Gerar scripts com o utilitário rs.exe e o serviço Web</span><span class="sxs-lookup"><span data-stu-id="22f6b-102">Script with the rs.exe Utility and the Web Service</span></span>
  <span data-ttu-id="22f6b-103">Desenvolvedores e administradores de servidor de relatório podem executar operações em um servidor de relatório por meio do utilitário **rs** (RS.exe).</span><span class="sxs-lookup"><span data-stu-id="22f6b-103">Developers and report server administrators can perform operations on a report server through the use of the **rs** utility (RS.exe).</span></span> <span data-ttu-id="22f6b-104">Com esse utilitário, você pode administrar de maneira programática um servidor de relatório usando scripts gravados com [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22f6b-104">Using this utility, you can programmatically administer a report server using scripts written with [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span></span>  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="22f6b-105">Os scripts podem ser usados para executar qualquer uma das operações de serviço Web do Servidor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="22f6b-105">scripts can be used to run any of the Report Server Web service operations.</span></span> <span data-ttu-id="22f6b-106">A geração de scripts pode ser usada para copiar a segurança para múltiplos relatórios em um servidor, acrescentar e excluir itens, copiar itens do servidor de relatório de um servidor para outro, entre outros.</span><span class="sxs-lookup"><span data-stu-id="22f6b-106">Scripting can be used to copy security to multiple reports on a server, to add and delete items, to copy report server items from one server to another and more.</span></span> <span data-ttu-id="22f6b-107">Para obter mais informações sobre o ambiente de scripts, consulte [Executar um arquivo de script do Reporting Services](run-a-reporting-services-script-file.md).</span><span class="sxs-lookup"><span data-stu-id="22f6b-107">For more information about the scripting environment, see [Run a Reporting Services Script File](run-a-reporting-services-script-file.md).</span></span> <span data-ttu-id="22f6b-108">Os arquivos de script usam um formato específico e são gravados no [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET.</span><span class="sxs-lookup"><span data-stu-id="22f6b-108">Script files take a certain format and are written in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET.</span></span> <span data-ttu-id="22f6b-109">Para obter mais informações, consulte [Formatar um arquivo de script do Reporting Services](format-a-reporting-services-script-file.md).</span><span class="sxs-lookup"><span data-stu-id="22f6b-109">For more information, see [Format a Reporting Services Script File](format-a-reporting-services-script-file.md).</span></span>  
  
 <span data-ttu-id="22f6b-110">Para exemplos de script, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="22f6b-110">For script samples, see the following:</span></span>  
  
 <span data-ttu-id="22f6b-111">[Reporting Services de exemplo rs.exe script para migrar conteúdo entre servidores de relatório](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span><span class="sxs-lookup"><span data-stu-id="22f6b-111">[Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span></span>  
  
 <span data-ttu-id="22f6b-112">[Amostras de produto do SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="22f6b-112">[SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22f6b-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="22f6b-113">See Also</span></span>  
 <span data-ttu-id="22f6b-114">[Implantação de script e tarefas administrativas](script-deployment-and-administrative-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="22f6b-114">[Script Deployment and Administrative Tasks](script-deployment-and-administrative-tasks.md) </span></span>  
 <span data-ttu-id="22f6b-115">[Serviço Web Servidor de Relatórios](../report-server-web-service/report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="22f6b-115">[Report Server Web Service](../report-server-web-service/report-server-web-service.md) </span></span>  
 <span data-ttu-id="22f6b-116">[Referência técnica &#40;SSRS&#41;](../technical-reference-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="22f6b-116">[Technical Reference &#40;SSRS&#41;](../technical-reference-ssrs.md) </span></span>  
 [<span data-ttu-id="22f6b-117">Utilitário RS.exe &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="22f6b-117">RS.exe Utility &#40;SSRS&#41;</span></span>](rs-exe-utility-ssrs.md)  
  
  
