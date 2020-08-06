---
title: Integrando o Reporting Services usando os controles ReportViewer | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- ReportViewer controls
- integrating reports [Reporting Services]
ms.assetid: 3ba47fb4-73a9-4059-89fd-329adebe94a8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 18e28dbf1557bf36106b454738d0c0bfc037f2a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569218"
---
# <a name="integrating-reporting-services-using-the-reportviewer-controls"></a><span data-ttu-id="e0cf1-102">Integrando o Reporting Services usando os controles ReportViewer</span><span class="sxs-lookup"><span data-stu-id="e0cf1-102">Integrating Reporting Services Using the ReportViewer Controls</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="e0cf1-103">[!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)]fornece dois controles ReportViewer para integrar a funcionalidade de exibição de relatório em seus aplicativos.</span><span class="sxs-lookup"><span data-stu-id="e0cf1-103">[!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] provides two ReportViewer controls for integrating report viewing functionality into your applications.</span></span> <span data-ttu-id="e0cf1-104">Existe uma versão para aplicativos baseados em Windows Forms e um para aplicativos Web Forms.</span><span class="sxs-lookup"><span data-stu-id="e0cf1-104">There is a version for Windows Forms-based applications and one for Web Forms applications.</span></span> <span data-ttu-id="e0cf1-105">Cada controle oferece funcionalidade semelhante mas cada é foi criado para ter como destino seus ambientes individuais.</span><span class="sxs-lookup"><span data-stu-id="e0cf1-105">Each control provides similar functionality but each is designed to target their individual environments.</span></span> <span data-ttu-id="e0cf1-106">Ambos os controles podem processar relatórios que foram implantados em um servidor de relatório (modo de processamento remoto) ou que foram copiados para um computador em que o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] não foi instalado (modo de processamento local).</span><span class="sxs-lookup"><span data-stu-id="e0cf1-106">Both controls can process reports that have been deployed to a report server (remote processing mode) or have been copied to a computer where [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] has not been installed (local processing mode).</span></span>  
  
 <span data-ttu-id="e0cf1-107">O controle ReportViewer não inclui suporte interno para adaptar-se de forma dinâmica a dispositivos diferentes com diferentes resoluções de tela.</span><span class="sxs-lookup"><span data-stu-id="e0cf1-107">The ReportViewer control does not include built-in support for dynamically adapting to different devices with different screen resolutions.</span></span>  
  
## <a name="remote-processing-mode"></a><span data-ttu-id="e0cf1-108">Modo de processamento remoto</span><span class="sxs-lookup"><span data-stu-id="e0cf1-108">Remote Processing Mode</span></span>  
 <span data-ttu-id="e0cf1-109">O modo de processamento remoto é o método preferido para exibir relatórios implantados em um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="e0cf1-109">Remote processing mode is the preferred method for viewing reports that have been deployed to a report server.</span></span> <span data-ttu-id="e0cf1-110">O modo de processamento remoto oferece as seguintes vantagens:</span><span class="sxs-lookup"><span data-stu-id="e0cf1-110">Remote processing mode provides the following advantages:</span></span>  
  
-   <span data-ttu-id="e0cf1-111">O processamento remoto fornece uma solução otimizada para a execução de relatórios porque o relatório é processado pelo servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="e0cf1-111">Remote processing provides an optimized solution for running reports because the report is processed by the report server.</span></span>  
  
-   <span data-ttu-id="e0cf1-112">Como todo o processamento é manipulado pelo servidor de relatório, uma solicitação de relatório pode ser processada por vários servidores de relatório em uma implantação em expansão ou por um servidor com vários processadores em um cenário de aumento de escala.</span><span class="sxs-lookup"><span data-stu-id="e0cf1-112">Because all processing is handled by the report server, a report request can be processed by multiple report servers in a scale-out deployment or a server that has multiple processors in a scale-up scenario.</span></span>  
  
 <span data-ttu-id="e0cf1-113">Além disso, o relatório executado em modo remoto pode utilizar a funcionalidade completa do servidor de relatório, incluindo toda a renderização e extensões de dados.</span><span class="sxs-lookup"><span data-stu-id="e0cf1-113">In addition, reports run in remote mode can utilize the full functionality of the report server including all rendering and data extensions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e0cf1-114">A lista de extensões disponíveis para o controle ReportViewer quando ele estiver sendo executado no modo de processamento remoto dependerá da edição do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instalada no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="e0cf1-114">The list of extensions available to the ReportViewer control when it is running in remote processing mode depends on the edition of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] that is installed on the report server.</span></span>  
  
## <a name="local-processing-mode"></a><span data-ttu-id="e0cf1-115">Modo de processamento local</span><span class="sxs-lookup"><span data-stu-id="e0cf1-115">Local Processing Mode</span></span>  
 <span data-ttu-id="e0cf1-116">O modo de processamento local oferece um método alternativo para a exibição e para a renderização de relatórios quando o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] não estiver instalado.</span><span class="sxs-lookup"><span data-stu-id="e0cf1-116">Local processing mode provides an alternative method for viewing and rendering reports when [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is not installed.</span></span> <span data-ttu-id="e0cf1-117">Ao contrário do processamento remoto, somente um subconjunto da funcionalidade fornecida pelo servidor de relatório estará disponível no controle.</span><span class="sxs-lookup"><span data-stu-id="e0cf1-117">Unlike remote processing only a subset of the functionality provided by the report server is available in the control.</span></span> <span data-ttu-id="e0cf1-118">No modo de processamento local, o processamento de dados não é realizado pelo controle, mas implementado pelo aplicativo host.</span><span class="sxs-lookup"><span data-stu-id="e0cf1-118">In local processing mode, data processing is not handled by the control but rather implemented by the hosting application.</span></span> <span data-ttu-id="e0cf1-119">Entretanto, o processamento de relatórios é tratado pelo próprio controle.</span><span class="sxs-lookup"><span data-stu-id="e0cf1-119">However report processing is handled by the control itself.</span></span> <span data-ttu-id="e0cf1-120">No modo de processamento local, somente as extensões de renderização PDF, Excel, Word e Imagem estarão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="e0cf1-120">In local processing mode, only the PDF, Excel, Word, and Image rendering extensions are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0cf1-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e0cf1-121">See Also</span></span>  
 <span data-ttu-id="e0cf1-122">[Integrando Reporting Services em aplicativos](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="e0cf1-122">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 [<span data-ttu-id="e0cf1-123">Criar relatórios do SSRS usando o Visual Studio (blog)</span><span class="sxs-lookup"><span data-stu-id="e0cf1-123">Create SSRS Reports Using Visual Studio (Blog)</span></span>](https://jwcooney.com/2015/01/07/ssrs-basics-set-up-visual-studio-to-write-a-new-ssrs-report/)  
  
  
