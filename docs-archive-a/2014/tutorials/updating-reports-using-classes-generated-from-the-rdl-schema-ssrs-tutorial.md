---
title: Atualizando relatórios usando classes geradas do esquema RDL (tutorial do SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- RDL [Reporting Services], generating
- RDL [Reporting Services], tutorials
- RDL [Reporting Services], serializing
ms.assetid: 8f81d48f-7ab9-4ef8-bce0-7d16d9a47fbd
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: f3972b8e1af6d50ccc6f5188c8f671fe333ebce8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570367"
---
# <a name="updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial"></a><span data-ttu-id="8da11-102">Atualizando Relatórios por Meio de Classes Geradas a Partir do Esquema RDL (Tutorial SSRS)</span><span class="sxs-lookup"><span data-stu-id="8da11-102">Updating Reports Using Classes Generated from the RDL Schema (SSRS Tutorial)</span></span>
  <span data-ttu-id="8da11-103">Este tutorial ilustra como usar a ferramenta de definição de esquema XML (Xsd.exe) para gerar classes que permitem serializar e desserializar arquivos de definição de relatório (. RDL e. rdlc) com a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] <xref:System.Xml.Serialization.XmlSerializer> classe.</span><span class="sxs-lookup"><span data-stu-id="8da11-103">This tutorial illustrates how to use the XML Schema Definition Tool (Xsd.exe) to generate classes that allow you to serialize and deserialize report definition files (.rdl and .rdlc) with the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="8da11-104">O que você aprenderá</span><span class="sxs-lookup"><span data-stu-id="8da11-104">What You Will Learn</span></span>  
 <span data-ttu-id="8da11-105">No decorrer deste tutorial, você executará estas atividades:</span><span class="sxs-lookup"><span data-stu-id="8da11-105">During the course of this tutorial, you will complete the following activities:</span></span>  
  
-   <span data-ttu-id="8da11-106">Crie um aplicativo usando o [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] modelo de projeto de aplicativo de console.</span><span class="sxs-lookup"><span data-stu-id="8da11-106">Create an application using the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Console Application project template.</span></span>  
  
-   <span data-ttu-id="8da11-107">Gere classes do esquema RDL (Report Definition Language) usando a ferramenta **XSD** .</span><span class="sxs-lookup"><span data-stu-id="8da11-107">Generate classes from the Report Definition Language (RDL) schema using the **xsd** tool.</span></span>  
  
-   <span data-ttu-id="8da11-108">Conecte-se a um servidor de relatório e recupere uma definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="8da11-108">Connect to a report server and retrieve a report definition.</span></span>  
  
-   <span data-ttu-id="8da11-109">Escreva código para atualizar o arquivo de definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="8da11-109">Write code to update the report definition file.</span></span>  
  
-   <span data-ttu-id="8da11-110">Salve a definição de relatório atualizada no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="8da11-110">Save the updated report definition back to the report server.</span></span>  
  
-   <span data-ttu-id="8da11-111">Executar o aplicativo de esquema RDL (VB/C#).</span><span class="sxs-lookup"><span data-stu-id="8da11-111">Run the RDL Schema Application (VB/C#).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8da11-112">Os exemplos de código fornecidos neste tutorial poderão falhar para relatórios que não têm nenhuma descrição.</span><span class="sxs-lookup"><span data-stu-id="8da11-112">The code samples provided in this tutorial might fail for reports having no description.</span></span> <span data-ttu-id="8da11-113">A falha ocorre porque a propriedade de descrição não existe para os relatórios sem a descrição especificada.</span><span class="sxs-lookup"><span data-stu-id="8da11-113">The failure is because the description property does not exist for the reports with description not specified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8da11-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8da11-114">Requirements</span></span>  
 <span data-ttu-id="8da11-115">Para concluir o tutorial, você deve ter o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8da11-115">To complete the tutorial, you must have the following:</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="8da11-116">[!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8da11-116">[!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="8da11-117">[!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8da11-117">[!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)].</span></span>  
  
-   <span data-ttu-id="8da11-118">Permissões suficientes para acessar e publicar relatórios no serviço Web Servidor de Relatórios no computador em que o servidor de relatório está localizado.</span><span class="sxs-lookup"><span data-stu-id="8da11-118">Sufficient permissions to be able to access and publish reports to the Report Server Web service on the computer where your report server is located.</span></span>  
  
-   <span data-ttu-id="8da11-119">O banco de dados de exemplo [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] instalado em uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8da11-119">The [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] sample database installed to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="8da11-120">Um relatório instalado no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="8da11-120">A report installed on your report server.</span></span> <span data-ttu-id="8da11-121">Este tutorial usa o relatório de exemplo, Company Sales 2012.</span><span class="sxs-lookup"><span data-stu-id="8da11-121">This tutorial uses the sample report, Company Sales 2012.</span></span> <span data-ttu-id="8da11-122">Para obter mais informações sobre relatórios de exemplo, consulte [SQL Server Reporting Services exemplos de produto](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="8da11-122">For more information about sample reports, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8da11-123">Os exemplos não são instalados automaticamente durante a instalação, mas podem ser instalados a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="8da11-123">The samples are not installed automatically during setup, but you can install them at any time.</span></span> <span data-ttu-id="8da11-124">Para obter informações sobre exemplos, consulte [SQL Server exemplos de produtos](https://go.microsoft.com/fwlink/?LinkId=182887).</span><span class="sxs-lookup"><span data-stu-id="8da11-124">For information about samples, see [SQL Server Product Samples](https://go.microsoft.com/fwlink/?LinkId=182887).</span></span>  
  
 <span data-ttu-id="8da11-125">**Tempo estimado para concluir o tutorial:** 30 minutos</span><span class="sxs-lookup"><span data-stu-id="8da11-125">**Estimated time to complete the tutorial:** 30 minutes</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="8da11-126">Tarefas</span><span class="sxs-lookup"><span data-stu-id="8da11-126">Tasks</span></span>  
 [<span data-ttu-id="8da11-127">Lição 1: Criar o projeto do Visual Studio de esquema RDL</span><span class="sxs-lookup"><span data-stu-id="8da11-127">Lesson 1: Create the RDL Schema Visual Studio Project</span></span>](../../2014/tutorials/lesson-1-create-the-rdl-schema-visual-studio-project.md)  
  
 [<span data-ttu-id="8da11-128">Lição 2: Gerar classes do esquema RDL usando a ferramenta xsd</span><span class="sxs-lookup"><span data-stu-id="8da11-128">Lesson 2: Generate Classes from the RDL Schema using the xsd Tool</span></span>](../../2014/tutorials/lesson-2-generate-classes-from-the-rdl-schema-using-the-xsd-tool.md)  
  
 [<span data-ttu-id="8da11-129">Lição 3: Carregar uma definição de relatório do Servidor de Relatório</span><span class="sxs-lookup"><span data-stu-id="8da11-129">Lesson 3: Load a Report Definition from the Report Server</span></span>](../../2014/tutorials/lesson-3-load-a-report-definition-from-the-report-server.md)  
  
 [<span data-ttu-id="8da11-130">Lição 4: Atualizar a definição do relatório programaticamente</span><span class="sxs-lookup"><span data-stu-id="8da11-130">Lesson 4: Update the Report Definition Programmatically</span></span>](../../2014/tutorials/lesson-4-update-the-report-definition-programmatically.md)  
  
 [<span data-ttu-id="8da11-131">Lição 5: Publicar a definição de relatório no servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="8da11-131">Lesson 5: Publish the Report Definition to the Report Server</span></span>](../../2014/tutorials/lesson-5-publish-the-report-definition-to-the-report-server.md)  
  
 [<span data-ttu-id="8da11-132">Lição 6: executar o aplicativo de esquema RDL &#40;VB-C&#35;&#41;</span><span class="sxs-lookup"><span data-stu-id="8da11-132">Lesson 6: Run the RDL Schema Application &#40;VB-C&#35;&#41;</span></span>](../../2014/tutorials/lesson-6-run-the-rdl-schema-application-vb-csharp.md)  
  
## <a name="see-also"></a><span data-ttu-id="8da11-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8da11-133">See Also</span></span>  
 [<span data-ttu-id="8da11-134">Linguagem RDL &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8da11-134">Report Definition Language &#40;SSRS&#41;</span></span>](../reporting-services/reports/report-definition-language-ssrs.md)  
  
  
