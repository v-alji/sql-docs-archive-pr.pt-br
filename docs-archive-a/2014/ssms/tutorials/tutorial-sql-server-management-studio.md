---
title: 'Tutorial: SQL Server Management Studio'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.tutorialstart.ssms.f1
helpviewer_keywords:
- projects [SQL Server Management Studio], tutorials
- templates [SQL Server], SQL Server Management Studio
- source controls [SQL Server Management Studio], tutorials
- Help [SQL Server], SQL Server Management Studio
- tutorials [SQL Server Management Studio]
- Transact-SQL tutorials
- solutions [SQL Server Management Studio], tutorials
- SQL Server Management Studio [SQL Server], tutorials
- scripts [SQL Server], SQL Server Management Studio
ms.assetid: d2bade70-07cf-4d94-b5d2-88aecb538ed1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8206fea828d6169975dc1d026a22e18e682f71e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582758"
---
# <a name="tutorial-sql-server-management-studio"></a><span data-ttu-id="3ea6c-102">Tutorial: SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3ea6c-102">Tutorial: SQL Server Management Studio</span></span>
  <span data-ttu-id="3ea6c-103">O tutorial do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] apresenta o ambiente integrado para gerenciar a infraestrutura do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3ea6c-103">The [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] tutorial introduces you to the integrated environment for managing your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] infrastructure.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="3ea6c-104">apresenta uma interface gráfica para configurar, monitorar e administrar as instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ea6c-104">presents a graphical interface for configuring, monitoring, and administering instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3ea6c-105">Ele também permite que você implante, monitore e atualize os componentes de camada de dados usados pelos aplicativos, como bancos de dados e data warehouses.</span><span class="sxs-lookup"><span data-stu-id="3ea6c-105">It also allows you to deploy, monitor, and upgrade the data-tier components used by your applications, such as databases and data warehouses.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="3ea6c-106">também fornece editores da linguagem [!INCLUDE[tsql](../../includes/tsql-md.md)], MDX, DMX e XML para editar e depurar scripts.</span><span class="sxs-lookup"><span data-stu-id="3ea6c-106">also provides [!INCLUDE[tsql](../../includes/tsql-md.md)], MDX, DMX, and XML language editors for editing and debugging scripts.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="3ea6c-107">O que você aprenderá</span><span class="sxs-lookup"><span data-stu-id="3ea6c-107">What You Will Learn</span></span>  
 <span data-ttu-id="3ea6c-108">Este tutorial o ajudará a compreender a apresentação de informações no [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] e como aproveitar os benefícios dos recursos.</span><span class="sxs-lookup"><span data-stu-id="3ea6c-108">This tutorial will help you understand the presentation of information in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and how to take advantage of the features.</span></span> <span data-ttu-id="3ea6c-109">Observe que este tutorial se aplica à instalação completa do [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] que é incluído em todas as edições de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], exceto [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ea6c-109">Note that this tutorial applies to the complete installation of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] that is included with all editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] except [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span> <span data-ttu-id="3ea6c-110">A funcionalidade para instalações básicas do [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] e para instalações do [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] fornecidas com o [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] é ligeiramente diferente da apresentada neste tutorial.</span><span class="sxs-lookup"><span data-stu-id="3ea6c-110">Functionality for basic installations of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and for [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] installations that ship with [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] is slightly different than what is presented in this tutorial.</span></span>  
  
 <span data-ttu-id="3ea6c-111">O melhor modo de se familiarizar com o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] é praticando.</span><span class="sxs-lookup"><span data-stu-id="3ea6c-111">The best way to get acquainted with [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] is through hands-on practice.</span></span> <span data-ttu-id="3ea6c-112">Este tutorial o ensinará a administrar os componentes do [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] e encontrar os recursos que você usa com regularidade.</span><span class="sxs-lookup"><span data-stu-id="3ea6c-112">This tutorial will teach you how to manage the components of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and how to find the features that you use regularly.</span></span>  
  
 <span data-ttu-id="3ea6c-113">Este tutorial divide-se em três lições:</span><span class="sxs-lookup"><span data-stu-id="3ea6c-113">This tutorial is divided into three lessons:</span></span>  
  
 [<span data-ttu-id="3ea6c-114">Lição 1: Navegação básica no SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3ea6c-114">Lesson 1: Basic Navigation in SQL Server Management Studio</span></span>](lesson-1-basic-navigation-in-sql-server-management-studio.md)  
 <span data-ttu-id="3ea6c-115">Nesta lição você aprenderá a usar os componentes do [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], a reconfigurar o layout do ambiente e a restaurar o layout padrão.</span><span class="sxs-lookup"><span data-stu-id="3ea6c-115">In this lesson you will learn how to use the components of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], how to reconfigure the environment layout, and how to restore the default layout.</span></span>  
  
 [<span data-ttu-id="3ea6c-116">Lição 2: Gravando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3ea6c-116">Lesson 2: Writing Transact-SQL</span></span>](lesson-2-writing-transact-sql.md)  
 <span data-ttu-id="3ea6c-117">Nesta lição, você aprenderá a abrir o Editor de Consultas, gerenciar código e usar os outros recursos novos do Editor de Consultas.</span><span class="sxs-lookup"><span data-stu-id="3ea6c-117">In this lesson, you will learn how to open Query Editor, how to manage code, and how to use the other new features of Query Editor.</span></span>  
  
 [<span data-ttu-id="3ea6c-118">Lição 3: Trabalhando com modelos, soluções e projetos de script</span><span class="sxs-lookup"><span data-stu-id="3ea6c-118">Lesson 3: Working with Templates, Solutions, and Script Projects</span></span>](lesson-3-working-with-templates-solutions-and-script-projects.md)  
 <span data-ttu-id="3ea6c-119">Nesta lição, você aprenderá a usar modelos e organizar scripts em soluções e projetos.</span><span class="sxs-lookup"><span data-stu-id="3ea6c-119">In this lesson you will learn how to use templates, and organize scripts into solutions and projects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ea6c-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3ea6c-120">Requirements</span></span>  
 <span data-ttu-id="3ea6c-121">Este tutorial foi desenvolvido para administradores experientes de bancos de dados e desenvolvedores de bancos de dados que não estão familiarizados com o [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], mas que estão familiarizados com conceitos de bancos de dados e linguagem [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3ea6c-121">This tutorial is intended for experienced database administrators and database developers who are not familiar with [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], but who are who are familiar with database concepts and the [!INCLUDE[tsql](../../includes/tsql-md.md)] language.</span></span>  
  
 <span data-ttu-id="3ea6c-122">Para que você possa usar o tutorial, os itens a seguir devem estar instalados no sistema:</span><span class="sxs-lookup"><span data-stu-id="3ea6c-122">Your system must have the following installed to use this tutorial:</span></span>  
  
-   [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="3ea6c-123">ou uma versão posterior com os bancos de dados de exemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3ea6c-123">or a later version with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample databases.</span></span> <span data-ttu-id="3ea6c-124">Para reforçar a segurança, os bancos de dados de exemplo não são instalados por padrão.</span><span class="sxs-lookup"><span data-stu-id="3ea6c-124">To enhance security, the sample databases are not installed by default.</span></span> <span data-ttu-id="3ea6c-125">Para instalar os bancos de dados de exemplo, consulte [Instalando amostras e bancos de dados de exemplo do SQL Server](http://sqlserversamples.codeplex.com).</span><span class="sxs-lookup"><span data-stu-id="3ea6c-125">To install the sample databases, see [Installing SQL Server Samples and Sample Databases](http://sqlserversamples.codeplex.com).</span></span>  
  
-   <span data-ttu-id="3ea6c-126">Internet Explorer 9.0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="3ea6c-126">Internet Explorer 9.0 or later.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ea6c-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3ea6c-127">See Also</span></span>  
 [<span data-ttu-id="3ea6c-128">Tutoriais do Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="3ea6c-128">Database Engine Tutorials</span></span>](../../relational-databases/database-engine-tutorials.md)  
  
  
