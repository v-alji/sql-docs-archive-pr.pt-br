---
title: Criando um relatório de tabela básico (Tutorial do SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- walkthroughs [Reporting Services]
- tutorials [Reporting Services]
- reports [Reporting Services], creating
ms.assetid: 3b539b4b-26f2-4c0b-b506-80f175679a46
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 02e0f42869a3bfa88e0c6646fd447968c8ba3a10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568349"
---
# <a name="create-a-basic-table-report-ssrs-tutorial"></a><span data-ttu-id="99804-102">Criando um relatório de tabela básico (Tutorial do SSRS)</span><span class="sxs-lookup"><span data-stu-id="99804-102">Create a Basic Table Report (SSRS Tutorial)</span></span>
  <span data-ttu-id="99804-103">Este tutorial foi criado para ajudar a criar uma tabela básica com base no banco de dados [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] usando o Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="99804-103">This tutorial is designed to help you create a basic table report based on the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database using Report Designer.</span></span> <span data-ttu-id="99804-104">Você também pode usar o Construtor de Relatórios ou o Assistente de Relatório para criar relatórios.</span><span class="sxs-lookup"><span data-stu-id="99804-104">You can also use Report Builder or the Report Wizard to create reports.</span></span> <span data-ttu-id="99804-105">Neste tutorial, você irá criar um projeto de relatório, configurar informações de conexão, definir uma consulta, adicionar uma região de dados de Tabela, agrupar e totalizar alguns campos e visualizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="99804-105">In this tutorial, you will create a report project, set up connection information, define a query, add a Table data region, group and total some fields, and preview the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="99804-106">Para concluir este tutorial, você deve estar executando o [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] em modo nativo.</span><span class="sxs-lookup"><span data-stu-id="99804-106">To complete this tutorial, you must be running [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] in native mode.</span></span> <span data-ttu-id="99804-107">Se você estiver executando o [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] em modo integrado do SharePoint, as etapas que usam URLs de servidor de relatório não funcionarão.</span><span class="sxs-lookup"><span data-stu-id="99804-107">If you are running [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] in SharePoint integrated mode, the steps that use report server URLs do not work.</span></span> <span data-ttu-id="99804-108">Para obter mais informações sobre [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] modos, consulte [Reporting Services servidor de relatório](reporting-services-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="99804-108">For more information about [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] modes, see [Reporting Services Report Server](reporting-services-report-server.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99804-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="99804-109">Requirements</span></span>  
 <span data-ttu-id="99804-110">Para que você possa usar o tutorial, os itens a seguir devem estar instalados no sistema:</span><span class="sxs-lookup"><span data-stu-id="99804-110">Your system must have the following installed to use this tutorial:</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)]<span data-ttu-id="99804-111">[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]mecanismo de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="99804-111">[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] database engine.</span></span>  
  
-   <span data-ttu-id="99804-112">O banco de dados [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="99804-112">The [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span>  <span data-ttu-id="99804-113">Para obter mais informações, consulte [Adventure Works para SQL Server 2012 (Adventure Works para SQL Server 2012)](https://go.microsoft.com/fwlink/?LinkId=245471) ( https://go.microsoft.com/fwlink/?LinkId=245471). .</span><span class="sxs-lookup"><span data-stu-id="99804-113">For more information, see [Adventure Works for SQL Server 2012 (Adventure Works for SQL Server 2012)](https://go.microsoft.com/fwlink/?LinkId=245471) (https://go.microsoft.com/fwlink/?LinkId=245471)..</span></span> <span data-ttu-id="99804-114">Para obter mais informações sobre o suporte para [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] bancos de dados de exemplo e código de exemplo para o [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] , consulte [visão geral de bancos de dados e exemplos](https://go.microsoft.com/fwlink/?LinkId=110391) no site do CodePlex.</span><span class="sxs-lookup"><span data-stu-id="99804-114">For more information about support for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] sample databases and sample code for [!INCLUDE[ssExpress](../includes/ssexpress-md.md)], see [Databases and Samples Overview](https://go.microsoft.com/fwlink/?LinkId=110391) on the CodePlex Web site.</span></span>  
  
-   [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)]<span data-ttu-id="99804-115">.</span><span class="sxs-lookup"><span data-stu-id="99804-115">.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="99804-116">[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99804-116">[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssNote64Samp](../includes/ssnote64samp-md.md)]  
  
 <span data-ttu-id="99804-117">Também é necessário ter permissões somente leitura para recuperar dados do banco de dados [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="99804-117">You must also have read-only permissions to retrieve data from the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="99804-118">Tarefas</span><span class="sxs-lookup"><span data-stu-id="99804-118">Tasks</span></span>  
 [<span data-ttu-id="99804-119">Lição 1: Criando um projeto do Servidor de Relatório &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="99804-119">Lesson 1: Creating a Report Server Project &#40;Reporting Services&#41;</span></span>](lesson-1-creating-a-report-server-project-reporting-services.md)  
  
 [<span data-ttu-id="99804-120">Lição 2: Especificando informações sobre conexão &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="99804-120">Lesson 2: Specifying Connection Information &#40;Reporting Services&#41;</span></span>](lesson-2-specifying-connection-information-reporting-services.md)  
  
 [<span data-ttu-id="99804-121">Lição 3: Definindo um conjunto de dados para o relatório de tabela &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="99804-121">Lesson 3: Defining a Dataset for the Table Report &#40;Reporting Services&#41;</span></span>](lesson-3-defining-a-dataset-for-the-table-report-reporting-services.md)  
  
 [<span data-ttu-id="99804-122">Lição 4: Adicionando uma tabela ao relatório &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="99804-122">Lesson 4: Adding a Table to the Report &#40;Reporting Services&#41;</span></span>](lesson-4-adding-a-table-to-the-report-reporting-services.md)  
  
 [<span data-ttu-id="99804-123">Lição 5: Formatando um relatório &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="99804-123">Lesson 5: Formatting a Report &#40;Reporting Services&#41;</span></span>](lesson-5-formatting-a-report-reporting-services.md)  
  
 [<span data-ttu-id="99804-124">Lição 6: Adicionando agrupamentos e totais &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="99804-124">Lesson 6: Adding Grouping and Totals &#40;Reporting Services&#41;</span></span>](lesson-6-adding-grouping-and-totals-reporting-services.md)  
  
> [!NOTE]  
>  <span data-ttu-id="99804-125">Ao revisar os tutoriais, recomendamos que você adicione os botões **Avançar** e **anterior** à barra de ferramentas do Visualizador de documentos.</span><span class="sxs-lookup"><span data-stu-id="99804-125">When reviewing tutorials, we recommend that you add **Next** and **Previous** buttons to the document viewer toolbar.</span></span> <span data-ttu-id="99804-126">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="99804-126">For more information, see.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99804-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="99804-127">See Also</span></span>  
 [<span data-ttu-id="99804-128">Tutoriais do Reporting Services &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="99804-128">Reporting Services Tutorials &#40;SSRS&#41;</span></span>](reporting-services-tutorials-ssrs.md)  
  
  
