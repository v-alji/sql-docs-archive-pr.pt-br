---
title: Acessando o serviço Web servidor de relatórios usando o Visual Basic ou o Visual C# (tutorial do SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
dev_langs:
- VB
helpviewer_keywords:
- walkthroughs [Reporting Services]
- Reporting Services, Web service
- Web service [Reporting Services], tutorials
ms.assetid: cf688163-4ac0-475b-b6dd-6f2f05b553c6
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 3dc2599b4fafe682d74089d637918e04db9ed219
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683224"
---
# <a name="accessing-the-report-server-web-service-using-visual-basic-or-visual-c-ssrs-tutorial"></a><span data-ttu-id="d342a-102">Acessando o Serviço Web do Servidor de Relatórios com Visual Basic ou Visual C# (Tutorial SSRS)</span><span class="sxs-lookup"><span data-stu-id="d342a-102">Accessing the Report Server Web Service Using Visual Basic or Visual C# (SSRS Tutorial)</span></span>
  <span data-ttu-id="d342a-103">O tutorial a seguir mostra como acessar o serviço Web servidor de relatórios de um aplicativo criado com o [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] ou o [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[csprcs](../includes/csprcs-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d342a-103">The following tutorial shows you how to access the Report Server Web service from an application created with [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] or [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[csprcs](../includes/csprcs-md.md)].</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="d342a-104">O que você aprenderá</span><span class="sxs-lookup"><span data-stu-id="d342a-104">What You Will Learn</span></span>  
 <span data-ttu-id="d342a-105">No decorrer deste tutorial, você fará o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d342a-105">During the course of this tutorial, you will complete the following:</span></span>  
  
-   <span data-ttu-id="d342a-106">Crie um aplicativo cliente usando o [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] modelo de projeto de aplicativo de console.</span><span class="sxs-lookup"><span data-stu-id="d342a-106">Create a client application using the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] Console Application project template.</span></span>  
  
-   <span data-ttu-id="d342a-107">Adicionará uma referência Web para o serviço Web Servidor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="d342a-107">Add a Web reference for the Report Server Web service.</span></span>  
  
-   <span data-ttu-id="d342a-108">Escreverá código para acessar o serviço Web.</span><span class="sxs-lookup"><span data-stu-id="d342a-108">Write code to access the Web service.</span></span>  
  
-   <span data-ttu-id="d342a-109">Executará o aplicativo de console no modo de depuração.</span><span class="sxs-lookup"><span data-stu-id="d342a-109">Run the console application in debug mode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d342a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d342a-110">Requirements</span></span>  
 <span data-ttu-id="d342a-111">Para concluir o tutorial, você deve ter o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d342a-111">To complete the tutorial, you must have the following:</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="d342a-112">[!INCLUDE[ssSQL11](../includes/sssql11-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d342a-112">[!INCLUDE[ssSQL11](../includes/sssql11-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)]<span data-ttu-id="d342a-113">[!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)]ou um semelhante [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] -ferramenta de desenvolvimento compatível.</span><span class="sxs-lookup"><span data-stu-id="d342a-113">[!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] or a similar [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]-compatible development tool.</span></span>  
  
-   <span data-ttu-id="d342a-114">Permissões suficientes para acessar o serviço Web Servidor de Relatórios do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] no computador em que o servidor de relatório está localizado.</span><span class="sxs-lookup"><span data-stu-id="d342a-114">Sufficient permissions to be able to access the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Report Server Web service on the computer where your report server is located.</span></span>  
  
-   <span data-ttu-id="d342a-115">Um relatório instalado no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="d342a-115">A report installed on your report server.</span></span> <span data-ttu-id="d342a-116">Este tutorial usa o relatório de exemplo, Vendas da Empresa.</span><span class="sxs-lookup"><span data-stu-id="d342a-116">This tutorial uses the sample report, Company Sales.</span></span> <span data-ttu-id="d342a-117">Para obter mais informações sobre relatórios de exemplo, consulte [SQL Server Reporting Services exemplos de produto](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="d342a-117">For more information about sample reports, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d342a-118">Os exemplos não são instalados automaticamente durante a instalação, mas podem ser instalados a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="d342a-118">The samples are not installed automatically during setup, but you can install them at any time.</span></span> <span data-ttu-id="d342a-119">Para obter informações sobre exemplos, consulte [SQL Server exemplos de produtos](https://go.microsoft.com/fwlink/?LinkId=182887).</span><span class="sxs-lookup"><span data-stu-id="d342a-119">For information about samples, see [SQL Server Product Samples](https://go.microsoft.com/fwlink/?LinkId=182887).</span></span>  
  
 <span data-ttu-id="d342a-120">**Tempo estimado para concluir o tutorial:** 60 minutos</span><span class="sxs-lookup"><span data-stu-id="d342a-120">**Estimated time to complete the tutorial:** 60 minutes</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="d342a-121">Tarefas</span><span class="sxs-lookup"><span data-stu-id="d342a-121">Tasks</span></span>  
 [<span data-ttu-id="d342a-122">Lição 1: Criando o serviço Web Projeto de Cliente</span><span class="sxs-lookup"><span data-stu-id="d342a-122">Lesson 1: Creating the Web Service Client Project</span></span>](../../2014/tutorials/lesson-1-creating-the-web-service-client-project.md)  
  
 [<span data-ttu-id="d342a-123">Lição 2: Adicionando uma referência Web</span><span class="sxs-lookup"><span data-stu-id="d342a-123">Lesson 2: Adding a Web Reference</span></span>](../../2014/tutorials/lesson-2-adding-a-web-reference.md)  
  
 [<span data-ttu-id="d342a-124">Lição 3: Acessando o serviço Web</span><span class="sxs-lookup"><span data-stu-id="d342a-124">Lesson 3: Accessing the Web Service</span></span>](../../2014/tutorials/lesson-3-accessing-the-web-service.md)  
  
 [<span data-ttu-id="d342a-125">Lição 4: executando o aplicativo &#40;VB-VC&#35;&#41;</span><span class="sxs-lookup"><span data-stu-id="d342a-125">Lesson 4: Running the Application &#40;VB-VC&#35;&#41;</span></span>](../../2014/tutorials/lesson-4-running-the-application-vb-vcsharp.md)  
  
  
